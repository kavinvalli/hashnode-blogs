---
title: "Try using this authentication method in your next NextJS project!! (Hint: Magic Links)"
seoDescription: "Securely enhance NextJS project with Magic Link authentication, a passwordless-alternative that reduces leaks and forgotten passwords"
datePublished: Tue Mar 21 2023 15:31:03 GMT+0000 (Coordinated Universal Time)
cuid: clfiexswk000409mkfxszccra
slug: try-using-this-authentication-method-in-your-next-nextjs-project-hint-magic-links
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679412526052/77a964bf-94f6-4177-a487-419a25aef889.png
tags: authentication, frontend-development, nextjs

---

Looking for a safe and reliable way to authenticate users? Consider implementing magic links. They offer a secure alternative to traditional passwords and can help mitigate the risk of password leaks and forgotten passwords.

Magic Link authentication, also known as Email-only authentication, is a trending method of authentication that has recently gained significant popularity.

## How does it work?

The following steps are involved:

1. The user enters their email.
    
2. If the user doesn't already exist in the database, an account is created.
    
3. A unique verification token is generated.
    
4. The user is sent an email with a link which contains the verification token encoded.
    
5. When the user visits the link, the verification token is cross-checked with the one stored on the database, and the user is authenticated if the token is valid.
    

## Why use Email-only authentication?

Doesn't it seem less secure without passwords? However, if you have access to someone's email, you can access their account. Most websites offer a "forgot password" function that allows you to reset a password with access to an email. So, if a hacker gains access to the email, they can still get into the account.

So, it does appear that email-only authentication (or passwordless authentication) could be more secure as it eliminates the risk of password hacking.

## How to add Email-only authentication to a NextJS project?

You can easily accomplish this by utilizing Next-Auth, which is now referred to as Auth.js. Check out my video tutorial on how to implement it for further information!

%[https://youtu.be/boyVzmMEtFg]