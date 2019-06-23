---
type: post
title: "Indigo - A Hugo Indiweb Theme - Features"
description: "Indigo is a A Hugo theme, designed with indieweb in mind."
summary: "The following classes are used to mark up the author bio for Indieweb parsing: h-card, u-photo, p-name, u-url, rel=me, p-locality, p-country-name, u-email, p-note. I'll be exploring these classes more thoroughly, soon."
categories: ["indigo"]
tags: ["hugo-indieweb-theme", "indieweb", "hugo","front matter","features","h-card"]
date: "2019-06-22T01:22:33-23:00"
draft: false
slug: /indigo-indieweb-features/

---

Hey!!! So I've been meaning to do this for a while.. and now [Indieweb Summit](https://indieweb.org/2019) is right around the corner. I've been hustling away on some related projects just so I could have something really nice prepared for the event.

I would encourage you to follow along with the associated links. I'm trying to keep this compact, while conveying essential information.

![](https://imgur.com/ZCC07f3.png)

* [AngeloStavrow/indigo](https://github.com/AngeloStavrow/indigo) - The theme of this web-site's home repository.
* [microformats.org](http://microformats.org/)
* [indieweb.org](https://indieweb.org/)
* [indieauth.com](https://indieauth.com/)

Those links are plenty to get started :)

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

## [h-card](http://microformats.org/wiki/h-card)

>h-card is a simple, open format for publishing people and organisations on the web. h-card is one of several open microformat draft standards suitable for embedding data in HTML.
>
>h-card is the microformats2 update to hCard.

* [microformats.org/wiki/h-card](http://microformats.org/wiki/h-card)

Yay! Structured Data! These are the bits that add flavor and context, for the machines we communicate through, to otherwise indistinguishable (to a machine) info.

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


### Indigo h-card

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


### rel=me

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


### Indieauth

<a href="https://indieauth.com"><img src="https://imgur.com/MsoJqzp.png" alt="IndieAuth.com provides an IndieAuth server for your website that authenticates you using your existing social accounts. First you link from your website to one or more authentication providers such as GitHub or a PGP key, then when you enter your domain name in the web sign-in form on websites that support IndieAuth, you can sign in without using a password."></a>

Once you've got the rel=me in there, Indieauth.com will check to see if it has verification methods available.

![](https://indieauth.com/img/code-sample.png)

If it does, then an automated system will take you through, much like logging into any web-service.

## Indigo-Source Deployed

Now I've done some basic configuration and have a few blog, posts up... lets examine the source of a single blog post, to see it in action.

### Endpoints

Here we see a few links identified as 'me', and an authorization end-point:

![](https://imgur.com/MJXJtFn.png)

*From `config.toml`*
```
#https://github.com/kisik21/indigo/commit/e168672487b78bef5070cc0eb70bc5d4e748c707
  [params.endpoints]
  Auth = "https://indieauth.com/auth"
  # To get webmention support, just register at webmention.io and paste the link for endpoint here.
  Webmention = "https://webmention.io/web-work.tools_indieweb_/webmention"
  # To get micropub support, you'll need to install a Micropub endpoint at your site and put its link there.
  # To get an endpoint with Hugo support, use nanopub: https://github.com/dg01d/nanopub
  # It will probably require some PHP hackery though, as it's fairly basic.
  #Micropub = ""
  # To get microsub support, you can use Aperture from p3k. Either go to https://aperture.p3k.io or self-host it (it's open source!)
  #Microsub = ""
```

For the authorization endpoint, that's simple enough. If you've set up your h-card paramaters in the config file, and deployed the site, it should walk you right through, and even guide you if anything is missing.


### h-entry

Ahaaa! Now we're getting to it.  I remember that there was some indieweb code not strictly defined in the documentation for this theme.  Let's check it out!

* [indieweb.org/h-entry](https://indieweb.org/h-entry)

  >h-entry is the microformats2 vocabulary for marking up blog posts on web sites. It can also be used to mark-up any other episodic or time series based content. 

...

  >Adding h-entry to your post pages enables post information [discovery](https://indieweb.org/discovery) on your permalinks, which is useful for a variety of things, including:
  >
  >  - [reply](https://indieweb.org/reply) context syndication
  >  - syndication of your [replies](https://indieweb.org/replies) from your site as comments on the permalinks of the sites that you reply to.
  >
  >Adding h-entry to your home page enables:
  >
  >  - subscribing to your posts directly from your home page (no separate feed needed).
  >  - A building block for adding [PuSH](https://indieweb.org/PuSH) 0.4 support for real time subscribers of your updates
  >
  >Any page with an explicit author and publication date can use h-entry and enables:
  >
  >  - Nicer [link-previews](https://indieweb.org/link-preview), especially with an optional [u-featured](https://indieweb.org/u-featured) image
  >  - For example: W3C specs like [Webmention](https://w3.org/TR/webmention) and [Micropub](https://w3.org/TR/micropub) have their name, editors, publication date all marked up with h-entry.

### [h-entry](http://microformats.org/wiki/h-entry) properties

**The following core h-entry properties have broad consensus and are broadly interoperably published and consumed:**

>* `p-name` - entry name/title
>* `p-summary` - short entry summary
>* `e-content` - full content of the entry
>* `dt-published` - when the entry was published
>* `dt-updated` - when the entry was updated
>* `p-author` - who wrote the entry, optionally embedded h-card(s)
>* `p-category` - entry categories/tags
>* `u-url` - entry permalink URL
>* `u-uid` - universally unique identifier, typically canonical entry URL
>* `p-location` - location the entry was posted from, optionally embed h-card, h-adr, or h-geo
>* `u-syndication` - URL(s) of syndicated copies of this post. The property equivalent of rel-syndication (example)
>* `u-in-reply-to` - the URL which the h-entry is considered reply to (i.e. doesn’t make sense without context, could show up in comment thread), optionally an embedded h-cite (reply-context) (example)
>* `p-rsvp` (enum, use `<data>` element or value-class-pattern)
  > "yes", "no", "maybe", "interested". Case-insensitive values, normalized to lowercase. Examples:
  > ... `<data class="p-rsvp" value="yes">is going</data>` to ..., or
  > ... `<data class="p-rsvp" value="maybe">might go</data>` to ...
  > ... `<data class="p-rsvp" value="no">unable to go</data>` to ...
  > ... `<data class="p-rsvp" value="interested">am interested/tracking/watching</data>` ... 
>* `u-like-of` - the URL which the h-entry is considered a “like” (favorite, star) of. Optionally an embedded h-cite
>* `u-repost-of` - the URL which the h-entry is considered a “repost” of. Optionally an embedded h-cite. 

Similar to h-card, our h-entry has a number of potential properties.

### Indigo Article Source

```
<article class="h-entry">
  <header>
      <h1 class="post-title p-name">FreeNode IRC #indieweb-dev on IIW RWoT and DID&#39;s</h1>
           
      <p class="post-date">Posted on
          <time class="dt-published" datetime="2019-06-03T11:22:33-23:00">
          3 June, 2019 at 11:22 -2300
          </time>  by <a href="https://web-work.tools/indieweb/" class="p-author h-card" rel="author">Infominer</a>
      </p>
            
      <p class="post-tag">Category: 
                
        <a href="https://web-work.tools/indieweb/categories/decentralized-identity" class="post-tag p-category">decentralized-identity</a>
                
        <a href="https://web-work.tools/indieweb/categories/resources" class="post-tag p-category">resources</a></p>

      <hr class="post-underline">
          
  </header>
```

The article is marked with the `h-entry` class, and then we have:

>* `p-name` - entry name/title
>* `dt-published` - when the entry was published
>* `p-category` - entry categories/tags
>* `p-author h-card rel="author"`

That last combo is interesting. Like mentioned earlier, the p-author is found as part of the h-card class. 

Perhaps its significant that this `h-card` is found within the `h-entry`... I'm just figuring this out as we go along.

### e-content

>* e-content - full content of the entry 

```  
  <section class="content e-content">
```

{{ content }} (not copyin the whole post here :)

All our tags marked with p-category:

```
  </section>
  <footer>
    <a class="permalink u-url" href="https://web-work.tools/indieweb/indieweb-dev-on-did/">🔗</a>
            
    <hr class="post-underline">
    <p class="post-tag">Tags for this post: 
            
    <a href="https://web-work.tools/indieweb/tags/indieweb" class="post-tag p-category">indieweb</a>
            
    <a href="https://web-work.tools/indieweb/tags/did" class="post-tag p-category">did</a>
            
    <a href="https://web-work.tools/indieweb/tags/rwot" class="post-tag p-category">rwot</a>
            
    <a href="https://web-work.tools/indieweb/tags/indieweb-dev" class="post-tag p-category">indieweb-dev</a>
            
    <a href="https://web-work.tools/indieweb/tags/freenode" class="post-tag p-category">freenode</a></p>
            
  </footer>
    </article>
</div>
```

Finally the `h-card`, in our footer, Lovely.

```    
    <div class="h-card">
      <img class="u-photo" src="https://web-work.tools/indieweb/images/infominer.svg" />
      <div class="card-content">
        <h2 class="card-name"><a class="p-name u-url" href="https://web-work.tools/indieweb/" rel="me">Infominer</a></h2>
        <p class="card-subhead">
          <span class="p-locality">Mehtab Bagh</span>,
          <span class="p-country-name">49 6e 64 75 73</span><br />
          <a class="u-email" href="mailto:infominer@protonmail.com">Email me</a>
        </p>
      </div>
      <p class="p-note">Full-Time Crypto-Curation and Histories ⧉ Bitcoin, Blockchain, DecentralizedID ⧉ Research, Publishing, WebWork, Indieweb ⧉ her/him</p>
    </div>
```

Check out [layouts/_default/single.html](https://github.com/AngeloStavrow/indigo/blob/master/layouts/_default/single.html) to see what it looks like before its built.


## Be Back Soon

I'll have more on this and everything else, shortly.