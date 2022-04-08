<div align="center">

<a href="https://getunleash.io" title="Unleash - Create with freedom. Release with confidence">
    <img src="./.github/github_header_opaque_landscape.svg" alt="The Unleash website">
</a>

[![Build and Tests](https://img.shields.io/github/workflow/status/unleash/unleash/Build%20%26%20Tests)](https://github.com/Unleash/unleash/actions/workflows/build.yaml)
[![Coverage Status](https://coveralls.io/repos/github/Unleash/unleash/badge.svg?branch=main&)](https://coveralls.io/github/Unleash/unleash?branch=main) [![npm](https://img.shields.io/npm/v/unleash-server)](https://www.npmjs.com/package/unleash-server)
[![Docker Pulls](https://img.shields.io/docker/pulls/unleashorg/unleash-server)](https://hub.docker.com/r/unleashorg/unleash-server)
[![Apache-2.0 license](https://img.shields.io/github/license/unleash/unleash)](https://github.com/Unleash/unleash/blob/main/LICENSE)
[![Join Unleash on Slack](https://img.shields.io/badge/slack-join-635dc5?logo=slack)](https://slack.unleash.run)

</div>

## About Unleash

Unleash is an open source feature management solution. It improves the workflow of your development team and leads to quicker software delivery. Unleash increases efficiency and gives teams *full control* of how and when they enable new functionality for end users. Unleash lets teams ship code to production in *smaller* releases *whenever* they want.

Feature toggles make it easy to test how your code works with real production data without the fear that you'll accidentally break your users' experience. It also helps your team work on multiple features in parallel without each maintaining an separate feature branch.

Unleash is the largest open source solution for feature flagging on GitHub. There's 12 official client and server SDKs and 10+ community SDKs available; you can even make your own if you want to. You can use Unleash with any language and any framework.

## Get started in 2 steps

### 1. Start Unleash

With [`git`](https://git-scm.com/) and [`docker`](https://www.docker.com/) installed, it's easy to get started:

Run this script:
``` bash
git clone git@github.com:Unleash/unleash-docker.git
cd unleash-docker
docker compose up -d
```

Then point your browser to `localhost:4242` and log in using
  - username: `admin`
  - password: `unleash4all`

### 2. Connect your SDK

Find your preferred SDK in [our list of official SDKs](#unleash-sdks) and import it into your project. Follow the setup guides for your specific SDK.

If you use the docker compose file from the previous step, here's the configuration details you'll need to get going:
- For front-end SDKs, use:
  - URL: `http://localhost:3000`
  - `clientKey`: `proxy-client-key`
- For server-side SDKs, use:
  - Unleash API URL: `http://localhost:4242`
  - API token: `default:development.unleash-insecure-api-token`

If you use a different setup, your configuration details will most likely also be different.

### Check a feature toggle

Checking the state of a feature toggle in your code is easy! The syntax will vary depending on your language, but all you need is a simple function call to check whether a toggle is available. Here's how it might look in Java:

```java
if (unleash.isEnabled("AwesomeFeature")) {
  // do new, flashy thing
} else {
  // do old, boring stuff
}
```

### Run Unleash on a service?

If you don't want to run Unleash locally, we also provide easy deployment setups for Heroku and Digital Ocean:

[![Deploy to Heroku](./.github/deploy-heroku-20.png)](https://www.heroku.com/deploy/?template=https://github.com/Unleash/unleash) [![Deploy to DigitalOcean](./.github/deploy-digital.svg)](https://cloud.digitalocean.com/apps/new?repo=https://github.com/Unleash/unleash/tree/main&refcode=0e1d75187044)

## Online demo

Try out [the Unleash online demo](https://www.getunleash.io/interactive-demo).

![The Unleash UI. It shows a project and its users, feature toggles and tabs for health, access, and environments.](./.github/github_online_demo.svg)

## Community and help — sharing is caring

We know that learning a new tool can be hard and time-consuming. We have a growing community that loves to help out. Please don't hesitate to reach out for help.

[![Join Unleash on Slack](https://img.shields.io/badge/slack-join-635dc5?logo=slack)](https://slack.unleash.run)

💬 ![Join Unleash on Slack](https://slack.unleash.run) if you want ask open questions about Unleash, feature toggling or discuss these topics in general.

💻 [Create a GitHub issue](https://github.com/Unleash/unleash/issues/new) if you have found a bug or have ideas on how to improve Unleash.

📚 [Visit the documentation](https://docs.getunleash.io/) for more in-depth descriptions, how-to guides, and more.

## Contribute to Unleash

Building Unleash is a collaborative effort, and we owe a lot of gratitude to many smart and talented individuals.
Building it together with community ensures that we build a product that solves real problems for real people.
We'd love to have your help too: Please feel free to open issues or provide pull requests.

Check out [the CONTRIBUTING.md file](./CONTRIBUTING.md) for contribution guidelines and the [Unleash developer guide](./website/docs/contributing/developer-guide.md) for tips on environment setup, running the tests, and running Unleash from source.

## Features our users love

### Flexibility and adaptability

- Get an easy overview of all feature toggles across all your environments, applications and services
- Use included [activation strategies](https://docs.getunleash.io/user_guide/activation_strategy) for most common use cases, or use a [custom activation strategy](https://docs.getunleash.io/advanced/custom_activation_strategy) to support any need you might have
- Organise feature toggles by [feature toggle tags](https://docs.getunleash.io/advanced/tags)
- [Canary releases / gradual rollouts](https://docs.getunleash.io/user_guide/activation_strategy#gradual-rollout)
- Targeted releases: release features to specific [users](https://docs.getunleash.io/user_guide/activation_strategy#userids), [IPs](https://docs.getunleash.io/user_guide/activation_strategy#ips), or [hostnames](https://docs.getunleash.io/user_guide/activation_strategy#hostnames)
- [Kill switches](https://docs.getunleash.io/advanced/feature_toggle_types#feature-toggle-types)
- [A/B testing](https://docs.getunleash.io/topics/a-b-testing)
- 2 [environments](https://docs.getunleash.io/topics/a-b-testing)
- Out-of-the-box integrations with popular tools ([Slack](https://docs.getunleash.io/addons/slack), [Microsoft Teams](https://docs.getunleash.io/addons/teams), [Datadog](https://docs.getunleash.io/addons/datadog)) + integrate with anything with [webhooks](https://docs.getunleash.io/addons/webhook)
- [Dashboard for managing technical debt](https://docs.getunleash.io/user_guide/technical_debt) and [stale toggles](https://docs.getunleash.io/user_guide/technical_debt#stale-and-potentially-stale-toggles)
- API-first: *everything* can be automated. No exceptions.
- [12 official client SDKs](https://docs.getunleash.io/sdks#official-sdks), and ten [community-contributed client SDKs](https://docs.getunleash.io/sdks#community-sdks)
- Run it via Docker with the [official Docker image](https://hub.docker.com/r/unleashorg/unleash-server) or as a pure Node.js application

### Security & performance

- Privacy by design (GDPR and Schrems II). End-user data never leaves your application.
- [Audit logs](https://docs.getunleash.io/advanced/audit_log)
- Enforce [OWASP's secure headers](https://owasp.org/www-project-secure-headers/) via the strict HTTPS-only mode
- Flexible hosting options: host it on premise or in the cloud (*any* cloud)
- Scale [the Unleash Proxy](https://docs.getunleash.io/sdks/unleash-proxy) independently of the Unleash server to support any number of front-end clients without overloading your Unleash instance

### Looking for more features?

If you're looking for one of the following features, please take a look at our [Pro and Enterprise plans](https://www.getunleash.io/plans):
- [role-based access control (RBAC)](https://docs.getunleash.io/user_guide/rbac)
- [single sign-on (SSO)](https://docs.getunleash.io/advanced/enterprise-authentication)
- more environments
- [feature toggles project support](https://docs.getunleash.io/user_guide/projects)
- [advanced segmentation](https://docs.getunleash.io/reference/segments)
- [additional strategy constraints](https://docs.getunleash.io/advanced/strategy_constraints)
- tighter security
- more hosting options (we can even host it for you!)

## Architecture

<img src="./.github/Unleash_architecture.svg" title="Unleash System Overview" />

Read more in the [*system overview* section of the Unleash documentation](https://docs.getunleash.io/user_guide/unleash_overview#system-overview).

## Unleash SDKs

To connect your application to Unleash you'll need to use a client SDK for your programming language.

**Official server-side SDKs**:

- [Go SDK](https://docs.getunleash.io/sdks/go_sdk)
- [Java SDK](https://docs.getunleash.io/sdks/java_sdk)
- [Node.js SDK](https://docs.getunleash.io/sdks/node_sdk)
- [PHP SDK](https://docs.getunleash.io/sdks/php_sdk)
- [Python SDK](https://docs.getunleash.io/sdks/python_sdk)
- [Ruby SDK](https://docs.getunleash.io/sdks/ruby_sdk)
- [Rust SDK](https://github.com/unleash/unleash-client-rust)
- [.NET SDK](https://docs.getunleash.io/sdks/dot_net_sdk)

**Official front-end SDKs:**

The front-end SDKs connects via the [Unleash Proxy](https://docs.getunleash.io/sdks/unleash-proxy) in order to ensure privacy, scalability and security.

- [Android SDK](https://docs.getunleash.io/sdks/android_proxy_sdk)
- [Javascript SDK](https://docs.getunleash.io/sdks/proxy-javascript)
- [React SDK](https://docs.getunleash.io/sdks/proxy-react)
- [iOS SDK](https://docs.getunleash.io/sdks/proxy-ios)

**Community SDKs**

If none of the official SDKs fit your need, there's also a number of [community-developed SDKs](https://docs.getunleash.io/sdks#community-sdks) where you might find an implementation for your preferred language (such as  [Elixir](https://gitlab.com/afontaine/unleash_ex), [Dart](https://pub.dev/packages/unleash), [Clojure](https://github.com/AppsFlyer/unleash-client-clojure), and more).

## What is a feature toggle?

The main motivation for doing feature toggling is to decouple the process for deploying code to production and releasing new features. This helps reducing risk, and allow us to easily manage which features to enable, and have full control of how we exposed the new feature for.

> Feature toggles decouple **deployment** of code from **release** of new features.

This repo contains the unleash-server, which contains the Unleash Admin UI and the Unleash API. To make use of unleash you will also need a client SDK.

<img src="./.github/dashboard.png" alt="Unleash Admin UI" />

[Online demo](https://app.unleash-hosted.com/demo)

## Segmentation

It's fine to have a system for turning stuff on and off. But sometimes we want more granular control, we want to decide who the toggle should be enabled for. This is where activation strategies come into the picture. Activation strategies take arbitrary config and allow us to enable a toggle to a specific subset of your users (segment).

Common activation strategies includes:

- Active For users with a specified userId
- GradualRollout to X-percent of our users
- Active for our beta users
- Active only for application instances running on host x.

Read more about [activation strategies in our docs](https://docs.getunleash.io/docs/user_guide/activation_strategy).

## The Client API

The [client SDKs](https://docs.getunleash.io/sdks) provides a simple abstraction making it easy to check feature toggles in your application. The code snippet below shows how you would use `Unleash` in Java.

```java
if (unleash.isEnabled("AwesomeFeature")) {
  //do some magic
} else {
  //do old boring stuff
}
```

## Running Unleash

The are numbers of ways you can run Unleash.

1. Unleash Enterprise - Cloud hosted by the Unleash Team. [see plans](https://www.getunleash.io/plans)
2. Unleash Open-Source - Self host with Docker. [Guide](https://docs.getunleash.io/deploy/getting_started#start-unleash-server)
3. Unleash Open-Source - Self host with Node.js [Guide](https://docs.getunleash.io/deploy/getting_started#start-unleash-server)
4. Unleash Open-Source - Helm chart [artifacthub.io](https://artifacthub.io/packages/helm/unleash/unleash)

### Run from Docker

1. Create a network by running the following command:

```sh
docker network create unleash
```

2. Start a postgres database:

```sh
docker run -e POSTGRES_PASSWORD=some_password \
  -e POSTGRES_USER=unleash_user -e POSTGRES_DB=unleash \
  --network unleash --name postgres postgres
```

3. Start Unleash via docker:

```sh
docker run -p 4242:4242 \
  -e DATABASE_HOST=postgres -e DATABASE_NAME=unleash \
  -e DATABASE_USERNAME=unleash_user -e DATABASE_PASSWORD=some_password \
  -e DATABASE_SSL=false \
  --network unleash unleashorg/unleash-server
```

The first time Unleash starts it will create a default user which you can use to sign-in to your Unleash instance and add more users with:

- username: `admin`
- password: `unleash4all`

## Users of Unleash

Unleash is trusted by thousands of companies all over the world (we are tracking more than 90 countries already). Proud Open-Source users:

<a href="https://www.nav.no" title="NAV.no"><img src="./.github/ext-logos/nav.jpg" height="70" style="padding: 10px; border: 1px solid silver"></a> <a href="https://www.otovo.com" title="Otovo"><img src="./.github/ext-logos/otovo.png" height="70" style="padding: 10px; border: 1px solid silver"></a> <a href="https://www.amedia.no/" title="Amedia"><img src="./.github/ext-logos/amedia-logo.png" height="70" style="padding: 10px; border: 1px solid silver"></a> <a href="https://budgets.money" title="Budgets"><img src="./.github/ext-logos/budgets.png" height="70" style="padding: 10px; border: 1px solid silver"></a> <a href="https://www.finn.no" title="FINN.no"><img src="./.github/ext-logos/finn.jpg" height="70" style="padding: 10px; border: 1px solid silver"></a>

_(PS! feel free to submit your logo!)_

## In the media

- [Free Code Camp: Feature toggles - Why and how to add to your software](https://www.youtube.com/watch?v=-yHZ9uLVSp4)
- [Feature toggling transient errors in load tests](https://nrkbeta.no/2021/08/23/feature-toggling-transient-errors-in-load-tests/) (English)
- [The Code Kitchen Episode 7: Feature flags with Unleash](https://share.fireside.fm/episode/zD-4e4KI+Pr379KBv) (English)
- [Utviklerpodden, 1 - Feature Flags og Unleash med Fredrik Oseberg](https://pod.space/utviklerpodden/feature-flags-og-unleash-med-fredrik-oseberg) (Norwegian)
- [Node Weekly issue 380](https://nodeweekly.com/issues/380)
- [Console 42 - The open-source newsletter](https://console.substack.com/p/console-42)
- [This Week in Rust 340](https://this-week-in-rust.org/blog/2020/05/27/this-week-in-rust-340/)
- [Unleash-hosted - Unleash as a Service](https://www.unleash-hosted.com)
- [Medium blog](https://medium.com/unleash-hosted)
- [Blog: Unleash your features gradually!](http://bytes.schibsted.com/unleash-features-gradually/)
- [Presentation: Unleash your features gradually!](http://ivarconr.github.io/feature-toggles-presentation/sch-dev-lunch-2017/#1)
- http://martinfowler.com/bliki/FeatureToggle.html
