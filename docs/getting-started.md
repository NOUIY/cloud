---
title: Getting Started
menuText: Get Started
description: Get started using Serverless Cloud with just a few simple steps.
menuOrder: 2
---

## Getting Started

Install globally from npm...

```
npm i -g @serverless/cloud@latest
```

Create a new directory...

```
mkdir my-cloud && cd my-cloud
```

Initialize a sample app and start developing

```
cloud
```

Visit the url, see live logs, make changes, and watch them quickly deploy to your own **personal instance**. Cloud Shell helps you write commands and go back in command history.

When ready, you can publish to `prod` from Cloud Shell:

```
deploy prod
```

This will publish to a completely seperate instance. You may continue developing using `cloud` without affecting `prod`, but anytime you want to copy the entire `prod` instance (including data) into your own personal development instance, just run:

```
clone [service_name]/prod
```

And continue developing on the code and data copied from `prod`:

## Building Applications with Serverless Cloud Helpers

`api`, `data`, `schedule`, and `params` are the helpers that you can use while developing on Serverless Cloud. You can import those helpers by importing them from @serverless/cloud package at the top of your index.js file as follows.

```javascript
// CommonJS
const { api, data, schedule, params } = require("@serverless/cloud");

// ES Modules
import { api, data, schedule, params } from "@serverless/cloud";
```

## Serverless Cloud Dashboard

Visit Serverless Cloud Dashboard to see your apps and instances, to define secrets and apply it to your instances and to check the logs and metrics of your instances via [cloud.serverless.com](https://cloud.serverless.com).

### Want to get started building apps on Serverless Cloud?

[Get access](https://cloud.serverless.com/?view=register)

## Feedback

Please log any issues and additional feedback can be sent to [cloud@serverless.com](mailto:cloud@serverless.com).
