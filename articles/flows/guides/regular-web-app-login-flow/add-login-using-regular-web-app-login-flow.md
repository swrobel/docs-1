---
description: Learn how to add login to your application using the regular web app login flow.
toc: true
topics:
  - api-authentication
  - oidc
  - authorization-code
contentType: tutorial
useCase:
  - add-login
---
# Add Login Using the Regular Web App Login Flow

<%= include('../../../_includes/_pipeline2') %>

::: note
This tutorial will help you add login to your regular web application using the regular web app login flow. If you want to learn how the flow works and why you should use it, see [Regular Web App Login Flow](/flows/concepts/regular-web-app-login-flow).
:::

Auth0 makes it easy for your app to implement the regular web app login flow using:

* [Auth0 Mobile SDKs](/libraries): The easiest way to implement the regular web app flow, which will do most of the heavy-lifting for you. Our [Regular Web App Quickstarts](/quickstart/webapp) will walk you through the process.
* Authentication API: If you prefer to roll your own, keep reading to learn how to call our API directly.

If you prefer to embed your own login pages within your regular web app, you can implement our login widget (Lock UI) directly into your app with our:

* [Lock v11 for Web](/libraries/lock/v11)

Following successful login, your application will have access to the user's [ID Token](/tokens/id-token) and [Access Token](/tokens/overview-access-tokens). The ID Token will contain basic user profile information, and the Access Token can be used to call the Auth0 /userinfo endpoint or your own protected APIs.

## Prerequisites

This tutorial can be used to add login to your regular web app. If you want to learn to call your API from a regular web app, see [Call My API Using the Regular Web App Login Flow](/flows/guides/regular-web-app-login-flow/call-api-using-regular-web-app-login-flow).

**Before beginning this tutorial:**

* [Register your Application with Auth0](/applications/webapps). 
  * Select an **Application Type** of **Regular Web Apps**.
  * Add an **Allowed Callback URL** of **https://${account.namespace}/callback**.
  * Make sure your Application's **[Grant Types](/applications/application-grant-types#how-to-edit-the-application-s-grant_types-property)** include **Authorization Code**.


## Steps

1. [Authorize the user](#authorize-the-user): 
Request the user's authorization and redirect back to your app with an `authorization_code`.
2. [Request Tokens](#request-tokens): 
Exchange your `authorization_code` for tokens.
3. [Refresh Tokens](#refresh-tokens):
Use a refresh token to request new tokens.

Optional: [Explore Sample Use Cases](#sample-use-cases)


<%= include('./includes/authorize-user-add-login') %>

<%= include('./includes/request-tokens') %>

<%= include('./includes/refresh-tokens') %>

<%= include('./includes/sample-use-cases-add-login') %>


## Keep Reading

::: next-steps
- [Why you should always use Access Tokens to secure APIs](/api-auth/why-use-access-tokens-to-secure-apis)
- [The OAuth 2.0 protocol](/protocols/oauth2)
- [The OpenID Connect protocol](/protocols/oidc)
- [Tokens used by Auth0](/tokens)
:::