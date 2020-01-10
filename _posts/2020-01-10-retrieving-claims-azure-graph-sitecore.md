---
layout: post
title: Retrieving Azure AD claims for Sitecore via Graph API
subtitle :
tags: [Azure, Sitecore, C#]
author: Bon
comments : True
---

Let's go and start fresh with some Azure action! So I've been trying to play around with the AD Graph API to integrate it with Sitecore.

<br>

In this post, I'll be tackling how to retrieve Azure AD claims from Sitecore via Graph API. Claims are needed to get the access token from Azure in order to retrieve data such as the user details. Reading through the [Graph API documentation](https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-reference-tokens#claims-in-id-and-access-tokens), it seems like it is a walk in the park. But it isn't the case when it comes to Sitecore. 

<br>

At first, I had been trying to retrieve the user details from my registered application in the Azure tenant but I failed to do so. You see, Sitecore overrides the claims that I am requesting. This is because the Sitecore security model somehow replaces them. In order to retrieve the claims, you have to access the cookies from the http request as mentioned from this [post](http://blog.baslijten.com/how-to-add-federated-authentication-with-sitecore-and-owin/). 

<br>

