---
layout: post
title: Transposer
desc: Javascript library and web app that transposes chords and lyrics.
proj-url: https://frigidrain.github.io/transposer
proj-num: 02
thumb: Transposer.png
---

## Introduction

Singers often have to change the key of their song so that they can hit all the notes. As someone who sometimes gives singing a try, I couldn't find a chord transposer that could do it properly back when I wrote this program. The chord transposers available would often give the wrong form of a chord. For example, it would give the chord Bb as A#. They are the same chord[^1], but by convention, the correct name for the chord is usually Bb A#.

## Features

This web application contains a combination of several features that distinguish it from existing chord transposition software.

#### Chord Detection

Given a bunch of lyrics containing both chords and lyrics, it can tell with reasonably high accuracy which text is a chord and which text are lyrics. It will then transpose only the chords, leaving the lyrics intact. It can identify and transpose a variety of chords including chords with suffixes such as `Ab7` and `Asus4` or chords with a bass note such as `F/G`.

#### Multiple Transposition Options

The user can choose to either transpose to a target key signature or transpose up/down a certain number of semitones. If the user chooses the latter option, the transposer will need to know the current key signature from the user. If the user does not provide it, then the transposer will naively infer the current key signature from the first chord. This saves a lot of time for the user since in the majority of cases, the first chord is the identity of the current key signature.

#### Knows About Key Signatures

The transposer will only output chords which are part of the target key signature. For example, if we are transposing to Bb major, the chord transposer will not output A# or E#, as these are not valid chords in Bb major.

### Technology

The transposer library is written in Javascript and uses HTML/CSS for the user interface. To recognize chords, it uses the [XRegExp](http://xregexp.com/) [regular expression](https://en.wikipedia.org/wiki/Regular_expression) javascript library.

#### Footnotes

[^1]:They are called [enharmonic equivalents](https://en.wikipedia.org/wiki/Enharmonic) since they are different notations for the same pitch.
