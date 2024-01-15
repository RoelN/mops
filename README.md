# MOPS

$ELEVATOR_PITCH goes here.

_“Not a reset, not a boilerplate... simply a mildly opinionated prose stylesheet!”_

Browsers offer a basic typographic system out of the box. But they can do so much more.

Likewise, fonts can offer OpenType features by default, but can do so much more.

MOPS™ will unlock extra typographic features you can just drop into your blog, personal site or $OTHER_USECASES.

# Use cases

Ideally you can use a class to unlock certain features.

Example: oldstyle figures could work nicely in a story, but not in a technical blog post.

- Blog
- Technical writing
    - Data
- News article
- Storytelling


# How to use

Perhaps something like this:

```html
<div class="mops mops-story">
   ...
</div>
```

The first class, `mops`, sets up the basics of the system. The second class, `mops-story` builds on that and adds styles that work best for "book-like" stories. For example oldstyle figures, hanging punctuation, etc.

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

## To Figure Out / To Do

- Are there already styleguides like this in "classic" typography?
- Do we go for `font-variant-*` only? Also `font-feature-settings` fallbacks? Let user choose?
- [Gutenberg](https://github.com/matejlatin/Gutenberg) does something similar. How is MOPS different? Should we offer float, align, horizontal rule styling? I like the [paragraph indenting](https://github.com/matejlatin/Gutenberg/wiki#paragraph-indenting), sounds like something that should be part of a mildly opinionated prose stylesheet!