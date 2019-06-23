---
type: post
title: "Indigo - A Hugo Indiweb Theme - Features"
date: 2019-06-22T11:22:33-23:00
draft: false
categories: ["indigo"]
tags: ["hugo-indieweb-theme", "indieweb", "hugo","front matter","features","h-card"]
slug: /indigo-authors/
summary: "The following classes are used to mark up the author bio for Indieweb parsing: h-card, u-photo, p-name, u-url, rel=me, p-locality, p-country-name, u-email, p-note. I'll be exploring these classes more thoroughly, soon."

---

Hey!!! So I've been meaning to do this for a while.. and now [Indieweb Summit](https://indieweb.org/2019) is right around the corner. I've been hustling away on some related projects just so I could have something really nice prepared for the event.

I would encourage you to follow along with the associated links. I'm going to try and keep this compact, but convey essential information as an overview.

## Setting up the author bio

A set of configuration options are used for displaying the biography.

```
[params]
  Author = "Author Name"
  Avatar = "images/site-logo.svg"
  Biography = "A short description, a few sentences describing the author. Set
               the 'ShowBio' parameter to false to hide this."
  ShowBio = true        

[params.indieWeb]  
    EmailAddress = "email.address@example.com"
    Country = "CountryName"
    City = "CityName"
```

Specifics on each setting item are as follows:

- `Author`: Your name; this is the site author name.
- `Avatar`: The path to your profile picture. By default, it will show the theme's logo (`/static/images/site-logo.svg`).
- `Biography`: Hopefully the placeholder text here is self-explanatory; add a couple of short sentences about yourself here.
- `ShowBio`: If you prefer not to show the author bio, set this to `false`. By default, it's set to `true`.
- `EmailAddress`: The email address at which you can be contacted.
- `Country`: The name of the country in which you live.
- `City`: The name of the city in which you live.

