# ⚠️ Deprecated `<head>` Elements
# ⚠️ მოძველებული `<head>` ელემენტები

> Tags and elements that were once part of the [HEAD](./README.md) guide but are now deprecated, obsolete, or otherwise no longer supported by the platforms/vendors they targeted.
> ტეგები და ელემენტები, რომლებიც ოდესღაც [HEAD](./README.md) გზამკვლევის ნაწილს წარმოადგენდნენ, თუმცა ახლა მოძველებულია, ამოღებულია ან უბრალოდ აღარ არის მხარდაჭერილი იმ პლატფორმების/მწარმოებლების მიერ, რომლებსაც ისინი ემსახურებოდნენ.

These are preserved here for historical reference. **Do not use them in new projects.**
აღნიშნული ჩამონათვალი შემონახულია უბრალოდ ისტორიული ცნობის სახით. **ნუ გამოიყენებთ მათ ახალ პროექტებში.**

## Table of Contents
## სარჩევი

- [Microsoft Internet Explorer](#microsoft-internet-explorer)
- [Apple Safari](#apple-safari)
- [Apple iOS](#apple-ios)
- [Link Relations](#link-relations)
- [Resource Hints](#resource-hints)
- [Site Verification](#site-verification)
- [Social](#social)
- [Miscellaneous](#miscellaneous)

## Microsoft Internet Explorer

Internet Explorer was [retired by Microsoft on June 15, 2022](https://learn.microsoft.com/en-us/lifecycle/announcements/internet-explorer-11-end-of-support-on-windows-10). All IE-specific tags are obsolete.
Internet Explorer [Microsoft-მა მოხმარებიდან ამოიღო 2022 წლის 15 ივნისს](https://learn.microsoft.com/en-us/lifecycle/announcements/internet-explorer-11-end-of-support-on-windows-10). IE-სთვის განკუთვნილი ყველა ტეგი ამჟამად მოძველებულად ითვლება.

```html
<!-- Force IE 8/9/10 to use its latest rendering engine -->
<!-- აიძულებს IE 8/9/10-ს, გამოიყენოს მისი უახლესი ამსახავი ძრავი (rendering engine) -->
<meta http-equiv="x-ua-compatible" content="ie=edge">

<!-- Disable automatic detection and formatting of possible phone numbers by Skype Toolbar browser extension -->
<!-- თიშავს შესაძლო სატელეფონო ნომრების ავტომატურ ამოცნობასა და ფორმატირებას Skype Toolbar ბრაუზერის გაფართოების (extension) მიერ -->
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Windows Tiles -->
<!-- Windows-ის პანელები (Tiles) -->
<meta name="msapplication-config" content="/browserconfig.xml">
```

Minimum required xml markup for `browserconfig.xml`:
მინიმალური საჭირო XML მარკირება `browserconfig.xml`-სთვის:

```xml
<?xml version="1.0" encoding="utf-8"?>
<browserconfig>
   <msapplication>
     <tile>
        <square70x70logo src="small.png"/>
        <square150x150logo src="medium.png"/>
        <wide310x150logo src="wide.png"/>
        <square310x310logo src="large.png"/>
     </tile>
   </msapplication>
</browserconfig>
```

Live tiles were removed from the Windows 11 Start menu and are no longer rendered by Edge.
საინფორმაციო პანელები (Live tiles) ამოღებულ იქნა Windows 11-ის Start მენიუდან და Edge-ის მიერ აღარ ხდება მათი ასახვა (render).

## Apple Safari

```html
<!-- Safari Pinned Tab Icon -->
<!-- Safari-ის მიმაგრებული ჩანართის (Pinned Tab) ხატულა -->
<link rel="mask-icon" href="/path/to/icon.svg" color="blue">
```

Safari Pinned Tabs were removed in Safari 17 (2023); the `mask-icon` link relation is no longer used.
Safari-ის მიმაგრებული ჩანართები (Pinned Tabs) ამოღებულ იქნა Safari 17-ში (2023); `mask-icon` ბმული აღარ გამოიყენება.

## Apple iOS

```html
<!-- Enable standalone (full-screen) mode -->
<!-- რთავს დამოუკიდებელ (standalone / სრულეკრანიან) რეჟიმს -->
<meta name="apple-mobile-web-app-capable" content="yes">
```

As of iOS 17.4, Apple [deprecated `apple-mobile-web-app-capable`](https://developer.apple.com/documentation/safari-release-notes/safari-17_4-release-notes) in favor of the standardized `mobile-web-app-capable`:
iOS 17.4-დან მოყოლებული, Apple-მა [მოძველებულად გამოაცხადა `apple-mobile-web-app-capable`](https://developer.apple.com/documentation/safari-release-notes/safari-17_4-release-notes) სტანდარტიზებული `mobile-web-app-capable`-ის გათვალისწინებით:

```html
<meta name="mobile-web-app-capable" content="yes">
```

## Resource Hints
## რესურსების მინიშნებები

```html
<!-- Prerender a full page in the background -->
<!-- მთლიანი გვერდის წინასწარი ასახვა ფონურ რეჟიმში -->
<link rel="prerender" href="https://example.com/">
```

`<link rel="prerender">` was [deprecated and removed from Chrome](https://developer.chrome.com/blog/prerender-pages) in favor of the [Speculation Rules API](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API).
`<link rel="prerender">` [მოძველებულად გამოცხადდა და ამოღებულ იქნა Chrome-იდან](https://developer.chrome.com/blog/prerender-pages) [Speculation Rules API-ის](https://developer.mozilla.org/en-US/docs/Web/API/Speculation_Rules_API) გათვალისწინებით.

```html
<!-- Completely opt out of DNS prefetching by setting to "off" -->
<!-- სრულად თიშავს DNS-ის წინასწარ ჩატვირთვას „off“ მნიშვნელობის მითითებით -->
<meta http-equiv="x-dns-prefetch-control" content="off">
```

`x-dns-prefetch-control` was a Firefox/IE-era extension that was never implemented in Chromium and is no longer meaningfully consumed by modern browsers. Use `<link rel="dns-prefetch">` for explicit prefetch hints.
`x-dns-prefetch-control` გახლდათ Firefox/IE-ის ეპოქის პროგრამული გაფართოება, რომელიც Chromium-ში არასოდეს განხორციელებულა და თანამედროვე ბრაუზერების მიერ აღარ გამოიყენება. წინასწარი ჩატვირთვის პირდაპირი მოთხოვნისთვის გამოიყენეთ `<link rel="dns-prefetch">`.

## Link Relations
## ბმულის მიმართებები

```html
<!-- Links to an AMP HTML version of the current document -->
<!-- მიუთითებს მიმდინარე დოკუმენტის AMP HTML ვერსიაზე -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">
```

Google [removed the AMP requirement from Top Stories](https://developers.google.com/search/blog/2021/04/more-details-page-experience) in 2021 and the AMP Page Experience signal was retired. The AMP Project itself is largely dormant.
Google-მა 2021 წელს [ამოიღო AMP-ის მოთხოვნა Top Stories-იდან](https://developers.google.com/search/blog/2021/04/more-details-page-experience) და AMP Page Experience სიგნალიც გაუქმდა. თავად AMP პროექტი დიდწილად მიძინებულია.

```html
<!-- Used when a 3rd party service is utilized to maintain a blog -->
<!-- გამოიყენება მაშინ, როცა ბლოგის სამართავად მესამე მხარის სერვისია ჩართული -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- Forms an automated comment when another WordPress blog links to your WordPress blog or post -->
<!-- ქმნის ავტომატურ კომენტარს, როცა სხვა WordPress ბლოგი თქვენს WordPress ბლოგზე ან პოსტზე ბმულს განათავსებს -->
<link rel="pingback" href="https://example.com/xmlrpc.php">
```

[RSD (Really Simple Discoverability)](https://en.wikipedia.org/wiki/Really_Simple_Discovery) was used by XML-RPC blog editors like Windows Live Writer (discontinued in 2017). XML-RPC pingbacks have been [widely disabled by default](https://make.wordpress.org/core/2015/09/30/xml-rpc-settings-in-4-4/) due to their use in DDoS amplification attacks. Use [Webmention](https://www.w3.org/TR/webmention/) instead.
[RSD (Really Simple Discoverability)](https://en.wikipedia.org/wiki/Really_Simple_Discovery) გამოიყენებოდა XML-RPC ბლოგის რედაქტორების მიერ, როგორიცაა Windows Live Writer (განვითარება შეწყდა 2017 წელს). XML-RPC pingback-ები [უმეტესწილად ნაგულისხმევად გათიშულია](https://make.wordpress.org/core/2015/09/30/xml-rpc-settings-in-4-4/), რადგან ისინი DDoS ტიპის კიბერთავდასხმების გასაძლიერებლად გამოიყენებოდა. სანაცვლოდ გამოიყენეთ [Webmention](https://www.w3.org/TR/webmention/).

```html
<!-- Links to a document that describes a collection of records, documents, or other materials of historical interest -->
<!-- მიუთითებს დოკუმენტზე, რომელიც აღწერს ისტორიული მნიშვნელობის ჩანაწერების, დოკუმენტების ან სხვა მასალების ერთობლიობას -->
<link rel="archives" href="https://example.com/archives/">

<!-- Links to top level resource in an hierarchical structure -->
<!-- მიუთითებს იერარქიული სტრუქტურის ზედა დონის რესურსზე -->
<link rel="index" href="https://example.com/article/">
```

Both `archives` and `index` were [removed from the HTML living standard](https://html.spec.whatwg.org/multipage/links.html#linkTypes) and are no longer registered in the [IANA link relations registry](https://www.iana.org/assignments/link-relations/link-relations.xhtml) for HTML.
ორივე — `archives` და `index` — [ამოღებულ იქნა HTML-ის ცოცხალი სტანდარტიდან](https://html.spec.whatwg.org/multipage/links.html#linkTypes) და HTML-ისთვის [IANA-ს ბმულების რეესტრში](https://www.iana.org/assignments/link-relations/link-relations.xhtml) აღარ არის დარეგისტრირებული.

## Site Verification
## საიტის დამოწმება

```html
<meta name="alexaVerifyID" content="verification_token"><!-- Alexa Console -->
```

[Alexa Internet](https://en.wikipedia.org/wiki/Alexa_Internet) (the web traffic analytics service — unrelated to the Amazon Alexa voice assistant) was [shut down by Amazon on May 1, 2022](https://support.alexa.com/hc/en-us/articles/4410503838999).
[Alexa Internet](https://en.wikipedia.org/wiki/Alexa_Internet) (ვებ ტრაფიკის ანალიტიკის სერვისი — არ არის კავშირში Amazon-ის ხმოვან ასისტენტ Alexa-სთან) [Amazon-მა 2022 წლის 1-ელ მაისს დახურა](https://support.alexa.com/hc/en-us/articles/4410503838999).

## Social
## სოციალური ქსელები

```html
<meta name="twitter:card" content="summary">
<meta name="twitter:site" content="@site_account">
<meta name="twitter:creator" content="@individual_account">
<meta name="twitter:url" content="https://example.com/page.html">
<meta name="twitter:title" content="Content Title">
<meta name="twitter:description" content="Content description less than 200 characters">
<meta name="twitter:image" content="https://example.com/image.jpg">
<meta name="twitter:image:alt" content="A text description of the image conveying the essential nature of an image to users who are visually impaired. Maximum 420 characters.">
```

X (formerly Twitter) now falls back to [Open Graph](./README.md#open-graph) tags when `twitter:*` tags are absent, making the dedicated Twitter Card markup redundant for most use cases. The [Twitter Card Validator](https://cards-dev.twitter.com/validator) was retired and the original [Twitter Developers documentation](https://dev.twitter.com/cards/getting-started) is no longer accessible. The tags are still parsed if present, but there's no reason to maintain a separate set alongside Open Graph.
X (ყოფილი Twitter) როდესაც `twitter:*` ტეგები არ არის წარმოდგენილი, [Open Graph](./README.md#open-graph) ტეგებს ეყრდნობა, რაც ცალკე Twitter Card მარკირებას უმეტეს შემთხვევაში ზედმეტს ხდის. [Twitter Card Validator](https://cards-dev.twitter.com/validator) გაუქმდა და ორიგინალი [Twitter Developers დოკუმენტაცია](https://dev.twitter.com/cards/getting-started) აღარ არის ხელმისაწვდომი. ეს ტეგები არსებობის შემთხვევაში კვლავ მუშავდება, თუმცა Open Graph-ის გვერდით მათი ცალკე შენარჩუნების საფუძველი აღარ არსებობს.

```html
<!-- disallow Twitter from using your site's info for personalization purposes -->
<!-- უკრძალავს Twitter-ს თქვენი საიტის ინფორმაციის პერსონალიზაციის მიზნით გამოყენებას -->
<meta name="twitter:dnt" content="on">
```

Twitter's Do Not Track support was effectively dropped following the platform's transition to X. The original [Twitter privacy options documentation](https://dev.twitter.com/web/overview/privacy) is no longer accessible, and the signal is not honored in practice.
Twitter-ის Do Not Track მხარდაჭერა ფაქტობრივად გაუქმდა პლატფორმის X-ად გარდაქმნის შემდეგ. ორიგინალი [Twitter-ის კონფიდენციალურობის პარამეტრების დოკუმენტაცია](https://dev.twitter.com/web/overview/privacy) აღარ არის ხელმისაწვდომი და აღნიშნული სიგნალი პრაქტიკაში აღარ არის გათვალისწინებული.

```html
<meta property="fb:app_id" content="123456789">
```

`fb:app_id` was historically required for Facebook Insights/Domain Insights but is no longer needed for Open Graph sharing. Meta's [current Sharing documentation](https://developers.facebook.com/docs/sharing/webmasters/) does not list it as required, and most Open Graph parsers ignore it.
`fb:app_id` ისტორიულად საჭირო იყო Facebook Insights/Domain Insights-ისთვის, თუმცა Open Graph-ით გაზიარებისთვის იგი აღარ არის აუცილებელი. Meta-ს [გაზიარების მიმდინარე დოკუმენტაცია](https://developers.facebook.com/docs/sharing/webmasters/) მას სავალდებულოდ აღარ მოიხსენიებს და Open Graph-ის პარსერების უმეტესობა მას უგულებელყოფს.

## Miscellaneous
## სხვადასხვა

```html
<!-- Specifies the document to appear in a specific frame -->
<!-- განსაზღვრავს დოკუმენტის კონკრეტულ ჩარჩოში (frame) გამოჩენას -->
<meta http-equiv="Window-Target" content="_value">
```

`Window-Target` was a non-standard, IE-era extension that was never adopted by the HTML standard and is not supported by modern browsers.
`Window-Target` გახლდათ არასტანდარტული, IE-ის ეპოქის პროგრამული გაფართოება, რომელიც HTML სტანდარტს არასოდეს უღიარებია და თანამედროვე ბრაუზერების მიერ მხარდაჭერილი არ არის.
