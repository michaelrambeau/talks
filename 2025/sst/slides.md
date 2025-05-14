---
title: Introducing SST

# apply unocss classes to the current slide
class: text-center
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
---

<div class="flex flex-col gap-6 items-center">

<img class="inline" src="https://sst.dev/_astro/logo-dark.DpZ7_bWK.svg" width="400" />

# Introducing SST

A presentation by Michael Rambeau
• 2025-05-14

</div>

---

## Context

We are building Calliope, a web application (SPA) connected to a REST API.

50 end-points: GET (26), POST (22) & PUT (2)

Most of the backend logic is in the monorepo `cci-calliope` that combines the React SPA and the API (100% TypeScript) 

Also: multiple services from other repos `cci-*` (Python)

---

## What we use currently: [serverless](https://www.serverless.com/) Framework 3

![Serverless Logo](https://cdn.prod.website-files.com/60acbb950c4d6606963e1fed/60acbb950c4d66854e3e2013_logo%20serverless%20dark.svg)

An open-source CLI tool to build, configure, and deploy serverless applications.

Can be used for:

- APIs end-point (AWS Lambda functions + API ApiGatewayV2)
- CRON jobs
- ...

Written in JS but can handle TypeScript (via esbuild plugin) and Python code

---

## How it looks like

Configuration with yml files

- `serverless.yml` describes the application configuration, sets up the environment variables
- `function.yml` describes all AWS Lambda functions: handlers + events that trigger the functions
- `resources.yml` describes the resources to be created:
  - databases (`AWS::DynamoDB::Table`)
  - queues (`AWS::SQS::Queue`)
  - alarms

---

### Deployment

Deployment from the command line targeting a **stage**:

```sh
serverless deploy --stage production
```

Every function is bundled, zipped and uploaded to AWS Lambda

Can be used to deploy a single function useful when developing and testing functions in the cloud because there is no "local" mode


```sh
serverless deploy --stage production --function myFunction
```

---

### API handlers

```yml
getAgentList:
  handler: src/handlers/agents/getAgentList.wrappedHandler # the exported function
  events: # what triggers the function to run
    - httpApi:
        method: get
        path: /agents/list
        authorizer:
          name: cciJwtAuthorizer
  destinations:
    onFailure: failureHandler
```

Docs: [Lambda destinations](https://www.serverless.com/blog/lambda-destinations/)

---

### CRON jobs

`functions.yml` can be used to set up CRON jobs too:

```yml
cronPerformanceMetrics:
  handler: src/handlers/metrics/cronPerformanceMetrics.wrappedHandler
  memorySize: 2048 # MB compromise on speed and price
  timeout: 240 # 4 minutes timeout so completes within cron interval
  events:
    - schedule:
          description: Renew performance metrics cache every 5 minutes
          rate: cron(0/5 * * * ? *)
  destinations:
    onFailure: failureHandler
```

---

## The main issue

The serverless business model has changed!

> The Serverless Framework CLI V.4+ is free, except for organizations earning over $2 million annually

---

### Other issues

Poor DX (improved with serverless 4)

Tedious setup with yml files (no guards against typos)

Lack of support (type inference) in the IDE

---

## Options to move away?

Get a license and upgrade to serverless 4? (which looks good: better DX and TS support)

Migrate to something else?
  - Open source fork of serverless: https://github.com/oss-serverless/serverless
  - AWS CDK
  - SST
  - any one aware of other options?

---

## Doing nothing is not really an option

Tech debt! (Node.js version, dependencies)

Vulnerabilities

Support / Documentation

---

## Introducing SST

> A framework that makes it easy to build serverless apps

A nice abstraction on top of AWS

Provides +150 components:

- Low level AWS resources (functions, queues, databases)
- Higher level frameworks
  - Full stack frameworks: Next.js, Astro
  - Backend frameworks: [Express](https://sst.dev/docs/start/aws/express/), [Hono](https://sst.dev/docs/start/aws/hono/), [NestJS](https://sst.dev/docs/start/aws/nestjs/)
  - Static site support: Perfect for SPAs with S3 + CloudFront ([docs](https://sst.dev/docs/component/aws/static-site/))

---

## Infrastructure as Code

Everything is code!

```ts
const api = new sst.aws.ApiGatewayV2("sst-playground-api");

api.route("GET /status", {
  handler: "api/src/handlers/v2/index.status",
  environment: { MY_VALUE: "xxx" },
});
```

---

## Dev mode

Used to develop in local, using resources created automatically.

Changes to the code are reflected by the API end-point in a few milliseconds! ⚡

You get an API URL you can connect your web app.

> Starts a watcher that deploys any infrastructure changes.
>
> Runs your functions Live, letting you make and test changes without having to redeploy them.
>
> Creates a tunnel to connect your local machine to any resources in a VPC.
>
> Starts your frontend and container services in dev mode and links it to your infrastructure.

---

### Terminal output

```
SST 3.14.11  ready!
➜  App:        sst-calliope
   Stage:      michael
   Console:    https://console.sst.dev/local/sst-calliope/michael
~  Deploy
↗  Permalink   https://sst.dev/u/5392165a
✓  Complete
   sst-playground-api: https://ifs8g2ziue.execute-api.ap-northeast-1.amazonaws.com
   ---
   api: https://ifs8g2ziue.execute-api.ap-northeast-1.amazonaws.com
   message: OK!
```

---

## SST Console

A web-based dashboard to manage your SST apps, hosted on their side (console.sst.dev)

- View all apps, resources and updates
- Real-time logs and alerts
- Git push to deploy
- Local development integration
- Team collaboration

Docs: https://sst.dev/docs/console/

---

## History / Numbers

Created in 2020

200 contributors, 3,400 commits

Built on top of Pulumi since [v3 release](https://sst.dev/blog/sst-v3), released in August 2024, instead of AWS CDK

Led by [Dax Raad](https://twitter.com/thdxr), known for his work on Local First web apps

Major milestones:

- v1: Initial release with AWS CDK
- v2: Improved DX and TypeScript support
- v3: Switched to Pulumi and Terraform, better multi-cloud support

Growing community with 23K+ GitHub stars

---

## Actively maintained!

[Latest tweet about OpenSearch](https://x.com/jayair/status/1922049110397387199)

<Tweet id="1922049110397387199" />


> The new `OpenSearch` component lets you add a new instance of OpenSearch to your app.

> We had gotten a few requests for this one.

> It also supports:

> - Sharing an instance across stages
> - Optionally connecting to a local instance in `sst dev`

---

## Real world examples


| Project | Description | Link
| --- | --- | --- |
| [tldraw](https://github.com/tldraw/tldraw) | A collaborative drawing and diagramming tool | [SST Config](https://github.com/tldraw/tldraw/blob/main/sst.config.ts)
| [Nestri](https://github.com/nestrilabs/nestri) | A self-hosted cloud gaming solution for your home server (Geforce Now alternative) | [SST Config](https://github.com/nestrilabs/nestri/blob/main/sst.config.ts)



---

## Router: API Management Made Simple

```ts
const router = new sst.aws.Router("MyRouter", {
  domain: {
    name: "api.example.com",
    aliases: ["*.api.example.com"]
  }
});

// Add routes to the same API Gateway
router.add("GET /users", "src/users.list");
router.add("POST /users", "src/users.create");
router.add("GET /products", "src/products.list");
```

Benefits:
- Single CloudFront distribution for all routes
- Type-safe route definitions
- Automatic CORS configuration
- Custom domain support
- Stage-based routing (dev, prod, PR environments)

Docs: [Configure a Router](https://sst.dev/docs/configure-a-router/)

---

## Summarizing the benefits

IaC (Infrastructure as Code)

Type safety

Excellent developer experience

Not tied to AWS (you can deploy to Cloudflare too)

Full-stack capabilities

---

## Migration Strategy

Two-phase approach:
1. Pilot phase
   - Migrate non-critical endpoints (e.g., user management)
   - Deploy to `api.v2.xxx.jp`
   - Validate deployment process and resource connections
   - Inconvenient: could slow down deploy of all end-point as SST dependency would be installed for nothing

2. Full migration
   - Move remaining endpoints to SST
   - Switch traffic to new domain
   - Remove serverless 3 dependencies


---

## Demo time!

To showcase:

- Dev mode
- Secrets management (over .env files)
- Link between resources
- Async nature
- Type Safety

---
layout: center
---

## Thank you!

Let me know what you think of SST and what you use in your own projects!



