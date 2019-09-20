---
layout: post
title: Respecting the dark mode on the web!
tags:
  - dark-mode
  - macOS
  - iOS
youtubeId: tVOOGUFnf9Y
---

For the past few days while working late nights, I figured that the dark text on light background in spite of having an extremely low brightness and contrasts on my screen gave me headaches. I know I'm pretty late here but I immediately turned to the dark themes on IDE to realize that I should start using macOS's (or any other OS's) dark mode for easier and longer usage without the strain on the eyes and no headaches.

On switching to the dark mode, all system applications turn darker and are easier to work with (of course, especially in the night). Thanks to the confirmation bias I started noticing that the developer community too had puns regarding the same.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">When u open Xcode on a new machine and it defaults to Light Mode <a href="https://t.co/n7IOvNenEI">pic.twitter.com/n7IOvNenEI</a></p>&mdash; Justin Poliachik (@poli_J_) <a href="https://twitter.com/poli_J_/status/1173404970726711296?ref_src=twsrc%5Etfw">September 16, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

But the problem still remained when dealing with websites!

I wished all the websites too confirmed to the system's color scheme preferences again only to realize that Apple did update Webkit's standards with a CSS media query called ```prefers-color-scheme``` that detects the system color scheme and decides which one to render! And it does has an RFC too.
Here's a [WWDC 2019's video](https://developer.apple.com/videos/play/wwdc2019/511/) depicting webpage's adaptation to the dark mode.

The process becomes easier by using CSS variables as follows:

```css
/* Defaults */
:root {
    --background-color: white;
    --text-color: black;
}

/* Light mode */
@media (prefers-color-scheme: light) {
    :root {
        --background-color: white;
        --text-color: black;
    }
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
    :root {
        --background-color: black;
        --text-color: white;
    }
}

/* Usage */
html {
    background: var(--background-color);
    color: var(--text-color);
}
```

The best part about this adaptation is also the fact that the websites can have 2 different set of images to the 2 schemes (light/dark) which is now kind of intuitive if you think about it. After making this small change I noticed that all the known developers in the community like Mattt who authors [NSHipster](http://nshipster.com/) or David Smith who writes [his blog](https://david-smith.org) had already made this change! Undoubtedly, this wave will hit the future of web design and thus will enable better web!

One last thing in the process is to choose the better (appropriate) versions of light and dark color palates for the webpages.

Here are few of my favorite dark theme color palates from this cool [website](https://colorhunt.co/palettes/dark).

![Palate-01](https://github.com/nirajkadam/nirajkadam.github.io/blob/master/images/dark-mode-themes/Palate-01.png?raw=true)
![Palate-02](https://github.com/nirajkadam/nirajkadam.github.io/blob/master/images/dark-mode-themes/Palate-02.png?raw=true)
![Palate-03](https://github.com/nirajkadam/nirajkadam.github.io/blob/master/images/dark-mode-themes/Palate-03.png?raw=true)
![Palate-04](https://github.com/nirajkadam/nirajkadam.github.io/blob/master/images/dark-mode-themes/Palate-04.png?raw=true)

Here's a small example of the difference:

{% include youtubePlayer.html id=page.youtubeId %}

Thank you for stopping by.
