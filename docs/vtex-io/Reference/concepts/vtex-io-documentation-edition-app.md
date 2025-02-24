---
title: "Edition App"
slug: "vtex-io-documentation-edition-app"
excerpt: "Learn what Edition Apps are and how they can streamline the setup of specific VTEX accounts."
hidden: false
createdAt: "2020-06-03T16:02:44.317Z"
updatedAt: "2022-12-13T20:17:44.705Z"
---

An Edition App represents a bundle of settings, policies, backend and frontend apps that are encapsulated into a single app. These apps are created and exported by a [Sponsor Account](https://developers.vtex.com/docs/guides/vtex-io-documentation-sponsor-account), with the main objective of streamlining the installation of multiple apps essential to quickly set up a specific group of accounts.

![EditionApp](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-io-documentation-edition-app.png)

## List of native Edition Apps

The `vtex` account currently provides the following native Edition Apps:

- Edition Store (`vtex.edition-store@5.x`) - installs all the necessary apps to develop a store with the [Store Framework](https://developers.vtex.com/docs/guides/getting-started-3).
- Edition Business (`vtex.edition-business@0.x`) - installs all the necessary apps to build a store with the [Legacy CMS Portal](https://help.vtex.com/en/tracks/cms--2YcpgIljVaLVQYMzxQbc3z/6OCY6S9tqBXPD5mgpbBInC).

If you are interested in creating your own Edition App, please refer to the [Developing an Edition app](#developing-an-edition-app) section.

## Changing the Edition App of an account

To change the Edition App installed in an account, you are required to [open a support ticket](https://help-tickets.vtex.com/smartlink/sso/login/zendesk). This process is crucial to prevent potential critical issues that could arise from misconfiguration.

## Developing an Edition app

Any VTEX account that meets the [requirements needed to be a Sponsor Account](https://developers.vtex.com/docs/guides/vtex-io-documentation-becoming-a-sponsor-account) can develop and release its own Edition Apps. This capability is particularly valuable for complex account families, such as those under the same brand or holding.

A Sponsor Account can extend a native `vtex` Edition App by creating a new customized version that caters to the specific needs of its account family.

For more detailed instructions on developing an Edition App, please refer to the [Developing an Edition App](https://developers.vtex.com/docs/guides/vtex-io-documentation-configuring-an-edition-app) guide.

### Dependencies and inherited apps

All Edition apps must depend, either directly or indirectly, on either `vtex.edition-business` or `vtex.edition-store`.

Apps included as [`dependencies`](https://developers.vtex.com/docs/guides/vtex-io-documentation-dependencies) within an Edition App are considered inherited apps. Moreover, all apps bundled within an Edition App must share the same [`vendor`](https://developers.vtex.com/docs/guides/vtex-io-documentation-manifest) as the Edition App itself.

It's important to note that Sponsored Accounts cannot modify apps and configurations installed through an Edition App. Only the Sponsor Account has the authority to make changes by releasing a new version of its Edition App and requesting a reinstallation.
