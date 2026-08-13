# 🤯 HEAD

> A simple guide to HTML `<head>` elements
> HTML-ის `<head>` ელემენტების მარტივი გზამკვლევი

[![Contributors](https://img.shields.io/github/contributors/joshbuchea/head.svg?style=for-the-badge)](https://github.com/joshbuchea/HEAD/graphs/contributors)
[![CC0](https://img.shields.io/badge/license-CC0-green.svg?style=for-the-badge)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Follow @joshbuchea on Mastodon](https://img.shields.io/badge/Follow_@joshbuchea-purple?logo=mastodon&logoColor=white&style=for-the-badge)](https://hachyderm.io/@joshbuchea)

## Table of Contents
## სარჩევი

- [Recommended Minimum](#recommended-minimum)
- [Elements](#elements)
- [Recommended Order](#recommended-order)
- [Meta](#meta)
- [Link](#link)
- [Scripts](#scripts)
- [Icons](#icons)
- [Social](#social)
  - [Open Graph](#open-graph)
  - [Schema.org](#schemaorg)
  - [Google JSON-LD Schema](#google-json-ld-schema)
  - [Pinterest](#pinterest)
  - [OEmbed](#oembed)
  - [QQ/Wechat](#qqwechat)
  - [Dublin Core](#dublin-core)
  - [Fediverse](#fediverse)
- [Browsers / Platforms](#browsers--platforms)
  - [Apple iOS](#apple-ios)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
- [Browsers (Chinese)](#browsers-chinese)
  - [360 Browser](#360-browser)
  - [QQ Mobile Browser](#qq-mobile-browser)
  - [UC Mobile Browser](#uc-mobile-browser)
- [App Links](#app-links)
- [Deprecated](#deprecated)
- [Other Resources](#other-resources)
- [Related Projects](#related-projects)
- [Translations](#-translations)
- [Contributing](#-contributing)
  - [Guide](#guide)
- [Contributors](#-contributors)
- [Author](#-author)
- [Support](#-support)
- [License](#-license)

## Recommended Minimum
## რეკომენდებული მინიმუმი

Below are the essential elements for any web document (websites/apps):
ქვემოთ მოცემულია არსებითი ელემენტები ნებისმიერი ვებ დოკუმენტისათვის (ვებსაიტებისთვის/აპებისთვის):

```html
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!--
  The above 2 meta tags should come as early as possible in the <head>
  to consistently ensure proper document rendering.
  Any other head element should come *after* these tags.
-->
<!--
  ზემოთ მოცემული ორი მეტა ტეგი <head>-ში რაც შეიძლება ადრე უნდა განთავსდეს,
  რათა დავრწმუნდეთ, რომ დოკუმენტი სათანადოდ აისახება (დარენდერდება).
  ნებისმიერი სხვა head-ელემენტი უნდა განთავსდეს ამ ტეგების *შემდეგ*.
-->
<title>Page Title</title>
<title>გვერდის სათაური</title>
```

`meta charset` - defines the encoding of the website, `utf-8` is the standard
`meta charset` - განსაზღვრავს ვებსაიტის კოდირებას[^1]; `utf-8` გახლავთ სტანდარტი

`meta name="viewport"` - viewport settings related to mobile responsiveness
`meta name="viewport"` - ხედვის არეალის[^2] პარამეტრები; მობილურთან თავსებადობის ხარისხზე ზემოქმედებს

`width=device-width` - use the physical width of the device (great for mobile!)
`width=device-width` - მოწყობილობის ფიზიკური სიგანის გამოყენება (შესანიშნავია მობილურებისთვის!)

`initial-scale=1` - the initial zoom, 1 means no zoom
`initial-scale=1` - საწყისი ზუმირება[^3]; 1 აღნიშნავს ზუმირების არარსებობას

## Elements
## ელემენტები

Valid `<head>` elements include `meta`, `link`, `title`, `style`, `script`, `noscript`, and `base`.
მოქმედ `<head>` ელემენტებს წარმოადგენენ: `meta`, `link`, `title`, `style`, `script`, `noscript` და `base`.

These elements provide information for how a document should be perceived, and rendered, by web technologies. e.g. browsers, search engines, bots, etc.
აღნიშნული ელემენტები იძლევიან ინფორმაციას იმის შესახებ, თუ როგორ უნდა იქნეს დოკუმენტი აღქმული და ასახული ვებტექნოლოგიების (მაგ.: ბრაუზერების, საძიებო სისტემების, ბოტების და ა.შ.) მიერ.

```html
<!--
  Set the character encoding for this document, so that
  all characters within the UTF-8 space (such as emoji)
  are rendered correctly.
-->
<!--
  განვსაზღვროთ სიმბოლოთა კოდირება ამ კონკრეტული დოკუმენტისთვის, რათა
  დავრწმუნდეთ, რომ UTF-8-ის ფარგლებში არსებული ყოველი სიმბოლოს (როგორიცაა ემოჯი)
  ასახვა სწორად მოხდება.
-->
<meta charset="utf-8">

<!-- Set the document's title -->
<!-- განვსაზღვროთ დოკუმენტის სათაური -->
<title>Page Title</title>

<!-- Set the base URL for all relative URLs within the document -->
<!-- განვსაზღვროთ ბაზისური URL, დოკუმენტში არსებული ყოველი URL-სთვის -->
<base href="https://example.com/page.html">

<!-- Link to an external CSS file -->
<!-- გარე CSS -->
<link rel="stylesheet" href="styles.css">

<!-- Used for adding in-document CSS -->
<!-- დოკუმენტის შიდა CSS -->
<style>
  /* ... */
</style>

<!-- JavaScript & No-JavaScript tags -->
<!-- JavaScript & No-JavaScript ტეგები -->
<script src="script.js"></script>
<script>
  // function(s) go here
  // ფუნქცია(ები) დაიწერება აქ
</script>
<noscript>
  <!-- No JS alternative -->
  <!-- ალტერნატიული კოდი იმ შემთხვევისთვის, როცა JS ხელმისაწვდომი არ არის -->
</noscript>
```

## Recommended Order
## რეკომენდებული თანმიმდევრობა

The following is the recommended order of elements in the `<head>` for best performance and correct document rendering:
ქვემოთ მოცემულია `<head>`-ში ელემენტების განთავსების რეკომენდებული თანმიმდევრობა საუკეთესო წარმადობისა და დოკუმენტის სწორად ასახვისათვის:

1. `<meta charset>` — Character encoding declaration; **must** appear within the first 1024 bytes of the document
1. `<meta charset>` — სიმბოლოთა კოდირების დეკლარაცია; **აუცილებლად** უნდა განთავსდეს დოკუმენტის პირველი 1024 ბაიტის ფარგლებში
2. `<meta name="viewport">` — Viewport settings; declare early to ensure correct responsive rendering
2. `<meta name="viewport">` — ხედვის არეალის პარამეტრები; განათავსეთ დოკუმენტის თავში, რათა უზრუნველყოთ ეკრანის ზომებთან თავსებადი სწორი ასახვა
3. `<title>` — Document title; placed after encoding/viewport to prevent potential re-rendering
3. `<title>` — დოკუმენტის სათაური; თავსდება კოდირებისა და ხედვის არეალის შემდეგ, რათა თავიდან იქნეს აცილებული შესაძლო ხელახალი ასახვა
4. Other `<meta>` tags (description, robots, etc.)
4. სხვა `<meta>` ტეგები (description, robots და ა.შ.)
5. Open Graph / Social meta tags
5. Open Graph / სოციალურ ქსელებთან დაკავშირებული მეტა ტეგები
6. `<link rel="canonical">` and other `<link>` tags (excluding stylesheets and resource hints)
6. `<link rel="canonical">` და სხვა `<link>` ტეგები (გარდა სტილის კასკადური ცხრილებისა[^4] და რესურსების მინიშნებების[^5])
7. `<link rel="preconnect">` / `<link rel="dns-prefetch">` — Resource hints; early to maximize their value
7. `<link rel="preconnect">` / `<link rel="dns-prefetch">` — რესურსების მინიშნებები; მაქსიმალური ეფექტურობისთვის განათავსეთ რაც შეიძლება ადრე
8. `<link rel="stylesheet">` — External CSS; stylesheets should come before scripts
8. `<link rel="stylesheet">` — გარე CSS; სტილის კასკადური ცხრილები სკრიპტებზე ადრე უნდა განთავსდეს
9. `<link rel="icon">` — Favicons
9. `<link rel="icon">` — საიტის ხატულები[^6]
10. `<script>` — Scripts; use `defer` or `async` where possible to avoid blocking rendering
10. `<script>` — სკრიპტები[^7]; შეძლებისდაგვარად გამოიყენეთ `defer` ან `async` [ატრიბუტები], რათა არ დაიბლოკოს ასახვა

```html
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Page Title</title>

  <meta name="description" content="Page description">
  <!-- other meta tags -->
  <!-- სხვა მეტა ტეგები -->

  <!-- Open Graph / Social meta tags -->
  <!-- Open Graph / სოციალურ ქსელებთან დაკავშირებული მეტა ტეგები -->
  <meta property="og:title" content="Page Title">
  <!-- other social meta tags -->
  <!-- სოციალურ ქსელებთან დაკავშირებული სხვა მეტა ტეგები -->

  <link rel="canonical" href="https://example.com/page.html">
  <!-- other link tags (excluding stylesheets and resource hints) -->
  <!-- სხვა link ტეგები (გარდა სტილის კასკადური ცხრილებისა და რესურსების მინიშნებების) -->

  <link rel="preconnect" href="https://example.com">
  <link rel="dns-prefetch" href="https://example.com">

  <link rel="stylesheet" href="styles.css">

  <link rel="icon" href="favicon.ico">

  <script defer src="script.js"></script>
</head>
```

## Meta
## მეტა

```html
<!--
  The following 2 meta tags should come as early as possible in the <head>
  to consistently ensure proper document rendering.
  Any other head element should come *after* these tags.
-->
<!--
  ქვემოთ მოცემული ორი მეტა ტეგი <head>-ში რაც შეიძლება ადრე უნდა განთავსდეს,
  რათა დავრწმუნდეთ, რომ დოკუმენტი სათანადოდ აისახება (დარენდერდება).
  ნებისმიერი სხვა head ელემენტი უნდა განთავსდეს ამ ტეგების *შემდეგ*.
-->
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">

<!--
  Allows control over where resources are loaded from.
  Place as early in the <head> as possible, as the tag
  only applies to resources that are declared after it.
-->
<!--
  საშუალებას გვაძლევს, ვაკონტროლოთ, თუ საიდან მოხდება რესურსების ჩატვირთვა.
  განათავსეთ <head>-ში რაც შეიძლება ადრე, ვინაიდან აღნიშნული ტეგი
  ვრცელდება მხოლოდ მის შემდგომ დეკლარირებულ რესურსებზე.
-->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">

<!-- Name of web application (only should be used if the website is used as an app) -->
<!-- ვებაპლიკაციის სახელი (უნდა განისაზღვროს მხოლოდ იმ შემთხვევაში, თუკი აღნიშნული ვებსაიტი გამოიყენება, როგორც აპლიკაცია) -->
<meta name="application-name" content="Application Name">

<!-- Theme Color for Chrome, Firefox OS and Opera -->
<!-- თემის ფერი Chrome-სთვის, Firefox OS-სთვის და Opera-სთვის -->
<meta name="theme-color" content="#4285f4">

<!-- Indicates the supported color schemes for the page (light, dark, or both) -->
<!-- მიუთითებს ვებგვერდის მიერ მხარდაჭერილ ფერთა სქემებს (ნათელი, მუქი ან ორივე) -->
<meta name="color-scheme" content="light dark">

<!-- Short description of the document (limit to 150 characters) -->
<!-- დოკუმენტის მოკლე აღწერა (მაქსიმალური სიგრძე: 150 სიმბოლო) -->
<!-- This content *may* be used as a part of search engine results. -->
<!-- აღნიშნული შინაარსი *შესაძლოა* გამოყენებულ იქნეს საძიებო სისტემის მიერ. -->
<meta name="description" content="A description of the page">

<!-- Control the behavior of search engine crawling and indexing -->
<!-- აკონტროლებს საძიებო სისტემის ქცევას ძიებისას და ინდექსირებისას -->
<meta name="robots" content="index,follow"><!-- All Search Engines --><!-- ყველა საძიებო სისტემა -->
<meta name="googlebot" content="index,follow"><!-- Google Specific --><!-- კონკრეტულად Google -->

<!-- Tells Google not to show the sitelinks search box -->
<!-- ეუბნება Google-ს, რომ ძიების შედეგებში არ აჩვენოს საიტის შიდა საძიებო ველი -->
<meta name="google" content="nositelinkssearchbox">

<!-- Tells Google not to provide a translation for this document -->
<!-- ეუბნება Google-ს, რომ არ უზრუნველყოს თარგმანი აღნიშნული დოკუმენტისთვის -->
<meta name="google" content="notranslate">

<!-- Verify website ownership -->
<!-- ვებსაიტის მფლობელობის დამოწმება -->
<meta name="google-site-verification" content="verification_token"><!-- Google Search Console -->
<meta name="yandex-verification" content="verification_token"><!-- Yandex Webmasters -->
<meta name="msvalidate.01" content="verification_token"><!-- Bing Webmaster Center -->
<meta name="p:domain_verify" content="code_from_pinterest"><!-- Pinterest Console-->
<meta name="norton-safeweb-site-verification" content="norton_code"><!-- Norton Safe Web -->

<!-- Identify the software used to build the document (i.e. - WordPress, Dreamweaver) -->
<!-- დოკუმენტის ასაგებად გამოყენებული პროგრამული უზრუნველყოფის იდენტიფიცირება (მაგ.: WordPress, Dreamweaver) -->
<meta name="generator" content="program">

<!-- Short description of your document's subject -->
<!-- დოკუმენტის შინაარსობრივი ნაწილის მოკლე აღწერა -->
<meta name="subject" content="your document's subject">

<!-- Gives a general age rating based on the document's content -->
<!-- დოკუმენტის შიგთავსზე დაყრდნობით განსაზღვრავს ზოგად ასაკობრივ შეფასებას -->
<meta name="rating" content="General">

<!-- Allows control over how referrer information is passed -->
<!-- საშუალებას გვაძლევს, ვაკონტროლოთ, თუ როგორ გადაიცემა ინფორმაცია წყარო გვერდის (referrer) შესახებ -->
<meta name="referrer" content="no-referrer">

<!-- Disable automatic detection and formatting of possible phone numbers -->
<!-- თიშავს შესაძლო სატელეფონო ნომრების ავტომატურ ამოცნობასა და ფორმატირებას -->
<meta name="format-detection" content="telephone=no">

<!-- Geo tags -->
<!-- გეო ტეგები -->
<meta name="ICBM" content="latitude, longitude"><!-- Geographic coordinates (latitude, longitude) in decimal degrees; eg. content="48.8566, 2.3522" --><!-- გეოგრაფიული კოორდინატები (განედი, გრძედი) ათწილადი გრადუსებით; მაგ.: content="48.8566, 2.3522" -->
<meta name="geo.position" content="latitude;longitude"><!-- Geographic coordinates; latitude and longitude are separated by a semicolon --><!-- გეოგრაფიული კოორდინატები; განედი და გრძედი ერთმანეთისგან გამოყოფილია წერტილ-მძიმით -->
<meta name="geo.region" content="country[-state]"><!-- Country code (ISO 3166-1): mandatory, state code (ISO 3166-2): optional; eg. content="US" / content="US-NY" --><!-- ქვეყნის კოდი (ISO 3166-1): სავალდებულო, შტატის კოდი (ISO 3166-2): არასავალდებულო; მაგ.: content="US" / content="US-NY" -->
<meta name="geo.placename" content="city/town"><!-- eg. content="New York City" --><!-- მაგ.: content="New York City" -->

<!-- Web Monetization https://webmonetization.org/docs/getting-started -->
<!-- ვებ მონეტიზაცია https://webmonetization.org/docs/getting-started -->
<meta name="monetization" content="$paymentpointer.example">
```

**Note:** Geo tags are **not** used by browsers directly — they are intended for search engines, web crawlers, and location-based services to understand the geographic relevance of a page's content. `ICBM` (named after the military ICBM address convention) and `geo.position` both express coordinates in decimal degrees; `ICBM` uses a comma separator while `geo.position` uses a semicolon. `geo.region` identifies the country (and optionally the state/region) using ISO codes, and `geo.placename` provides a human-readable place name.
**შენიშვნა:** გეო ტეგებს ბრაუზერები უშუალოდ **არ** იყენებენ — ისინი განკუთვნილია საძიებო სისტემებისთვის, ვებ კროულერებისთვის[^8] და მდებარეობაზე დაფუძნებული სერვისებისთვის, რათა მათ შეძლონ გვერდის შიგთავსის გეოგრაფიული რელევანტურობის განსაზღვრა. `ICBM` (სახელწოდება მომდინარეობს სამხედრო ICBM მისამართების კონვენციიდან) და `geo.position` — ორივე გამოხატავს კოორდინატებს ათწილადი გრადუსებით; `ICBM` გამყოფად იყენებს მძიმეს, ხოლო `geo.position` — წერტილ-მძიმეს. `geo.region` ISO კოდების მეშვეობით განსაზღვრავს ქვეყანას (და, სურვილისამებრ, შტატს/რეგიონს), ხოლო `geo.placename` გვაწვდის ადგილმდებარეობის ადამიანისთვის წაკითხვად სახელწოდებას.

- 📖 [Meta tags that Google understands](https://developers.google.com/search/docs/crawling-indexing/special-tags?hl=en)
- 📖 [WHATWG Wiki: MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions)
- 📖 [ICBM on Wikipedia](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- 📖 [Geotagging on Wikipedia](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

## Link
## ბმული (Link)

```html
<!-- Points to an external stylesheet -->
<!-- მიუთითებს გარე სტილის კასკადურ ცხრილზე (CSS ფაილზე) -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- Helps prevent duplicate content issues -->
<!-- გვეხმარება შიგთავსის დუბლირებასთან დაკავშირებული პრობლემების თავიდან აცილებაში -->
<link rel="canonical" href="https://example.com/article/?page=2">

<!-- Links to a Web App Manifest — the recommended way to define PWA metadata such as app name, icons, theme_color, and display mode -->
<!-- მიუთითებს Web App Manifest-ზე — ესაა PWA მეტამონაცემების (როგორიცაა აპლიკაციის სახელი, ხატულები, theme_color და ჩვენების რეჟიმი) განსაზღვრის რეკომენდებული გზა -->
<link rel="manifest" href="manifest.json">

<!-- Links to information about the author(s) of the document -->
<!-- მიუთითებს ინფორმაციას დოკუმენტის ავტორის (ან ავტორების) შესახებ -->
<link rel="author" href="humans.txt">

<!-- Refers to a copyright statement that applies to the link's context -->
<!-- მიუთითებს საავტორო უფლებების განცხადებაზე, რომელიც ვრცელდება ბმულის კონტექსტზე -->
<link rel="license" href="copyright.html">

<!-- Gives a reference to a location in your document that may be in another language -->
<!-- იძლევა მითითებას დოკუმენტის იმ ვერსიის მისამართის შესახებ, რომელიც შეიცავს იგივე შინაარსს ალტერნატიულ ენაზე -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- Provides information about an author or another person
     Used for RelMeAuth, a distributed form of identity verification.
     See https://microformats.org/wiki/RelMeAuth to learn more -->
<!-- გვაწვდის ინფორმაციას ავტორის ან სხვა პირის შესახებ.
     გამოიყენება RelMeAuth-ისთვის — ვინაობის დამოწმების მიზნით.
     დამატებითი ინფორმაციისთვის იხილეთ https://microformats.org/wiki/RelMeAuth -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- Provides a self reference - useful when the document has multiple possible references -->
<!-- გვაწვდის მითითებას საკუთარ თავზე — გამოსადეგია, როცა დოკუმენტს რამდენიმე შესაძლო მისამართი აქვს -->
<link rel="self" type="application/atom+xml" href="https://example.com/atom.xml">

<!-- The previous, and next documents in a series of documents, respectively -->
<!-- დოკუმენტთა მიმდევრობაში, შესაბამისად, წინა და შემდეგი დოკუმენტები -->
<link rel="prev" href="https://example.com/article/?page=1">
<link rel="next" href="https://example.com/article/?page=3">

<!-- Notifies a URL when you link to it on your document
     More information at https://webmention.net -->
<!-- აცნობებს URL-ს, როცა თქვენს დოკუმენტში მასზე ბმულს განათავსებთ.
     დამატებითი ინფორმაცია: https://webmention.net -->
<link rel="webmention" href="https://example.com/webmention">

<!-- Enables posting to your own domain using a Micropub client 
     More information at https://indieweb.org/Micropub -->
<!-- საშუალებას გვაძლევს, გამოვაქვეყნოთ პოსტები საკუთარ დომენზე Micropub კლიენტის გამოყენებით.
     დამატებითი ინფორმაცია: https://indieweb.org/Micropub -->
<link rel="micropub" href="https://example.com/micropub">

<!-- Enables you to use your site with IndieAuth, an identity solution that
     lets you authenticate with your domain name.
     Read more at https://indieauth.net. -->
<!-- საშუალებას გვაძლევს, ჩვენი საიტი გამოიყენოთ IndieAuth-თან (ვინაობის დადგენის გადაწყვეტილება) ერთად,
     რომელიც ავთენტიფიკაციის გავლის საშუალებას გაძლევთ საკუთარი დომენის სახელით.
     დამატებითი ინფორმაცია: https://indieauth.net -->
<link rel="token_endpoint" href="https://example.com/token">
<link rel="authorization_endpoint" href="https://example.com/auth">

<!-- Open Search -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Search Title">

<!-- Feeds -->
<!-- არხები (Feeds) -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- Prefetching, preloading, prebrowsing -->
<!-- რესურსების წინასწარი ჩატვირთვა (Prefetching, preloading, prebrowsing) -->
<!-- More info: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<!-- დამატებითი ინფორმაცია: https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">

<link rel="preload" href="image.png" as="image">
```

**Note:** The [Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest) (`manifest.json`) is the recommended, cross-platform way to declare installable web app properties — including `name`, `icons`, `theme_color`, and `display` mode — in a single file, instead of relying on multiple platform-specific `<meta>` tags.
**შენიშვნა:** [Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest) (`manifest.json`) გახლავთ დაინსტალირებადი ვებაპლიკაციის თვისებების — მათ შორის `name`, `icons` (ხატულები[^9]), `theme_color` და `display` რეჟიმის — ერთ ფაილში გამოცხადების რეკომენდებული, პლატფორმათაშორისი გზა, ნაცვლად იმისა, რომ დავეყრდნოთ კონკრეტული პლატფორმებისთვის განკუთვნილ მრავალ `<meta>` ტეგს.

- 📖 [Link Relations](https://www.iana.org/assignments/link-relations/link-relations.xhtml)
- 📖 [Web App Manifest (MDN)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest)

## Scripts
## სკრიპტები

```html
<!--
  Scripts: place <script> tags at the end of <body> when possible.
  The following attributes control loading behavior when placed in <head>:
-->
<!--
  სკრიპტები: შეძლებისდაგვარად <script> ტეგები განათავსეთ <body>-ის ბოლოში.
  ქვემოთ მოცემული ატრიბუტები აკონტროლებენ ჩატვირთვის ქცევას <head>-ში განთავსებისას:
-->

<!-- Blocks HTML parsing and content rendering until the script is fetched and executed -->
<!-- ბლოკავს HTML-ის დამუშავებას (parsing) და შიგთავსის ასახვას, ვიდრე სკრიპტი არ ჩამოიტვირთება და შესრულდება -->
<script src="script.js"></script>

<!-- The script will be fetched in parallel with parsing and executed as soon as it is available (before parsing completes) -->
<!-- სკრიპტი ჩამოიტვირთება დამუშავების პარალელურად და შესრულდება ხელმისაწვდომობისთანავე (დამუშავების დასრულებამდე) -->
<script async src="script.js"></script>

<!-- The script will be fetched in parallel with parsing and executed when the page has finished parsing -->
<!-- სკრიპტი ჩამოიტვირთება დამუშავების პარალელურად და შესრულდება მაშინ, როცა გვერდის დამუშავება დასრულდება -->
<script defer src="script.js"></script>

<!-- async takes precedence in modern browsers; defer acts as a fallback for older browsers that don't support async -->
<!-- თანამედროვე ბრაუზერებში უპირატესობა ენიჭება async-ს; defer წარმოადგენს სათადარიგო ვარიანტს ძველი ბრაუზერებისთვის, რომლებსაც async-ის მხარდაჭერა არ გააჩნიათ -->
<script async defer src="script.js"></script>

<!-- Inline script -->
<!-- დოკუმენტის შიდა სკრიპტი -->
<script>
  // function(s) go here
  // ფუნქცია (ან ფუნქციები) დაიწერება აქ
</script>

<!-- Subresource Integrity (SRI): use the integrity attribute to verify that the fetched resource has been delivered without unexpected manipulation -->
<!-- Subresource Integrity (SRI): გამოიყენეთ integrity ატრიბუტი, რათა გადაამოწმოთ, რომ ჩამოტვირთული რესურსი მოწოდებულია არასასურველი მანიპულაციების გარეშე -->
<script src="https://example.com/script.js" integrity="sha384-oqVuAfXRKap7fdgcCY5uykM6+R9GqQ8K/uxy9rx7HNQlGYl1kPzQho1wx4JwY8wC"></script>
```

- 📖 [async vs defer attributes](https://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html)
- 📖 [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Defenses/Subresource_Integrity)

## Icons
## ხატულები

```html
<!-- For IE 10 and below -->
<!-- IE 10-ისა და უფრო ძველი ვერსიებისთვის -->
<!-- Place favicon.ico in the root directory - no tag necessary -->
<!-- განათავსეთ favicon.ico ძირეულ (root) დირექტორიაში - ტეგი არ არის საჭირო -->

<!-- Icon in the highest resolution we need it for -->
<!-- ხატულა იმ უმაღლესი გარჩევადობით, რომლითაც იგი გვჭირდება -->
<link rel="icon" sizes="192x192" href="/path/to/icon.png">

<!-- Apple Touch Icon (reuse 192px icon.png) -->
<!-- Apple Touch Icon (გამოიყენეთ იგივე 192-პიქსელიანი icon.png) -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">
```

- 📖 [All About Favicons (And Touch Icons)](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- 📖 [Favicon Cheat Sheet](https://github.com/audreyfeldroy/favicon-cheat-sheet)
- 📖 [Icons & Browser Colors](https://web.dev/articles/icons-and-browser-colors)

## Social

### Open Graph

> The [Open Graph protocol](https://ogp.me/) is the de facto standard for controlling how your content appears when shared on social platforms. Originally created by Facebook, it's now consumed by most major platforms — including LinkedIn, X (as a fallback when Twitter Card tags are absent), Discord, Slack, iMessage, Mastodon, Bluesky, and WhatsApp.

```html
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Content Title">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:image:alt" content="A description of what is in the image (not a caption)">
<meta property="og:description" content="Description Here">
<meta property="og:site_name" content="Site Name">
<meta property="og:locale" content="en_US">
<meta property="article:author" content="">
```

- 📖 [Open Graph protocol](https://ogp.me/)
- 🛠 Test your page with the [Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/) or the [LinkedIn Post Inspector](https://www.linkedin.com/post-inspector/)

### Schema.org

```html
<html lang="" itemscope itemtype="https://schema.org/Article">
    <head>
      <link rel="author" href="">
      <link rel="publisher" href="">
      <meta itemprop="name" content="Content Title">
      <meta itemprop="description" content="Content description less than 200 characters">
      <meta itemprop="image" content="https://example.com/image.jpg">
```

**Note:** These meta tags require the `itemscope` and `itemtype` attributes to be added to the `<html>` tag.

- 📖 [Getting Started - schema.org](https://schema.org/docs/gs.html)
- 🛠 Test your page with the [Rich Results Test](https://search.google.com/test/rich-results)

### Google JSON-LD Schema

The following is used by Google to help provide your site with a knowledge graph result when someone Googles you (this is the pane to the right of the search results that typically appears for larger brands):

```html
<script type="application/ld+json">
  {
    "@context": "http://schema.org",
    "@type": "Organization",
    "name": "yourbrand.com",
    "url": "https://www.yourbrand.com/",
    "logo": "https://www.yourbrand.com/logo.png",
    "sameAs": [
      "https://www.facebook.com/yourbrand",
      "https://twitter.com/yourbrand",
      "https://uk.pinterest.com/yourbrand/",
      "https://www.instagram.com/yourbrand/",
      "https://www.linkedin.com/company/yourbrand-com"
    ]
  }
</script>
```

### Pinterest

Pinterest lets you prevent people from saving things from your website, according [to their help center](https://help.pinterest.com/en/business/article/prevent-saves-to-pinterest-from-your-site). The `description` is optional.

```html
<meta name="pinterest" content="nopin" description="Sorry, you can't save from my website!">
```

### OEmbed

```html
<link rel="alternate" type="application/json+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="https://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- 📖 [oEmbed format](https://oembed.com/)

### QQ/Wechat

Users share web pages to qq wechat will have a formatted message

```html
<meta itemprop="name" content="share title">
<meta itemprop="image" content="http://imgcache.qq.com/qqshow/ac/v4/global/logo.png">
<meta name="description" itemprop="description" content="share content">
```

- 📖 [Code Format Docs](https://open.mobile.qq.com/api/mqq/index#api:setShareInfo)

### Dublin Core

[Dublin Core](https://www.dublincore.org/) is a metadata vocabulary standardized as [ISO 15836](https://www.iso.org/standard/71339.html) and maintained by the Dublin Core Metadata Initiative (DCMI). It defines fifteen core elements for describing resources and is widely used in digital libraries, institutional repositories, academic publishing, and government portals. To use Dublin Core in HTML, declare the DC namespace and then add the desired elements as `<meta>` tags with a `DC.` prefix.

```html
<!-- Declare the Dublin Core namespace -->
<link rel="schema.DC" href="https://purl.org/dc/elements/1.1/">

<meta name="DC.title" content="Page Title">
<meta name="DC.creator" content="Author Name">
<meta name="DC.subject" content="Keywords; Topics">
<meta name="DC.description" content="A brief description of the page content">
<meta name="DC.publisher" content="Publisher Name">
<meta name="DC.contributor" content="Contributor Name">
<meta name="DC.date" content="YYYY-MM-DD">
<meta name="DC.type" content="Text">
<meta name="DC.format" content="text/html">
<meta name="DC.identifier" content="https://example.com/page.html">
<meta name="DC.source" content="https://example.com/original-source">
<meta name="DC.language" content="en">
<meta name="DC.relation" content="https://example.com/related">
<meta name="DC.coverage" content="Spatial or temporal coverage">
<meta name="DC.rights" content="Copyright Owner Name">
```

- 📖 [Dublin Core Metadata Element Set](https://www.dublincore.org/specifications/dublin-core/dces/)
- 📖 [Using Dublin Core in HTML](https://www.dublincore.org/specifications/dublin-core/dcq-html/)

### Fediverse

Some Fediverse software such as Mastodon allow you to put your Fediverse handle in a meta tag which will show up in embeds to your website. In addition to the tag you will also need to add your domain to the list of allowed websites in "Settings -> Public profile -> Verification -> Author attribution" (for Mastodon).

```html
<meta name="fediverse:creator" content="@handle@example.org">
```

## Browsers / Platforms

### Apple iOS

```html
<!-- Smart App Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- Disable automatic detection and formatting of possible phone numbers -->
<meta name="format-detection" content="telephone=no">

<!-- Launch Icon (180x180px or larger) -->
<link rel="apple-touch-icon" href="/path/to/apple-touch-icon.png">

<!-- Launch Screen Image -->
<link rel="apple-touch-startup-image" href="/path/to/launch.png">

<!-- Launch Icon Title -->
<meta name="apple-mobile-web-app-title" content="App Title">

<!-- Enable standalone (full-screen) mode -->
<meta name="mobile-web-app-capable" content="yes">

<!-- Status bar appearance (has no effect unless standalone mode is enabled) -->
<meta name="apple-mobile-web-app-status-bar-style" content="black">

<!-- Viewport fit for notched phones (iPhone X and later); add viewport-fit=cover to your existing viewport meta tag -->
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">

<!-- iOS app deep linking -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- 📖 [Configuring Web Applications](https://developer.apple.com/library/archive/documentation/AppleApplications/Reference/SafariWebContent/ConfiguringWebApplications/ConfiguringWebApplications.html)

**Note:** Properties such as app title (`apple-mobile-web-app-title`), standalone/display mode, and app icons (`apple-touch-icon`) are more reliably and portably configured using the [Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest) (`<link rel="manifest">`), which is the recommended approach for Progressive Web Apps (PWAs). The Apple-specific meta tags remain useful as a fallback for older iOS versions.

### Google Android

```html
<meta name="theme-color" content="#E64545">

<!-- Add to home screen -->
<meta name="mobile-web-app-capable" content="yes">
<!-- More info: https://developer.chrome.com/multidevice/android/installtohomescreen -->

<!-- Android app deep linking -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

**Note:** `theme-color` and the "add to home screen" / standalone behavior are better defined using the [Web App Manifest](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Manifest) (`<link rel="manifest">`). The `theme-color` meta tag can still serve as a fallback for browsers that do not yet support the manifest `theme_color` property.

### Google Chrome

```html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- Disable translation prompt -->
<meta name="google" content="notranslate">
```

## Browsers (Chinese)

### 360 Browser

```html
<!-- Select rendering engine order -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ Mobile Browser

```html
<!-- Locks the screen into the specified orientation -->
<meta name="x5-orientation" content="landscape/portrait">

<!-- Display this document in fullscreen -->
<meta name="x5-fullscreen" content="true">

<!-- Document will be displayed in "application mode" (fullscreen, etc.) -->
<meta name="x5-page-mode" content="app">
```

### UC Mobile Browser

```html
<!-- Locks the screen into the specified orientation -->
<meta name="screen-orientation" content="landscape/portrait">

<!-- Display this document in fullscreen -->
<meta name="full-screen" content="yes">

<!-- UC browser will display images even if in "text mode" -->
<meta name="imagemode" content="force">

<!-- Document will be displayed in "application mode"(fullscreen, forbidding gesture, etc.) -->
<meta name="browsermode" content="application">

<!-- Disabled the UC browser's "night mode" for this document -->
<meta name="nightmode" content="disable">

<!-- Simplify the document to reduce data transfer -->
<meta name="layoutmode" content="fitscreen">

<!-- Disable the UC browser's feature of "scaling font up when there are many words in this document" -->
<meta name="wap-font-scale" content="no">
```

- 📖 [UC Browser Docs](https://www.uc.cn/download/UCBrowser_U3_API.doc)

## App Links

```html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">

<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">

<!-- Web fall back -->
<meta property="al:web:url" content="https://applinks.org/documentation">
```

- 📖 [App Links](https://developers.facebook.com/docs/applinks)

## Deprecated

For tags and elements that were once part of this guide but are no longer supported (Internet Explorer compatibility, Safari Pinned Tabs, Alexa verification, etc.), see [DEPRECATED.md](https://github.com/joshbuchea/HEAD/blob/master/DEPRECATED.md).

## Other Resources

- 📖 [HTML5 Boilerplate Docs: The HTML](https://github.com/h5bp/html5-boilerplate/blob/main/docs/html.md)
- 📖 [HTML5 Boilerplate Docs: Extend and customize](https://github.com/h5bp/html5-boilerplate/blob/main/docs/extend.md)

## Related Projects

- [Atom HTML Head Snippets](https://github.com/joshbuchea/atom-html-head-snippets) - Atom package for `HEAD` snippets
- [Sublime Text HTML Head Snippets](https://github.com/marcobiedermann/sublime-head-snippets) - Sublime Text package for `HEAD` snippets
- [head-it](https://github.com/hemanth/head-it) - CLI interface for `HEAD` snippets
- [vue-head](https://github.com/ktquez/vue-head) - Manipulating the meta information of the `HEAD` tag for Vue.js

## 🌐 Translations

- [Bahasa](https://github.com/rijdz/HEAD)
- [Bengali](https://github.com/AveyBD/HEAD)
- [Brazilian Portuguese](https://github.com/Webschool-io/HEAD)
- [Chinese (Simplified)](https://github.com/Amery2010/HEAD)
- [German](https://github.com/Shidigital/HEAD)
- [Italian](https://github.com/Fakkio/HEAD)
- [Japanese](https://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- [Korean](https://github.com/Lutece/HEAD)
- [Malay](https://github.com/shoen1x/HEAD)
- [Russian/Русский](https://github.com/Konfuze/HEAD)
- [Spanish](https://github.com/alvaroadlf/HEAD)
- [Turkish/Türkçe](https://github.com/mkg0/HEAD)
- [Ukrainian](https://github.com/Shramkoweb/HEAD)

## 🤝 Contributing

**Open an issue or a pull request to suggest changes or additions.**

### Guide

The **HEAD** repository consists of two branches:

#### 1. `master`

This branch consists of the `README.md` file that is reflected on the [htmlhead.dev](https://htmlhead.dev/) website. All changes to the content of the guide should be made in this file.

Please follow these steps for pull requests:

{:.list-style-default}

- Modify only one tag, or one related set of tags at a time
- Use double quotes on attributes
- Don't include a trailing slash in self-closing elements — the HTML5 spec says they're optional
- Consider including a link to documentation that supports your change

#### 2. `gh-pages`

This branch is responsible for the [htmlhead.dev](https://htmlhead.dev/) website. We use [Jekyll](https://jekyllrb.com/) to deploy the `README.md` markdown file to [GitHub Pages](https://pages.github.com/). All website related modifications should be made in this branch.

You may find it helpful to review the [Jekyll Docs](https://jekyllrb.com/docs/home/) and understand how Jekyll works before working in this branch.

## 🌟 Contributors

Check out all the super awesome [contributors](https://github.com/joshbuchea/HEAD/graphs/contributors) 🤩

## 👤 Author

**Josh Buchea**

- GitHub: [@joshbuchea](https://github.com/joshbuchea)
- Mastodon: [@joshbuchea@hachyderm.io](https://hachyderm.io/@joshbuchea)

## 💛 Support

If this project was helpful for you or your organization, please considering supporting my work directly:

- 💛 [Sponsor me on GitHub](https://github.com/sponsors/joshbuchea)
- ⭐️ [Star this project on GitHub](https://github.com/joshbuchea/HEAD)
- 🐙 [Follow me on GitHub](https://github.com/joshbuchea)
- 🐘 [Follow me on Mastodon](https://hachyderm.io/@joshbuchea)

Everything helps, thanks! 🙏

— Josh

## 📝 License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

[^1]:
    სიგნალის ან მონაცემების გადასაცემად ვარგის ფორმატში გადაყვანა (ინგლ.: Encoding)
[^2]:
    (ინგლ.: Viewport)
[^3]:
    კადრის / გამოსახულების სწრაფი გადიდება (ინგლ.: Zoom)
[^4]:
    ტექნოლოგია, რომელიც გამოიყენება მოსანიშნ ენაზე, მაგ.: HTML დოკუმენტის იერსახისა და ფორმატირების აღსაწერად; აბრევ. CSS (ინგლ.: Stylesheets)
[^5]:
    (ინგლ.: Resource hints)
[^6]:
    (ინგლ.: Favicons)
[^7]:
    მცირე პროგრამა / ტექსტური ფაილი, რომელიც შეიცავს სხვა პროგრამისთვის შესასრულებელ ბრძანებებს (ინგლ.: Script)
[^8]:
    საძიებო რობოტი, საძიებო აგენტი, „ობობა“ (სპეციალური კომპიუტერული პროგრამა, რომელიც ინტერნეტში ავტომატურად აგროვებს და ახარისხებს ინფორმაციას, ახდენს ვებსაიტების ინდექსაციას და მისთ.; აგრ. web crawler, spider).
[^9]:
    მცირე ზომის სიმბოლური გამოსახულება ეკრანზე ამა თუ იმ პროგრამის, ფოლდერის და ა.შ. ამოსარჩევად (ინგლ.: Icon)
