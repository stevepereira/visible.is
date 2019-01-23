---
title: The Building Blocks of Gatsby
date: 2018-11-20 00:00:00 +0000
menu:
  guides:
    name: Building Blocks
    parent: Developing with Gatsby
    identifier: gatsby-building-blocks
    weight: 3
draft: true

---


{{% warning "Currently in Beta" %}}

Support for Gatsby in Forestry is currently in closed beta, but you can [follow us on Twitter](https://twitter.com/forestryio/) or [join our community Slack](/blog/join-our-slack-community/) to be the first to know when Gatsby support becomes available for everyone!
{{% /warning %}}

For developers accustomed to Jekyll and Hugo, Gatsby will present a bit of a learning curve. This is in part because, unlike those two static site generators, Gatsby aims at a broader purpose. Gatsby is a highly-configurable tool that can generate a static frontend from a variety of different content sources.

If you want a markdown-based site similar to what you would create with Jekyll or Hugo, you will need to jump through a few hoops. To better understand how to do it, it will help to examine a few of the **building blocks** of a Gatsby site.

{{% tip %}}
This document provides a high-level overview of a few Gatsby concepts. For a practical example of how these building blocks work together, take a look at our [guide to using Markdown in Gatsby](/docs/guides/developing-with-gatsby/markdown/).
{{% /tip %}}

## Plugins

In Gatsby, **plugins** are standalone packages that hook into the **Gatsby lifecycle** to modify its behavior. To add a plugin to your Gatsby project, install it via NPM or Yarn and then add the name of the plugin to the `plugins` section of your `gatsby-config.js` file.

{{% tip "Further Reading" %}}
If you want to learn more about Gatsby's lifecycle and how you can hook into it, [this blog post from Dennis Brotzky](https://medium.com/narative/understanding-gatsbys-lifecycle-31c473ba2f2d) is a great introduction.
{{% /tip %}}

## GraphQL

GraphQL is the primary interface for working with content in Gatsby. Content gets dumped into GraphQL, where it can be queried and converted into pages. While it's possible to [build a Gatsby site without using GraphQL](https://www.gatsbyjs.org/docs/using-gatsby-without-graphql/), you're better off using it in most cases.

{{% tip "GraphQL Resources" %}}
- [How To GraphQL](https://www.howtographql.com/)
- [Data in Gatsby](https://www.gatsbyjs.org/tutorial/part-four/)
{{% /tip %}}

## Sourcing And Transforming Content

One of Gatsby's biggest strengths is its ability to aggregate content from different sources. These sources could be files, databases, or data from an API. In order to incorporate this content into your site, it must first be exposed to GraphQL via a **source plugin**.

Even content from your local filesystem needs to be exposed via a source plugin (in which case you'd use `gatsby-source-filesystem`.)

### Transforming File Nodes

When sourcing content from local files, they will be exposed to GraphQL as file nodes. This can give you some metadata like the path to the file and its creation time, but in order to use the file's data in GraphQL you will need a **transformer plugin** to process it.

For example, `gatsby-transformer-json` will take the data in a JSON file and make it queryable via Gatsby's GraphQL interface.

{{% tip "Further Reading" %}}
[Gatsby: Sourcing Content and Data](https://www.gatsbyjs.org/docs/content-and-data/)
{{% /tip %}}

## Generating Pages For Your Site

Once your content is available via GraphQL, you can hook into Gatsby's build process to create pages from it. Gatsby exposes several API hooks that can be implemented in the `gatsby-node.js` file, including the `createPages` function.

{{% tip "Further Reading" %}}
[Gatsby: Programmatically Create Pages From Data](https://www.gatsbyjs.org/tutorial/part-seven/)
{{% /tip %}}

## Building Pages With React Components

In Gatsby, a page is just a React component. When you generate pages with `createPage`, you pass in the path to a `.js` file containing a React component. This component will serve as your template.

{{% tip "Further Reading" %}}
[Gatsby: Building With Components](https://www.gatsbyjs.org/tutorial/part-one/#building-with-components)
{{% /tip %}}