# [Create a Responsive Website Using HTML5 and CSS3](https://www.youtube.com/watch?v=eOG90Q8EfRo)

Rewritten from the YouTube tutorial by 1stWebDesigner, published on March 16, 2013.

## Why This Tutorial

So the last time I did professional web development was 2010, and a _lot_ of the technology standards have significantly changed since. This tutorial is from 2013: more up to date than 2010 but not overwhelmingly so.

I tried to educate myself on modern web development standards with freeCodeCamp, but those projects gave me acute blank page anxiety, and really halted my learning progress. I did complete a few fcc projects, but I wanted a better anchoring than my stale instincts. I also wanted to use "on the job" what I intuited were the most common modern webdev tools, namely Visual Studio Code and git.

And wow, I really did hit the jackpot! I enjoyed the length and simplicity of this tutorial, and I [copied the original nearly verbatim](https://codepen.io/bgbraithwaite/pen/zbjwqZ). I recognized areas that I could improve on the original with more modern standards I had learned about in fcc and outside reading, and decided to push myself (pun intended) by doing just that.

This tutorial rewrite is intended to cement my knowledge of semantic HTML5, basic Flexbox, and to a much lesser extent CSS3.

## Notes on the Original

### `<content>` Tag

[`<content>`: The Shadow DOM Content Placeholder element (obsolete)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) reveals that the `<content>` tag is not only deprecated, but was not ever what 1stWebDesigner seemed to think it was. He used it as a kind of `<div>` or sub-`<article>` tag, but it seems to have been a draft tag for webapps using Web Components.

I wish that I had recognized it's fishiness instinctively, but really I googled it because VSCode didn't recognize the tag.

Unfamiliar topics: Shadow DOM, Web Components, `<slot>`

### Layout Oddities

There are strange vertical gap irregularities I can't explain above the sidebar: too large a gap in desktop view, too narrow in "mobile" responsive view.

He relies on CSS classes way more than I feel comfortable doing; if nothing else, it felt repetitive to class out semantic tags for styling. Reminds me of inline styles but ... more elaborate?

## Changes for the Rewrite

### Flexbox

After watching [Making Future Interfaces: Algorithmic Layouts](https://www.youtube.com/watch?v=qOUtkN6M52M) by Heydon Pickering, I am both charmed and going to use the Flexbox sidebar layout he describes (with some modifications found in the comments [here](https://gist.github.com/Heydon/c0b1d088461c64370d6fe1a19bff4b9f)), but switching the right-hand side to be the sidebar that goes under.

Since this is a simple layout, I'll use it to practice Flexbox.

Later: Unnecessarily complicate my life by making a version 2.0 with CSS Grid.

### Stylistic Choices

I set a different font, just to be contrary.

I added some border highlights to the content articles (and ran into a weird layout problem, see below).

I shrank many whitespaces purposefully, but in general I set spacing as rem units rather than with percentages (see same weird layout problem down below).

## Things I Don't Understand (Yet)

### Sidebar Border ... Thing

This CSS makes the sidebar display like I would expect it to, same look as the main article elements:

`border: var(--white) solid 0.1rem;`

However, I would expect it to display the same with or without me setting border properties manually. Without a set border, it's like _something_ collapses and as far as I can discern, there is no... padding? The usual `* {border: red solid 1px;}` debugging tool just... fixes it, without enlightening me as to why it was broken.

So to find out why this happens, I'm fairly certain I need to read about what CSS properties collapse when unset, probably something to do with the border box model (super suspicious it has to do with padding).

I notice [Christian has a similar-appearing problem in his original design](https://codepen.io/bgbraithwaite/pen/zbjwqZ), but he didn't set article borders for his design at all. Instead the problem is far more mysterious to me: the elements interpreted the calculated `margin-top: 2%;` differently. WHAT.
