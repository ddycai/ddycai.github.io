---
layout: post
title: Transposer
desc: Javascript library and web app that transposes chords and lyrics.
proj-url: https://frigidrain.github.io/transposer
proj-num: 02
thumb: Transposer.png
---

## Introduction

Singers often have to change the key of their song so that the notes are within their vocal range. As someone who sometimes gives singing a try, I found myself going through the painstaking process of transposing chords by hand. To save myself some time, I wrote this program to transpose chords automatically for me. I did find some chord transposers online at the time, but I wasn't satisfied with their performance. They would often give the wrong form of a chord. For example, giving **Bb** as **A#**. Although they are the same chord[^1], **A#** is almost never seen and would be incorrect in most key signatures.

## Features

I designed the web application to contain features that I thought were useful and were missing from other chord transposition software.

#### Chord Detection

The program can tell with reasonably high accuracy which parts of the text are chords and which parts are lyrics. It will then transpose only the chords, leaving the lyrics intact. It can identify and transpose a variety of chords including chords with suffixes such as **Ab7** and **Asus4** or chords with a bass note such as **F/G**. Here are all the types of chords which the program is able to transpose:

 * Major and minor chords eg. Cm, Cmin, Cmaj
 * Dominant seventh eg. C7
 * Diminished, sustained, augmented eg. Cdim, Csus4, Caug
 * Chords with added notes eg. Cadd9, C+9, C9

#### Multiple Transposition Options

The user can choose to either transpose to a target key signature or transpose up/down a certain number of semitones. Most other transposition software I've seen has only one of these features, but not both.

If the user chooses to transpose by a number of semitones, the transposer will need to know the current key signature from the user. If the user does not provide the current key signature, then the transposer will naively infer the current key signature from the first chord. In the majority of cases, the first chord identifies the key signature, which saves users the trouble of having to state it for the program.

#### Knows About Key Signatures

The transposer understands which chords are valid in the target key signature and will only output those chords. For example, if we are transposing to **Bb** major, the chord transposer will not output **A#** or **E#**, as these are not valid chords in **Bb** major.

#### Chord Highlighting

The program highlights chords which are the same in the same colour. This is useful for anyone reading the chords to easily identify which chords are the same. The colour scheme can also be changed at the top right.

## Technology

The transposer library is written in Javascript and uses HTML/CSS for the user interface. To recognize chords, it uses the [XRegExp](http://xregexp.com/) [regular expression](https://en.wikipedia.org/wiki/Regular_expression) javascript library.

## Footnotes

[^1]:They are called [enharmonic equivalents](https://en.wikipedia.org/wiki/Enharmonic) since they are different notations for the same pitch.
