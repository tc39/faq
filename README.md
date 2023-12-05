# Frequently Asked Questions

This document contains typical responses to questions that are commonly raised about JavaScript language development, both within the community and to the committee via our various discussion platforms.

Anyone may suggest new topics by [opening an issue](https://github.com/tc39/faq/issues/new). Delegates may add new topics by creating a Pull Request. If a delegate disagrees with one of these topics, it should be removed. It can be re-added if they and the original topic suggester are able to come to agreement on wording.

## Disclaimer

The information in this document is curated by individual TC39 delegates with minimal review and may reflect personal biases; it is not authoritative and has not been endorsed by TC39. Regardless, it may be helpful for those with questions, or at least a handy reference for delegates or anyone else fielding these questions.

## Questions

### Why not just add a new version and fix all the mistakes?

[Disclaimer: FAQ answers are not endorsed by TC39][]

Having to maintain multiple versions of the language forever wouldn't actually make the world better, and we can't ever stop supporting the existing version. Many of the mistakes are in standard library functions, and those can't realistically be versioned. We'd just have to add new ones and keep the old ones around.

### Why don't we just break the web?

[Disclaimer: FAQ answers are not endorsed by TC39][]

Browsers are [unwilling to break web pages](https://developer.chrome.com/blog/smooshgate/#why-dont-we-just-keep-the-existing-name-and-break-the-web) for their users, no matter how much you think the developers of those websites deserve it. However, "not breaking the web" does not mean 100% backward compatibility. Backward-incompatible changes *can* be made when the undesirable behaviour is not being relied upon, but the web is very large, which makes it both hard to confidently determine this and unlikely except for very minor or very strange behaviours.

### Will WebAssembly replace JS?

[Disclaimer: FAQ answers are not endorsed by TC39][]

In the short term, you'll continue to need JS glue code to do many things like interacting with the DOM. In the long term, maybe you will be able to skip the glue code, though some people will continue to write JS, and JS engines will not be implemented in WebAssembly.

### Why do numbers sometimes behave unintuitively?

[Disclaimer: FAQ answers are not endorsed by TC39][]

JavaScript numbers and arithmetic are specified in IEEE-754. See <https://0.30000000000000004.com>.

### Will JavaScript ever add JSX notation?

[Disclaimer: FAQ answers are not endorsed by TC39][]

JSX as it is today can't be added because it conflicts with existing syntax, but a variant could be done, in principle. It's a hard problem because you don't want to tie it to any particular framework.

### Can we change the way this language feature or API works?

[Disclaimer: FAQ answers are not endorsed by TC39][]

This is always very unlikely due to web compatibility difficulties. It would have to be very well motivated to even attempt. See [*Why don't we just break the web?*](#why-dont-we-just-break-the-web).

### Can we change JSON?

[Disclaimer: FAQ answers are not endorsed by TC39][]

No chance. Because it is an interchange format with implementations in nearly every computing environment, JSON is set in stone forever.

### What's up with PTCs? Does JS have them or not?

[Disclaimer: FAQ answers are not endorsed by TC39][]

Proper tail calls (PTCs) are [defined in the specification](https://tc39.es/ecma262/multipage/ecmascript-language-functions-and-classes.html#sec-preparefortailcall), but are currently only implemented by JavaScriptCore, the JavaScript engine used in the Safari browser. Other engines have no plans to implement PTCs at the moment. PTCs predate our current process, which would have prevented a situation like this from happening, and will prevent any others from happening in the future.

### Why are some things specified in ECMA-262 and others are in WHATWG/W3C specs? How do I know what is where?

[Disclaimer: FAQ answers are not endorsed by TC39][]

ECMA-262 defines a general-purpose programming language which is meant to run in many environments, not just the web. So features that are only relevant to the web will not live in ECMA-262. Additionally, any I/O (including DOM APIs) will not be in ECMA-262. Unfortunately, for general-purpose features that you may be familar with on the web, there is not a good way to know what feature lives in what spec ahead of time. Many of these distinctions are due to outside circumstances, not careful planning.

[Disclaimer: FAQ answers are not endorsed by TC39]: #disclaimer
