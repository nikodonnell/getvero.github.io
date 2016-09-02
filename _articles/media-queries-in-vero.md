---
title: Using media queries (@media) in Vero
category: email design
layout: articles
getting_started: true
---

# Using Media Queries (@media) in Vero

Vero provides support for media queries in HTML templates, however they must be wrapped in a separate `<style>` element containing the special tag `data-premailer='ignore'`.

    
    <style>
        /** desktop styles go here *//
    </style>

    <style data-premailer='ignore'>      
        /** mobile styles go here e.g. */
        
        @media only screen and (max-width: 620px) {
            width:320px;
        }
        
    </style>
    

## Background

Acheiving visual consistency across email clients is an ongoing challenge for marketers. It can, however, be significantly improved by scoping styles to the exact element they apply to. This is also known as element-level CSS specificity. Unfortunately, this approach does make managing your styles difficult and ultimately defeats the purpose of CSS itself. 

To get around this problem, it has become standard practice for mail platforms to automatically inline CSS contained within the header of an email (styles in between the `<style></style>` elements) to the style tag of the element they apply to (`style=""`).

This approach makes marketer's lives easier as they can style using CSS classes, and email makes email rendering more consistent between clients (Gmail, Outlook, Mail etc.) as every style is hardcoded on the element itself.

In Vero, inlining CSS is included in our pre-mail processes, occurring automatically betweeen the time you click schedule and the time an email leaves our mail servers.

## Ensuring your media queries are not inlined

Naturally, if your media queries are stripped out of the header styles, they will no longer work. To avoid this happening, you must wrap all media queries in a separate `<style>` element containing the special tag `data-premailer='ignore'`.