<p align="center">
  <a href="https://www.medusajs.com">
    <img alt="Medusa" src="https://user-images.githubusercontent.com/91620216/197357924-7ecbbce9-7e29-4d55-be6d-76c4dffb4f1c.png" width="100" />
  </a>
</p>

<h1 align="center">
  Medusa for Artists
</h1>

<p align="center">
Medusa is an open-source headless commerce engine that enables developers to create amazing digital commerce experiences. This project builds on top of it to bring
it close to artists!
</p>

<p align="center">
  <a href="https://github.com/medusajs/medusa/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Medusa is released under the MIT license." />
  </a>
  <a href="https://github.com/medusajs/medusa/blob/master/CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="PRs welcome!" />
  </a>
  <a href="https://discord.gg/xpCwq3Kfn8">
    <img src="https://img.shields.io/badge/chat-on%20discord-7289DA.svg" alt="Discord Chat" />
  </a>
  <a href="https://twitter.com/intent/follow?screen_name=medusajs">
    <img src="https://img.shields.io/twitter/follow/medusajs.svg?label=Follow%20@medusajs" alt="Follow @medusajs" />
  </a>
</p>

> **Prerequisites**: To use the starter you should have a Medusa server running locally on port 9000. Check out [medusa](https://github.com/eggsmayhem/medusa) for a quick setup.

# Overview

![banner](https://user-images.githubusercontent.com/91620216/197358920-7c238de0-bf1c-4f86-9512-1441fa6cd1e8.png)

Changes over the Next.js starter:

- Site structure optimized for artists
- Dramatic color scheme
- SEO
- Focus indicator for increased accessibility 
- Carousel to display past works
- Separate page highlighting commissionable art by category

Going forward:

- [ ] Simplified admin panel
- [ ] Artist can update commissions page through admin panel, decreasing need for developer intervention
- [ ] Associate images with variant type at checkout for cleaner customer experience

Medusa for artists is built with:

- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Typescript](https://www.typescriptlang.org/)
- [Medusa](https://medusajs.com/)

## Out-of-the-box Artist Features

### Storefront Carousel

An attractive Carousel on your storefront can show your customers your past work by category and extend your site from a mere store to clearly offering custom commissions as well, a seamless feature to help artists sell more art

![carousel](https://user-images.githubusercontent.com/91620216/197407995-c96f840e-370b-495f-abeb-23abaed97058.gif)

### Gallery and Commissions

This template includes a customizable Gallery componenet where the artist can display their past works by category/medium.

An artist can easily plug in their past works for a nicely-formatted Gallery, along with a link to contact the artist about commissioning custom work

![commissions](https://user-images.githubusercontent.com/91620216/197408427-16512e2c-fc76-4fa7-a051-8b90b8ff519b.gif)

# Quickstart

## Deploy in 5 minutes

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/medusajs/nextjs-starter-medusa)

## Setting up the environment variables

Navigate into your projects directory and get your enviroment variables ready:

```shell
cd nextjs-starter-medusa/
mv .env.template .env.local
```

### Install dependencies

Use Yarn to install all dependencies.

```shell
yarn
```

### Start developing

You are now ready to start up your project.

```shell
yarn dev
```

### Open the code and start customizing

Your site is now running at http://localhost:8000!

Edit `/pages/index.tsx` to see your site update in real-time!

# Payment integrations

By default this starter supports the following payment integrations

- [Stripe](https://stripe.com/)
- [Paypal](https://www.paypal.com/)

To enable the integrations you need to add the following to your `.env.local` file:

```shell
MEDUSA_PAYMENT_STRIPE_PUBLIC_KEY=<your-stripe-public-key>
MEDUSA_PUBLIC_PAYPAL_CLIENT_ID=<your-paypal-client-id>
```

You will also need to setup the integrations in your Medusa server. See the [Medusa documentation](https://docs.medusajs.com) for more information on how to configure [Stripe](https://docs.medusajs.com/add-plugins/stripe) and [PayPal](https://docs.medusajs.com/add-plugins/paypal) in your Medusa project.

# SEO integration

There are several implentations to further optimize SEO. One such implentation is the careful curation of meta data. In addition, the starter has been populated with meaningful semantic and alt tags. All of which increase accessibility for all. 

# Search integration

This starter is configured to support using the `medusa-search-meilisearch` plugin out of the box. To enable search you will need to enable the feature flag in `./store-config.json`, which you do by changing the config to this:

```json
{
  "features": {
    "search": true
  }
}
```

Before you can search you will need to install the plugin in your Medusa server, for a written guide on how to do this – [see our documentation](https://docs.medusajs.com/add-plugins/meilisearch).

The search components in this starter are developed with Algolia's `react-instant-search-hooks-web` library which should make it possible for you to seemlesly change your search provider to Algoli instead of MeiliSearch.

To do this you will need to add `algoliasearch` to the project, by running

```shell
yarn add algoliasearch
```

After this you will need to switch the current MeiliSearch `SearchClient` out with a Alogolia client. To do this update `@lib/search-client`.

```ts
import algoliasearch from "algoliasearch/lite"

const appId = process.env.NEXT_PUBLIC_SEARCH_APP_ID || "test_app_id" // You should add this to your environment variables

const apiKey = process.env.NEXT_PUBLIC_SEARCH_API_KEY || "test_key"

export const searchClient = algoliasearch(appId, apiKey)

export const SEARCH_INDEX_NAME =
  process.env.NEXT_PUBLIC_INDEX_NAME || "products"
```

After this you will need to set up Algolia with your Medusa server, and then you should be good to go. For a more thorough walkthrough of using Algolia with Medusa – [see our documentation](https://docs.medusajs.com/add-plugins/algolia), and the [documentation for using `react-instantsearch-hooks-web`](https://www.algolia.com/doc/guides/building-search-ui/getting-started/react-hooks/).

# Resources

## Learn more about Medusa

- [Website](https://www.medusa-commerce.com/)
- [GitHub](https://github.com/medusajs)
- [Documentation](https://docs.medusa-commerce.com/)

## Learn more about Next.js

- [Website](https://nextjs.org/)
- [GitHub](https://github.com/vercel/next.js)
- [Documentation](https://nextjs.org/docs)
