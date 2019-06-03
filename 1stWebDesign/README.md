# [Create a Responsive Website Using HTML5 and CSS3](https://www.youtube.com/watch?v=eOG90Q8EfRo)

Rewritten from the YouTube tutorial by 1stWebDesigner, published on March 16, 2013.

## Notes on the Original

### `<content>` Tag

[`<content>`: The Shadow DOM Content Placeholder element (obsolete)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/content) reveals that the `<content>` tag is not only deprecated, but was not ever what 1stWebDesigner seemed to think it was. He used it as a kind of `<div>` or sub-`<article>` tag, but it seems to have been a draft tag for webapps using Web Components.

I wish that I had recognized it's fishiness instinctively, but really I googled it because VSCode didn't recognize the tag.

Unfamiliar topics: Shadow DOM, Web Components, `<slot>`

## Changes for the Rewrite

### Flexbox and CSS Grid

After watching [Making Future Interfaces: Algorithmic Layouts](https://www.youtube.com/watch?v=qOUtkN6M52M) by Heydon Pickering, I am both charmed and going to use the Flexbox sidebar layout he describes (with some modifications found in the comments [here](https://gist.github.com/Heydon/c0b1d088461c64370d6fe1a19bff4b9f)), but switching the right-hand side to be the sidebar that goes under.

Rather than using CSS Grid for this simple layout, I'll practice Flexbox and save Grid practice for some more complex or experimental layout.

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
