<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github-production-user-asset-6210df.s3.amazonaws.com/658727/272340510-34957be5-7318-4473-8141-2751ca571c4f.png">
    <source media="(prefers-color-scheme: light)" srcset="https://github-production-user-asset-6210df.s3.amazonaws.com/658727/272340472-ad8d7a46-ef85-47ea-9129-d815206ed2f6.png">
    <img alt="Garden" src="https://github-production-user-asset-6210df.s3.amazonaws.com/658727/272340472-ad8d7a46-ef85-47ea-9129-d815206ed2f6.png">
  </picture>
</p>
<div align="center">
  <a href="https://garden.io/?utm_source=github-web-app-example">Website</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://docs.garden.io/?utm_source=github-web-app-example">Docs</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://github.com/garden-io/garden/tree/0.13.21/examples">Examples</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://garden.io/blog/?utm_source=github-web-app-example">Blog</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://go.garden.io/discord">Discord</a>
</div>

## Welcome to Garden's Three Tier Web App Example 👋

This repository contains the three tier web app that's used in the [Getting Started with
Garden video series](https://youtu.be/0y5E8K-8kr4) and in the ['Your First Project' tutorial](https://docs.garden.io/tutorials/your-first-project) from our documentation.

- If you're coming from the tutorial, checkout out to the [`tutorial-start`](https://github.com/garden-io/web-app-example/tree/tutorial-start) branch to follow along.
- If you're coming from the tutorial but can't wait to see the end result, checkout out to the [`tutorial-complete`](https://github.com/garden-io/web-app-example/tree/tutorial-complete) branch.
- If you're here to look at the end result of the "Getting Started" video, use the `main` branch.

## About the project

The project is a simplified version of the microservice voting application you'll find in various Garden examples. Garden is typically used in projects that have multiple microservices but
sometimes its better to keep things simple and here we have a three-tier web app version with API, web and database components.

### Garden Plugins

The `main` branch that the ["Getting Started" video](https://youtu.be/0y5E8K-8kr4) is based off uses the [`ephemeral-kubernetes`](https://docs.garden.io/kubernetes-plugins/ephemeral-k8s) plugin. The [tutorial from our documentation](https://docs.garden.io/tutorials/your-first-project) however goes into more detail and discusses the different options for deploying the project to Kubernetes.

### Garden Actions

The project is a voting application with the following components:

- `web` — A frontend Vue application
- `api` — A Python API server
- `db` — A Postgres database

These services are built, deployed, and tested with [Garden actions](https://docs.garden.io/overview/core-concepts#action).

Specifically, the `api` and `web` components have their own Kubernetes manifests so we use the `container` Build action to build them
and the `kubernetes` Deploy action to deploy them.

The `db` component is an "off the shelf" Postgres Helm chart that's deployed via the `helm` Deploy action.
