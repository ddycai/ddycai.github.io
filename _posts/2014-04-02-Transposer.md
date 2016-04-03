---
layout: post
title: Transposer
desc: Javascript library and web app that transposes chords and lyrics.
proj-url: https://frigidrain.github.io/transposer
proj-num: 02
thumb: Transposer.png
---



## Transposer

Singers often have to change the key of their song so that they can hit all the notes. As someone who sometimes gives singing a try, I couldn't find a chord transposer that could do it properly back then. Many chord transposer would try to give you a song that is in Bb major as A#. They are the same chord, but A# is almost never seen since it does not make sense.

This web application transposes chords and lyrics to any key the user wants. These are its most important features:

1. **Chord detection**: Given a bunch of lyrics containing both chords and lyrics, it can tell with reasonably high accuracy which text contains chords and which text contains lyrics. It will then transpose only the chords.
2. **Knowledge of key signatures**: The transposer will only output chords which are part of the target key signature. For example, if we are transposing to Bb major, the chord transposer will not output A# or E#.


### Technology

The transposer library is written in Javascript and uses HTML/CSS for the user interface. To recognize chords, it uses the [XRegExp](http://xregexp.com/) [regular expression](https://en.wikipedia.org/wiki/Regular_expression) javascript library.

