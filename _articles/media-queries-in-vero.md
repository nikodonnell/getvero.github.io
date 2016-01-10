---
layout: articles
title:  Using media queries (@media) in Vero
categories: email design
getting_started: true
---

# Using Media Queries (@media) in Vero

Vero provides support for media queries in HTML templates, however they must be wrapped with a in a separate `<style>` element containing the special tag `data-premailer='ignore'`.

    
    <style>
        /** desktop styles go here *//
    </style>

    <style data-premailer='ignore'>      
        /** mobile styles go here e.g. */
        
        @media only screen and (max-width: 620px) {
        }
        
    </style>
    

##Background

Acheiving visual consistency across email clients is difficult, but can be significantly improved through element-level CSS specificity. In email, styles should ideally be scoped to the `style="..."` tag of each individual element they apply to. This, of course, makes managing your styles difficult and ultimately defeats the purpose of CSS itself.

To get around this problem, it has become standard practice for mail platforms to automatically inline CSS contained within the header of an email (in between the `<style></style>` elements) to the style (`style=""`)tag of the element they apply to.

In Vero, inlining CSS is included in our pre-mail processes—taking place betweeen the time you click schedule and the time an email leaves our mail servers.

##Ensuring your media queries are not inlined

Naturally, if your media queries are stripped out of the header styles, they will no longer work. To avoid this happening, you must wrap all media queries in a separate `<style>` element containing the special tag `data-premailer='ignore'`.