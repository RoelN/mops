# Mildly Opinionated Prose Styles

Or MOPS, that's the name. (But we're not just doing prose. There's also technical writing, and data, and perhaps even physics or math?)

Browsers offer a basic typographic system out of the box. But they can do so much more.

Likewise, fonts can offer OpenType features by default, but can do so much more.

# The big idea

OpenType features (and some text-related features) are hard to discover. If you don't use them there won't be a problem. But if you _do_ use them, text is going to look better.

"Better"? Yeah, we think so. You might not like all changes that are happening, but you can easily turn off what you don't like. Discoverability > dictating styles.

It's better to see your options in action, and then deciding to not use them, than to never even know those options existed.

That's why _mildly_ opinionated.

# The things MOPS does

## Generic / to decide / misc

- Font synthesis off? (Also e.g. for superscript and their faux user agent superscripts)
- Do something with ex / cap? E.g. `.size-to-cap-height` utility class?

## Prose

Blog post, book, magazine article.

- Oldstyle figures
- Small caps in `<abbr>`
- Titling caps in `<h1>`

- Hyphenation in `<p>`
- Hanging punctuation in `<p>`
- `text-wrap: pretty` in `<p>`
- `text-wrap: balance` in `<h1>` (only advisable for centered text)

## Data

Tables.

- Tabular numbers

## Technical

A.k.a. "not prose".

- Lining numbers
- Fractions
- Scientific inferiors (which tag?)
- Proper superscript for `<sup>`
- Proper subscript for `<sub>`

# How to use

Perhaps something like this:

```html
<div class="mops mops-story">
   ...
</div>
```

```html
<table class="mops mops-data">
   ...
</table>
```

The first class, `mops`, sets up the basics of the system. The second class, `mops-story` builds on that and adds styles that work best for "book-like" typography. For example oldstyle figures, hanging punctuation, etc.

Likewise `mops-data` would enable tabular numbers. How about fractions?

# What (not) to do

## Should it include a type scale?

Yes:

- sounds like an essential part of a type-related stylesheet

No:

- out of scope
- there are several solutions for that
    - How to make MOPS work with an independent system that sets font sizes? Maybe as a rule we don't interfere with any font sizes? (At least out of the box. Or maybe optionally let users wire them up to MOPS via CSS variables?)

## Should it have CSS for features that might not be in the font?

In the oldstyle figures example, this only works if the font includes it. We can't know this beforehand. How to deal with that?

Superfutureidea: hook this up to the Wakamai Fondue engine. Folks can drop a font and only the features that are supported will be included.
