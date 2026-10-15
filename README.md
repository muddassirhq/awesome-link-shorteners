# Awesome In-App Browsers [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Everything about the browsers hidden inside Instagram, Facebook, TikTok, LinkedIn, X, Snapchat, WhatsApp, Telegram, LINE and WeChat — why links feel broken in them, how to detect them, and how to get visitors out to their real browser.

When someone taps a link inside a social or messaging app, it usually opens in that app's built-in WebView instead of Safari or Chrome. The visitor is logged out of everything, links that should open an app (YouTube, Spotify, Amazon, Maps) stay as mobile web pages, saved passwords and cards are missing, "Sign in with Google" is blocked, and the page disappears when they close the app.

This list collects the research, libraries, techniques and tools for dealing with that.

## Contents

- [Understanding the problem](#understanding-the-problem)
- [Escape cheat sheet](#escape-cheat-sheet)
- [Libraries](#libraries)
  - [Detection](#detection)
  - [Escape](#escape)
- [Testing tools](#testing-tools)
- [Official documentation](#official-documentation)
- [Open-source link shorteners](#open-source-link-shorteners)
- [Open-source link-in-bio pages](#open-source-link-in-bio-pages)
- [Hosted services](#hosted-services)
- [Related lists](#related-lists)

## Understanding the problem

- [The Pitfalls of In-App Browsers](https://frontendmasters.com/blog/the-pitfalls-of-in-app-browsers/) - Frontend Masters overview of what breaks inside in-app browsers and why.
- [Spying on the spies: what JavaScript in-app browsers inject](https://www.malwarebytes.com/blog/news/2022/08/spying-on-the-spies-see-what-javascript-commands-get-injected-by-an-in-app-browser) - Malwarebytes on Felix Krause's research into scripts injected by Instagram, Facebook and TikTok.
- [Escaping Instagram's In-App Browser on iOS (and Why It's So Hard)](https://dev.to/jplogix/escaping-instagrams-in-app-browser-on-ios-and-why-its-so-hard-58om) - Practical write-up of iOS escape attempts.
- [What Actually Escapes Instagram's In-App Browser in 2026](https://plugwith.me/blog/what-escapes-instagram-in-app-browser-in-2026/) - Per-app test results for `extbrowser`, `x-safari-https` and meta-refresh techniques.
- [Upcoming security changes to Google's OAuth 2.0 endpoint in embedded webviews](https://developers.googleblog.com/en/upcoming-security-changes-to-googles-oauth-20-authorization-endpoint-in-embedded-webviews/) - Why Google sign-in fails with `403 disallowed_useragent` inside in-app browsers.

## Escape cheat sheet

Observed techniques. None are officially documented except LINE's, and apps change them without notice — always ship a visible fallback (an "Open in browser" button or copy-link).

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

## Libraries

### Detection

- [inapp-spy](https://github.com/shalanah/inapp-spy) - Detects 14 in-app browsers by User-Agent plus Telegram and SFSafariViewController checks. TypeScript.
- [detect-inapp](https://github.com/f2etw/detect-inapp) - Early, widely forked in-app browser detector.
- [am-i-inapp-browser](https://github.com/luizcieslak/am-i-inapp-browser) - Series of tests for detecting an in-app browser.

### Escape

- [escape-webview](https://github.com/pauljump/escape-webview) - Breaks out of X, Instagram, Facebook and TikTok in-app browsers.
- [inapp-escape](https://github.com/deepthix/inapp-escape) - Escapes Instagram, TikTok, Facebook and X in-app browsers.
- [InAppBrowser-Escaper](https://github.com/jeonghunn/InAppBrowser-Escaper) - In-app browser escape helper.
- [open-in-native-browser](https://github.com/muddassirhq/open-in-native-browser) - Detects 14 in-app browsers, hands off to Safari/Chrome per app, and shows a fallback banner with Open and Copy link. Zero dependencies; npm, script tag, WordPress plugin and GTM template.

## Testing tools

- [InAppBrowser.com](https://github.com/KrauseFx/InAppBrowser.com) - Open it inside any app to see which JavaScript the in-app browser injects.
- [inapp-debugger](https://github.com/shalanah/inapp-debugger) - Test page for common in-app browser issues.

## Official documentation

- [LINE: Open in an external browser](https://developers.line.biz/en/docs/line-mini-app/develop/external-browser/) - LINE's documented way to leave its in-app browser.

## Open-source link shorteners

Short links shared on social media are the most common way visitors end up in an in-app browser. None of these escape in-app browsers out of the box yet; for each, the fix is to serve a small HTML interstitial (loading an escape script) to in-app User-Agents instead of the plain 301/302. Contributions documenting a built-in option or plugin are welcome.

- [Chhoto URL](https://github.com/SinTan1729/chhoto-url) - Simple, fast, self-hosted shortener. Rust.
- [Dub](https://github.com/dubinc/dub) - Link attribution platform with short links and analytics. TypeScript.
- [gh-pages-url-shortener](https://github.com/nelsontky/gh-pages-url-shortener) - Shortener hosted entirely on GitHub Pages. HTML.
- [Kutt](https://github.com/thedevs-network/kutt) - Free modern URL shortener. Node.js.
- [Lua](https://github.com/luadotsh/lua) - Scalable open-source shortener. PHP.
- [netlify-shortener](https://github.com/kentcdodds/netlify-shortener) - Your own shortener on Netlify redirects. JavaScript.
- [Polr](https://github.com/cydrobolt/polr) - Modern, robust shortener. PHP.
- [Pygmy](https://github.com/amitt001/pygmy) - Feature-rich, extensible shortener. Python.
- [Shlink](https://github.com/shlinkio/shlink) - Self-hosted shortener with a REST API. PHP.
- [shrtnr](https://github.com/oddbit/shrtnr) - Short links on Cloudflare Workers with MCP server, REST API and SDKs. TypeScript.
- [shortme](https://github.com/andyxning/shortme) - Shortening service in Go.
- [Sink](https://github.com/miantiao-me/Sink) - Serverless shortener with analytics on Cloudflare. TypeScript.
- [Slash](https://github.com/yourselfhosted/slash) - Self-hosted platform for sharing and managing links. TypeScript/Go.
- [Slug](https://github.com/pheralb/slug) - Shortener built with the T3 stack. TypeScript.
- [Snapp](https://github.com/urania-dev/snapp) - URL shortener. Svelte.
- [Suri](https://github.com/surishortlink/suri) - Short links as a static site. JavaScript.
- [UrlHub](https://github.com/realodix/urlhub) - Laravel-based shortener. PHP.
- [Url-Shorten-Worker](https://github.com/xyTom/Url-Shorten-Worker) - Shortener on Cloudflare Workers. JavaScript.
- [YOURLS](https://github.com/YOURLS/YOURLS) - The long-standing self-hosted PHP shortener with a plugin system.
- [zws](https://github.com/zws-im/zws) - Shortens URLs using invisible spaces. TypeScript.

## Open-source link-in-bio pages

Link-in-bio pages live inside Instagram and TikTok profiles, so nearly every visit starts in an in-app browser. These render HTML, so an escape script can go straight into the page `<head>`.

- [LinkNode](https://github.com/sujjeee/linknode) - Link-in-bio page generator. TypeScript.
- [Linkees](https://github.com/heysagnik/Linkees) - Linktree clone in React.
- [LinkStack](https://github.com/LinkStackOrg/LinkStack) - Self-hosted personal profile and link page. PHP.
- [LittleLink](https://github.com/sethcottle/littlelink) - Lightweight DIY Linktree alternative. HTML.
- [Singlelink](https://github.com/singlelink-co/Singlelink) - Open-source Linktree alternative. TypeScript.

## Hosted services

Commercial link tools that advertise opening links outside in-app browsers.

- [Bouncy](https://bouncy.ai)
- [link.boo](https://link.boo)
- [Linko](https://linko.me)
- [Lnk.Bio](https://lnk.bio)
- [Onlynk](https://onlynk.me)
- [PlugWith.me](https://plugwith.me)
- [U2L](https://u2l.ai)
- [WarpLink](https://warplink.app)

## Related lists

- [Awesome URL Shortener](https://github.com/738/awesome-url-shortener) - Curated list of URL shortener services and software.

## Contributing

Contributions welcome — read [CONTRIBUTING.md](CONTRIBUTING.md). Device test results for the cheat sheet are especially valuable: open an issue with app, app version, OS version, technique and result.

