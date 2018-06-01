
## Live site

**[View the live site running from this code here.](http://mootmeijer.com)**


# [Start Bootstrap - Agency](https://startbootstrap.com/template-overviews/agency/)

I based this site off of [Agency](https://startbootstrap.com/template-overviews/agency/), a one page agency portfolio theme for [Bootstrap](http://getbootstrap.com/) created by [Start Bootstrap](http://startbootstrap.com/). This theme features several content sections, a responsive portfolio grid with hover effects, full page portfolio item modals, a responsive timeline, and a working PHP contact form.

I didn't end up using all of the features provided by the theme, but my site is pretty substantially based from it.

## Copyright and License

The original code I used was Copyright 2013-2018 Blackrock Digital LLC. Code released under the [MIT](https://github.com/BlackrockDigital/startbootstrap-agency/blob/gh-pages/LICENSE) license. 
This license is really permissive, and so I'm also releasing it under the same MIT license. 

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/sjmeijer/mootmeijer/master/LICENSE)

## About

Start Bootstrap is an open source library of free Bootstrap templates and themes. All of the free templates and themes on Start Bootstrap are released under the MIT license, which means you can use them for any purpose, even for commercial projects.

* https://startbootstrap.com
* https://twitter.com/SBootstrap

Start Bootstrap was created by and is maintained by **[David Miller](http://davidmiller.io/)**, Owner of [Blackrock Digital](http://blackrockdigital.io/).

* http://davidmiller.io
* https://twitter.com/davidmillerskt
* https://github.com/davidtmiller

Start Bootstrap is based on the [Bootstrap](http://getbootstrap.com/) framework created by [Mark Otto](https://twitter.com/mdo) and [Jacob Thorton](https://twitter.com/fat).

# Notes about getting the site actually set up

## Domain

I decided to purchase the domain from our [evil overlord Google](https://domains.google.com), since they have a nice simple $12/yr private domain with an easy famliar interface. It also seems like they update the DNS records quickly, being the nexus of the internet. 

## Hosting

You're looking at it. I decided that such a simple site didn't need any fancy hosting, so I just pushed it all to a github repo and in the repo settings, I set it to point to mootmeijer.com. 

In the google DNS record settings, I added in two types of "custom resource records":

> Name 	Type	TTL	Data
> @	A	1m	185.199.108.153
> 			185.199.109.153
> 			185.199.110.153
> 			185.199.111.153
> 	
> www	CNAME	1m	sjmeijer.github.io.

I guess the @ name points to the root of my site (mootmeijer.com). The 4x IPs are the github pages name servers. Since I had already told github my repo should point to mootmeijer.com, I guess that works.
The www CNAME just lets either the apex or www point to the same site


In order to change the color scheme, I had to update the CSS. 
The CSS is actually translated from SCSS, and compiled in CSS. This can be accomplished with:

1. Installing sass:
`sudo gem install sass --no-user-install`

2. Tell sass to watch for changes in the SCSS folder and compile it into CSS in the right folder
`sass --watch scss:css`

3. Then this makes a css/agency.css file, which still needs to be translated into a minified css/agency.min.css, which I just did using https://cssminifier.com/

4. Alternately, I can minify it all at once with:
`sass --watch scss/agency.scss:css/agency.css --watch css/agency.css:css/agency.min.css --style compressed --scss`