![](https://imgur.com/GO6ub1u.png)

## IndieWeb features

Filling out these settings makes your site more machine readable, and to communicate specific items of information to other sites you wish to interact with.

As you can see above, the following microformats are related to who we are. These are simple way of identifying ourselves to other sites. This way, when we want to communicate, there's no need to think about sending over our avatar, it's already prepared in our web-site.

>The following classes are used to mark up the author bio for [IndieWeb][indieweb] parsing:

| Element         | Class                       |
| :-------------- | :-------------------------- |
| The author card | `h-card`                    |
| Profile picture | `u-photo`                   |
| Author URL*     | `p-name`, `u-url`, `rel=me` |
| City            | `p-locality`                |
| Country         | `p-country-name`            |
| Email address   | `u-email`                   |
| Biography       | `p-note`                    |

*Author URL is set to the site's base URL.

[indieweb]: https://indieweb.org

Lets explore each of these, and what it does.

### [h-card](http://microformats.org/wiki/h-card)

>h-card is a simple, open format for publishing people and organisations on the web. h-card is one of several open microformat draft standards suitable for embedding data in HTML.
>
>h-card is the microformats2 update to hCard.

* [microformats.org/wiki/h-card](http://microformats.org/wiki/h-card)

Yay! Structured Data! These are the bits that add flavor and context, for the machines we communicate through, to otherwise indistinguishable code.

> The class h-card is a root class name that indicates the presence of an h-card.
>
>For minimal examples where at most p-name, u-url and u-photo are required (such as the first given above), only the root class name is needed — see [implied properties](http://microformats.org/wiki/microformats-2-implied-properties).


Basically, it seems that the h-card is the root for the rest of the data-structure's we're reviewing.

If find one in the wild, an h-card will b nearby.

### h-card properties

So you can see, the idea is to give people and organizations a variety of ways to identify themselves.

>h-card properties, inside an element with class h-card:
>
>* p-name - The full/formatted name of the person or organization
>* p-honorific-prefix - e.g. Mrs., Mr. or Dr.
>* p-given-name - given (often first) name
>* p-additional-name - other (e.g. middle) name
>* p-family-name - family (often last) name
>* p-sort-string - string to sort by
>* p-honorific-suffix - e.g. Ph.D, Esq.
>* p-nickname - nickname/alias/handle
>* u-email - email address
>* u-logo - a logo representing the person or organization (e.g. a face icon)
>* u-photo - a photo of the person or organization
>* u-url - home page or other URL representing the person or organization
>* u-uid - universally unique identifier, preferably canonical URL
>* p-category - category/tag
>* p-adr - postal address, optionally embed an h-adr
>* Main article: h-adr
>* p-post-office-box - post office box description if any
>* p-extended-address - apartment/suite/room name/number if any
>* p-street-address - street number + name
>* p-locality - city/town/village
>* p-region - state/county/province
>* p-postal-code - postal code, e.g. US ZIP
>* p-country-name - country name
>* p-label
>* p-geo or u-geo, optionally embed an h-geo
>* Main article: h-geo
>* p-latitude - decimal latitude
>* p-longitude - decimal longitude
>* p-altitude - decimal altitude
>* p-tel - telephone number
>* p-note - additional notes
>* dt-bday - birth date
>* u-key - cryptographic public key e.g. SSH or GPG
>* p-org - affiliated organization, optionally embed an h-card
>* p-job-title - job title, previously 'title' in hCard, disambiguated.
>* p-role - description of role
>* u-impp per RFC4770, new in vCard4 (RFC 6350)
>* p-sex - biological sex, new in vCard4 (RFC 6350)
>* p-gender-identity - gender identity, new in vCard4 (RFC 6350)
>* dt-anniversary


### Built In Features:

The author card - `h-card`
Profile picture - `u-photo` 
City            - `p-locality`
Country         - `p-country-name`
Email address   - `u-email`
Biography       - `p-note` - additional notes
Author URL:
  - `p-name` - The full/formatted name of the person or organization
  - `u-url` - home page or other URL representing the person or organization
  - `rel=me`


## rel=me

* [microformats.org/wiki/rel-me](http://microformats.org/wiki/rel-me)

>XFN 1.1 introduced the "me" rel value which is used to indicate profile equivalence and for [identity-consolidation](http://microformats.org/wiki/identity-consolidation).
  >Identity consolidation is the ability for a user to indicate that one or more identities, profiles, URLs across different sites all represent that same user. Also known as: profile aggregation, profile equivalency.

This is how we state "this is me". If your website has a series of social media icons that connect people to you on different platforms, I would drop a rel=me into each of those links..

This is how I did it on another site:


```
    {% if site.footer.links %}
      {% for link in site.footer.links %}
        {% if link.label and link.url %}
          <li><a href="{{ link.url }}" rel="me"><i class="{{ link.icon | default: 'fas fa-link' }}" aria-hidden="true"></i> {{ link.label }}</a></li>
        {% endif %}
      {% endfor %}
    {% endif %}
```

All I had to do was put the `rel="me"` into the url like so `<a href="{{ link.url }} rel="me">link txt</a>`.

Don't mind the scripting language... if that bothers you.. think of it like this:

```
<a href="https://infominer.id" rel="me">infominer.id</a>
```

Now I set that in my template, I've identified all of the social profiles (and e-mail) that I link to as belonging to me :D

**But wait!** You say...

Yes, even though you've used 'u=email' to identify your e-mail address, it's the links with rel=me that sites will look to for authentication. You might notice, if you follow a number of "getting started" guides that you've been placing various properties everywhere, and it can seem a bit redundant at times.

However, each has its own purpose... 


## Indieauth

<a href="https://indieauth.com"><img src="https://imgur.com/MsoJqzp.png" alt="IndieAuth.com provides an IndieAuth server for your website that authenticates you using your existing social accounts. First you link from your website to one or more authentication providers such as GitHub or a PGP key, then when you enter your domain name in the web sign-in form on websites that support IndieAuth, you can sign in without using a password."></a>

Once you've got the rel=me in there, Indieauth.com will check to see if it has verification methods available.

![](https://indieauth.com/img/code-sample.png)

If it does, then an automated system will take you through, much like logging into any web-service.

## Be Back Soon

I'll have more on this and everything else, shortly.