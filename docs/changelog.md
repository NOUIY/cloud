---
title: Changelog
menuText: Changelog
description: See what's new in Serverless Cloud as we build the most developer-friendly serverless app platform ever! 🚀
menuOrder: 6
---

# Serverless Cloud updates and changes

See what's new in Serverless Cloud as we build the most developer-friendly serverless app platform ever! 🚀

## September 2021

### Bring Your Own Framework (BYOF) Support

You can now use your existing HTTP frameworks like Express.js or Connect with Serverless Cloud. Using our new `http` helper, we will support your framework's API routing capabilities while still allowing you to take advantage of our other features. Serverless Cloud provides our own [modern API framework](/cloud/docs/apps/api) that makes it easy to build and deploy cloud native APIs, but if you've already invested in another framework, you can now easily migrate that application to Serverless Cloud. Learn more about this feature in the [documentation](https://www.serverless.com/cloud/docs/apps/frameworks)

```javascript
// Import and initialize your framework
import express from "express"; // or any supported framework
const app = new express();

// Enable express body parsing middleware
app.use(express.json());

// Import the http helper and wrap your initialized app
import { http } from "@serverless/cloud";
http.use(app);

// Express yourself! 🎉
app.get("/", (req, res) => {
	... make api magic ...
})
```

### Lightning Fast Syncing!

Serverless Cloud gives you a personal developer instance which syncs your code changes automatically from your IDE as you develop your application. This typically took 5-10 seconds to sync these changes. We are excited to release a major perfomance improvement that reduces the sync time to less than 1 seconds for normal code changes. With this update, code changes are immediately synced and deployed to your personal developer instance before you can even switch to your browser to test them. This feature requires you to update your CLI to the latest version.

### CLI Update for Faster & Simpler Onboarding

We continue to work on the onboarding process to make it incredible fast and easy to get a project up and running with Serverless Cloud. This update introduces new features to let you select between different sample applications, as well as some style/usability updates to the CLI to enhance developer productivity. Just type `cloud` from your terminal to see the latest changes! This feature requires you to update your CLI to the latest version.

### Data Events

We are very excited to announce the release of **Data Events** to Serverless Cloud. With this new update, you’re able to listen for changes to Serverless Data items, and then perform tasks asynchronously on the changed data. This opens up more use cases and processing capabilities for Serverless Cloud, including Slackbots and other applications that require asynchronous processing. Read more about this update from the [documentation](https://www.serverless.com/cloud/docs/apps/data#reacting-to-changes).

### Custom Domains Support

When you need to share your work with the outside world, it’s probably best to do it with your own brand. With this new update, you’ll be able to assign a custom domain to stages and start serving your application on your domain. In order to take advantage of this update:

1. Visit the settings page for any stage from the dashboard.
2. Click “Add Domain” and type in your domain name.
3. Add the record appeared in your domain registrar to verify the domain name.

### Serverless Cloud Private Preview

We have been working for months to make Serverless Cloud available to more people, and today we are proud to announce our Private Preview Launch. The registration is open on the Serverless Cloud Dashboard but we’ll start putting newcomers on the waitlist when we run out of our limited seats. We have also made some improvements on our CLI, so don’t forget to update it to the latest version.

We’d like to thank all of our private beta users for helping us get Serverless Cloud ready to launch. Your continued feedback is much appreciated.

## August 2021

### TypeScript Support

We are happy to announce that you can now build your Serverless Cloud applications using Typescript. Change the entry point of the application to `index.ts` to enable TypeScript. More information can be found in our [documentation](https://www.serverless.com/cloud/docs/apps/typescript).

### CI/CD Integration

We are happy to announce that you can now add CI/CD automation to your Serverless Cloud workflows. Create an access key in the Serverless Cloud dashboard and add it as an environment variable name `SERVERLESS_ACCESS_KEY` in your CI/CD environment. See the GitHub Actions example from our [documentation](https://www.serverless.com/cloud/docs/workflows/cicd).

### Monitoring with Instance Level Metrics

For any customer facing application, it’s crucial to see the performance of your application by keeping track of the important metrics. We are happy to announce instance level metrics that provides information about the number of requests, errors, and duration with additional summary data. Visit the metrics page for your instance from the Serverless Cloud dashboard to track performance.

### Testing for Serverless Cloud Applications

We are excited to announce new built-in testing capabilities for Serverless Cloud. You’ll be able to write unit and integration tests by using a Jest-compatible testing framework. Serverless Cloud creates an isolated test instance when you type `cloud test`, seeds it with data you provide, runs your tests and tears down the test instance. You can now run your tests against real cloud environments with a single command. You can also run your tests against your personal instance by typing `test` command from Cloud Shell. Visit our [documentation](https://www.serverless.com/cloud/docs/workflows/testing) for more information.

### Set Timeouts for APIs and Schedules

We are happy to introduce the ability to set timeout values for APIs and scheduled tasks on Serverless Cloud. You can now set timeouts of up to 29 seconds for API routes and up to 5 minutes for scheduled tasks.

```javascript
// Set a timeout for an API route
api.get('/foo', { timeout: 5000 }, (req, res) => { ...do something ... });

// Set a timeout for a schedule task
schedule.every('1 hour', { timeout: 30000 }, (event) => { ...do something ... });
```

## July 2021

### Parameter/Secrets Support

You are now able to define app level parameters and read the values programmatically from your Serverless Cloud applications. When you change a parameter in the dashboard, all running instances are immediately updated with the new value. Parameters can also be overridden at the instance level to allow you to set different values for different instances. All the parameters are encrypted and stored securely by Serverless Cloud. Visit our [documentation](https://www.serverless.com/cloud/docs/apps/params) for more information.

### Introducing Serverless Cloud Dashboard

Early users of Serverless Cloud have been using our CLI to build applications and manage workflows. Today, we are super excited to bring user a dashboard available at [cloud.serverless.com](https://cloud.serverless.com).

You can take following actions on Serverless Cloud Dashboard:

- View apps, create new apps, delete existing apps.
- View instances of apps, edit the name of an instance, delete an instance, create a new instance.
- View the API routes and scheduled tasks for an instance.

We’ll continue to add new capabilities to the Serverless Cloud Dashboard. Stay tuned for upcoming updates!

## June 2021

### Introducing the “cloud” shell

Previously, our users have been using the `cloud init` command to create a Serverless Cloud project in a directory and then type the `cloud start` command to initiate their development session on their personal development instance.

Today, we are simplifying this process by introducing the `cloud` command that combines the functionality of `init` and `start` commands. This new command now activates the “Cloud Shell” that makes it easier to run commands on Serverless Cloud. This feature requires you to update your CLI to the latest version.

### Serverless Cloud Private Beta Launch

After working for months and making internal releases with our team, we are super excited to say “hello world!” and launch the private beta release of Serverless Cloud. Serverless Cloud lets you build scalable, highly-secure, pay-per-use applications, without needing a deep knowledge of cloud services. The goal of Serverless Cloud is to reduce development complexity by focusing on interpretation instead of configuration, and by automatically applying best practices to common use cases, removing the need for all the boilerplate and configuration, and allowing developers to do what they do best: build software.
