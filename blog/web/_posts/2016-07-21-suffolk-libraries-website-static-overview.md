---
layout: post
title: How we built a static Suffolk Libraries website (an overview)
category: web
---

After lots and lots of work and a painful propagation period we've got a new [Suffolk Libraries](https://www.suffolklibraries.co.uk) site up and running (by we I mean me and the excellent [Emma Raindle](https://twitter.com/emmaraindle), who will be sorely missed at Suffolk Libraries when she leaves next week).

I'll maybe write a lot more about it over the next few weeks, but here's a summary of what we've built (which is, if nothing else, different from any other library website).

## Our set up

- We use Jekyll to build a set of static HTML, CSS and javascript files (AKA a _website_). Jekyll uses a potent mix of HTML, CSS, Markdown, CSV, YAML and Liquid to magic up the site.
- We use Tachyons and Pure CSS (and a sprinkling of our own)
- We push code to three [Github repo](https://github.com/suffolklibraries/sljekyll) branches (dev/staging/master)
- We use [Netlify](https://netlify.com) to host the site. Netlify links our production and staging sites to two of our Github branches. That means when we `git push` to these branches our websites get updated.
- Netlify provides some smart dynamic features, including redirects, emailed form submissions and, even better, Zapier integration. That means we can automatically build our site at 1am every morning, send email notifications in response to form submissions and add those submissions to Google sheets.
- We also get free, one click `https` (from Let's Encrypt)

## Why oh Why

- A faster site. The combination of static HTML and Netlify's hosting (with Cloudfront's CDN) makes the site feel really zippy.
- A more robust site. No database calls, plugins or WordPress updates. No 500 internal server errors.
- A more secure site. No database or scripting to hack into.
- Flexible Jekyll data. Categorised recurrent events, categorised special events, library data; we've only really scratched the possibilities.
- Great workflow. Github &rarr; Netlify makes versioning, backups and deployment simple.

## Todo

- Rewrite Google Maps javascript. At the moment it's adding ~600k to map pages.
- Add data for mobile libraries and research resources.
- Improve event finding.
- Docs

We're happy with it. Let's see if it makes much difference to our feedback and analytics.
