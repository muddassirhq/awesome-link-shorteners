# Awesome Link Shorteners [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Link shorteners, link-in-bio pages and app-opener links — hosted and open source — compared on what matters when your links are shared on social media: does the link open properly, or does it get stuck inside Instagram's in-app browser?

Most short links are tapped inside Instagram, TikTok, LinkedIn, Facebook or WhatsApp. Those apps open links in a built-in browser where visitors are logged out, app links (YouTube, Spotify, Amazon) don't open their apps, saved cards are missing and Google sign-in is blocked. The **In-app escape** column marks tools that advertise getting visitors out to their real browser.

**Legend:** ✅ advertised by the vendor · — not advertised (as of October 2026) · 🔓 open source

## Contents

- [Hosted shorteners](#hosted-shorteners)
- [App-opener and in-app escape links](#app-opener-and-in-app-escape-links)
- [Link-in-bio pages](#link-in-bio-pages)
  - [Hosted bio pages](#hosted-bio-pages)
  - [Open-source bio pages](#open-source-bio-pages)
- [Self-hosted open-source shorteners](#self-hosted-open-source-shorteners)
  - [Serverless and static](#serverless-and-static)
- [Commercial self-hosted](#commercial-self-hosted)
- [In-app browsers and short links](#in-app-browsers-and-short-links)
  - [Reading](#reading)
  - [Escape cheat sheet](#escape-cheat-sheet)
  - [Libraries](#libraries)
  - [Testing tools](#testing-tools)
- [Related lists](#related-lists)

## Hosted shorteners

General-purpose shortening services.

| Service | Focus | In-app escape |
|---|---|---|
| [Bitly](https://bitly.com) | Branded links, QR codes, analytics | — |
| [Bl.ink](https://www.bl.ink) | Enterprise branded links | — |
| [Buffer (buff.ly)](https://buffer.com) | Shortening inside a social scheduler | — |
| [Capsulink](https://www.capsulink.com) | Branded links | — |
| [Cuttly](https://cutt.ly) | Free shortener with analytics | — |
| [Dub](https://dub.co) 🔓 | Link attribution and analytics | — |
| [is.gd](https://is.gd) | Free, no account | — |
| [Kutt](https://kutt.to) 🔓 | Hosted instance of Kutt | — |
| [Linkly](https://linklyhq.com) | Link management and retargeting | — |
| [Ow.ly](https://www.hootsuite.com/pages/owly) | Shortening inside Hootsuite | — |
| [Pxl](https://www.pxl.to) | Branded links with pixels | — |
| [Rebrandly](https://rebrandly.com) | Branded domains | — |
| [Replug](https://replug.io) | Branded links with CTAs | — |
| [Short.io](https://short.io) | Branded short links on your domain | — |
| [shorturl.at](https://www.shorturl.at) | Free, no account | — |
| [Spoo.me](https://spoo.me) 🔓 | Free shortener with stats | — |
| [Switchy](https://switchy.io) | Branded links with retargeting | — |
| [T.LY](https://t.ly) | Shortener with browser extensions | — |
| [TinyURL](https://tinyurl.com) | The original free shortener | — |
| [URLR](https://urlr.me/en) | GDPR-focused shortener | — |
| [v.gd](https://v.gd) | Free, no account | — |
| [x.gd](https://x.gd) | Free shortener | — |

## App-opener and in-app escape links

Links built to open the right app (YouTube, Amazon, Spotify) or to leave social in-app browsers.

| Service | Focus | In-app escape |
|---|---|---|
| [BoringOne](https://boringone.page) | TikTok-focused links | ✅ |
| [Bouncy](https://bouncy.ai) | Creator links, 30+ platforms | ✅ |
| [Eden](https://eden.so) | YouTube app links | ✅ (Android) |
| [GeniusLink](https://geniuslink.com) | Retail and app deep links | — |
| [link.boo](https://link.boo) | Creator links to stores and apps | ✅ |
| [LinkMe](https://link.me) | Link-in-bio with deep links | ✅ |
| [Linko](https://linko.me) | Links that leave in-app browsers | ✅ |
| [LinkTwin](https://linktw.in) | Deep links to 100+ apps | — |
| [Lnk.Bio](https://lnk.bio) | Link-in-bio with deep linking | ✅ |
| [Onlynk](https://onlynk.me) | Deep links and in-app browser handling | ✅ |
| [OpeninApp](https://openinapp.com) | App-opening links | — |
| [PlugWith.me](https://plugwith.me) | Links that leave Instagram's browser | ✅ |
| [U2L](https://u2l.ai) | Links that open in the default browser | ✅ |
| [URLgenius](https://urlgeni.us) | App deep links without an SDK | — |
| [WarpLink](https://warplink.app) | Deep links through in-app browsers | ✅ |

## Link-in-bio pages

Bio pages are opened from Instagram and TikTok profiles, so nearly every visit starts inside an in-app browser.

### Hosted bio pages

| Service | In-app escape |
|---|---|
| [Beacons](https://beacons.ai) | — |
| [Bio.link](https://bio.link) | — |
| [Linktree](https://linktr.ee) | — |

### Open-source bio pages

These render HTML, so an escape script can go straight into the page `<head>`.

- [LinkNode](https://github.com/sujjeee/linknode) - Link-in-bio page generator. TypeScript.
- [Linkees](https://github.com/heysagnik/Linkees) - Linktree clone in React.
- [LinkStack](https://github.com/LinkStackOrg/LinkStack) - Self-hosted personal profile and link page. PHP.
- [LittleLink](https://github.com/sethcottle/littlelink) - Lightweight DIY Linktree alternative. HTML.
- [Singlelink](https://github.com/singlelink-co/Singlelink) - Open-source Linktree alternative. TypeScript.

## Self-hosted open-source shorteners

None of these escape in-app browsers out of the box yet. The usual fix: for in-app User-Agents, serve a small HTML interstitial that loads an escape script, instead of the plain 301/302. If your project adds this, open a PR and we'll mark it.

- [Chhoto URL](https://github.com/SinTan1729/chhoto-url) - Simple, fast, self-hosted shortener. Rust.
- [Dub](https://github.com/dubinc/dub) - Link attribution platform with short links and analytics. TypeScript.
- [Kutt](https://github.com/thedevs-network/kutt) - Free modern URL shortener. Node.js.
- [Lua](https://github.com/luadotsh/lua) - Scalable open-source shortener. PHP.
- [Polr](https://github.com/cydrobolt/polr) - Modern, robust shortener. PHP.
- [Pygmy](https://github.com/amitt001/pygmy) - Feature-rich, extensible shortener. Python.
- [Shlink](https://github.com/shlinkio/shlink) - Self-hosted shortener with a REST API. PHP.
- [shortme](https://github.com/andyxning/shortme) - Shortening service in Go.
- [Slash](https://github.com/yourselfhosted/slash) - Self-hosted platform for sharing and managing links. TypeScript/Go.
- [Slug](https://github.com/pheralb/slug) - Shortener built with the T3 stack. TypeScript.
- [Snapp](https://github.com/urania-dev/snapp) - URL shortener. Svelte.
- [UrlHub](https://github.com/realodix/urlhub) - Laravel-based shortener. PHP.
- [YOURLS](https://github.com/YOURLS/YOURLS) - The long-standing self-hosted PHP shortener with a plugin system.
- [zws](https://github.com/zws-im/zws) - Shortens URLs using invisible spaces. TypeScript.

### Serverless and static

- [gh-pages-url-shortener](https://github.com/nelsontky/gh-pages-url-shortener) - Shortener hosted entirely on GitHub Pages. HTML.
- [netlify-shortener](https://github.com/kentcdodds/netlify-shortener) - Your own shortener on Netlify redirects. JavaScript.
- [shrtnr](https://github.com/oddbit/shrtnr) - Short links on Cloudflare Workers with MCP server, REST API and SDKs. TypeScript.
- [Sink](https://github.com/miantiao-me/Sink) - Serverless shortener with analytics on Cloudflare. TypeScript.
- [Suri](https://github.com/surishortlink/suri) - Short links as a static site. JavaScript.
- [Url-Shorten-Worker](https://github.com/xyTom/Url-Shorten-Worker) - Shortener on Cloudflare Workers. JavaScript.

## Commercial self-hosted

- [Premium URL Shortener](https://gempixel.com/products/premium-url-shortener) - Paid self-hosted PHP shortener script.

## In-app browsers and short links

### Reading

- [The Pitfalls of In-App Browsers](https://frontendmasters.com/blog/the-pitfalls-of-in-app-browsers/) - What breaks inside in-app browsers and why.
- [Spying on the spies: what JavaScript in-app browsers inject](https://www.malwarebytes.com/blog/news/2022/08/spying-on-the-spies-see-what-javascript-commands-get-injected-by-an-in-app-browser) - Felix Krause's research into scripts injected by Instagram, Facebook and TikTok.
- [Escaping Instagram's In-App Browser on iOS](https://dev.to/jplogix/escaping-instagrams-in-app-browser-on-ios-and-why-its-so-hard-58om) - Practical write-up of iOS escape attempts.
- [What Actually Escapes Instagram's In-App Browser in 2026](https://plugwith.me/blog/what-escapes-instagram-in-app-browser-in-2026/) - Per-app test results for `extbrowser`, `x-safari-https` and meta-refresh techniques.
- [Google: OAuth changes for embedded webviews](https://developers.googleblog.com/en/upcoming-security-changes-to-googles-oauth-20-authorization-endpoint-in-embedded-webviews/) - Why Google sign-in fails with `403 disallowed_useragent` in in-app browsers.
- [LINE: Open in an external browser](https://developers.line.biz/en/docs/line-mini-app/develop/external-browser/) - LINE's official way out of its in-app browser.

### Escape cheat sheet

Observed techniques. Only LINE's is officially documented; apps change the rest without notice, so always ship a visible fallback (an "Open in browser" button or copy-link).

| App | Detect (User-Agent) | iOS | Android |
|---|---|---|---|
| Instagram | `Instagram` | `instagram://extbrowser/?url=<encoded>` (meta refresh or tap) | `intent://…#Intent;scheme=https;…;end` |
| Threads | `Barcelona` | `barcelona://extbrowser/?url=<encoded>` | intent |
| Facebook / Messenger | `FBAN`, `FBAV`, `FB_IAB` | `x-safari-https://…` after a tap | intent |
| LinkedIn | `LinkedInApp` | `x-safari-https://…` after a tap | intent |
| TikTok | `musical_ly`, `Bytedance` | `x-safari-https://…` after a tap | intent |
| X / Twitter | `Twitter` | `x-safari-https://…` | intent |
| WhatsApp | `WAiOS`, `WA4A` | `x-safari-https://…` | intent |
| Telegram | `window.TelegramWebviewProxy` | `x-safari-https://…` | intent |
| LINE | `Line/` | `?openExternalBrowser=1` (official) | same |
| WeChat | `MicroMessenger` | none — show "three-dot menu → Open in browser" | none |

### Libraries

Detection:

- [am-i-inapp-browser](https://github.com/luizcieslak/am-i-inapp-browser) - Series of tests for detecting an in-app browser.
- [detect-inapp](https://github.com/f2etw/detect-inapp) - Early, widely forked in-app browser detector.
- [inapp-spy](https://github.com/shalanah/inapp-spy) - Detects 14 in-app browsers by User-Agent plus Telegram and SFSafariViewController checks. TypeScript.

Escape:

- [escape-webview](https://github.com/pauljump/escape-webview) - Breaks out of X, Instagram, Facebook and TikTok in-app browsers.
- [inapp-escape](https://github.com/deepthix/inapp-escape) - Escapes Instagram, TikTok, Facebook and X in-app browsers.
- [InAppBrowser-Escaper](https://github.com/jeonghunn/InAppBrowser-Escaper) - In-app browser escape helper.
- [open-in-native-browser](https://github.com/muddassirhq/open-in-native-browser) - Detects 14 in-app browsers, hands off to Safari/Chrome per app, with a fallback banner. Works via npm or a script tag, including on shortener interstitials.

### Testing tools

- [InAppBrowser.com](https://github.com/KrauseFx/InAppBrowser.com) - Open it inside any app to see what JavaScript the in-app browser injects.
- [inapp-debugger](https://github.com/shalanah/inapp-debugger) - Test page for common in-app browser issues.

## Related lists

- [Awesome URL Shortener](https://github.com/738/awesome-url-shortener) - Broad directory of shortener services, including archived and deprecated ones.
