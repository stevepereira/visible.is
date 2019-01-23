---
title: Gatsby's Project Structure
date: 2018-11-20 00:00:00 +0000
menu:
  guides:
    name: Project Structure
    parent: Developing with Gatsby
    identifier: gatsby-project-structure
    weight: 5
draft: true

---

A bare-bones Gatsby project might look something like this:

```
/
├── plugins/
├── public/
├── src/
    └── pages/
    └── templates/
    └── html.js
├── static/
├── gatsby-config.js
├── gatsby-node.js
├── gatsby-ssr.js
├── gatsby-browser.js

```

## _plugins/_

You can use the `plugins` directory to store local Gatsby plugins. While Gatsby recommends installing plugins through NPM, using plugins stored in the `plugins` directory can be convenient while developing or testing a new plugin.

## _public/_

By default, Gatsby will build your site to the `public` directory.

## _src/_

The `src` directory is a convention in Gatsby and is where you should put the content and layout files that will compose your website. However, you can place these files anywhere as long as you reference the correct paths when sourcing your content and calling components.

## _static/_

Files in the `static` directory will be copied to the corresponding path in the generated HTML files.

## _gatsby-config.js_

The `gatsby-config.js` file is where you will configure Gatsby, defining site-wide metadata and defining which plugins your site uses.

{{% tip "Further Reading" %}}
[Gatsby: Gatsby Config](https://www.gatsbyjs.org/docs/gatsby-config/)
{{% /tip %}}

## Hooking in to Gatsby

Gatsby provides three files that allow you to plug in your own code and customize Gatsby: `gatsby-node.js`, `gatsby-ssr.js`, and `gatsby-browser.js`.

### _gatsby-node.js_

In the `gatsby-node.js`, you can use Gatsby's Node APIs to customize what happens when your site is generated. This is how, for example, you can create pages from Markdown files.

{{% tip "Further Reading" %}}
[Gatsby: Node APIs](https://www.gatsbyjs.org/docs/node-apis/)
{{% /tip %}}

### _gatsby-ssr.js_

Use `gatsby-ssr.js` to utilize any of Gatsby's server rendering APIs.

{{% tip "Further Reading" %}}
[Gatsby: SSR APIs](https://www.gatsbyjs.org/docs/ssr-apis/)
{{% /tip %}}

### _gatsby-browser.js_

In `gatsby-browser.js` you can use Gatsby's browser APIs to write client-side JavaScript code.

{{% tip "Further Reading" %}}
[Gatsby: Browser APIs](https://www.gatsbyjs.org/docs/browser-apis/)
{{% /tip %}}