# Purpose of this doc
We're coming up with an outline of concepts, demos, and topics for a set of open modules on lo-fi machine learning

# Markov processes
## Core concepts
### Math introduced
 - probability
 - graphs? but like as paths that are influenced by the models?
### Context vs. contextless
### Randomness for generation
## Demos
### Text generation
### Audio generation
- For working with polyphonic music one approach is to "encode" the polyphony into a BigInt by sorting the notes then shift and bitwise and them into ascending 8 bit sections. This relates to hashing and "dimensional reduction" but is a very "lo-fi" version. 
### Absurd image gen
- colors could be (and often are) stored in the same way as the polyphonic notes above. where a state includes rgba info. so if we spent time on that it could be worthwhile to support these examples. it also gives insight into the data structure of a "hash map" which is a cs fundamental and how the markov chain is implemented in code.
# Nearest neighbors and applications
## Core concepts
## Demos
### phone sensor lab
- Get pitch, yaw and roll from mobile phone via [sensors api](https://developer.mozilla.org/en-US/docs/Web/API/Sensor_APIs) (chrome-like browsers + safari)
- Create a data set of 3 classes (using phone, phone flat, phone in bags or pockets)
- Use kNN to see if our "shady app" can classify user "phone engagement" from background polling the position
- Discussion: "meaning" of data. does position really map to use?
### photo mosaic (with your own photos)
inspiration:
https://www.lambertleong.com/projects/photo-mosaic

can we let them link to a google drive folder in-browser to collage?
https://www.slidesmaker.me/blog/google-drive-api-javascript-all-operations

- have students take a photo of their own and collage it out of their other photos

art potential in very simple algorithms
### zany idea: finding the closest poetic match
Okay hear me out (and I might need to proof of concept this to demonstrate it's possible) consider adapting this algorithm
https://tug.org/docs/liang/liang-thesis.pdf
that's used for hyphenation to, instead, find and break down the syllabic structure of words

the learner is trained on a bunch of poetic forms and then matches the syllabic patterns to the one that's the closest fit, then forces the linebreaks so it kinda fits albeit probably with decent wrenching

No I'm not actually sure how this will work it just sounds fun and I want something textual
# Curve fitting: a first introduction
# Optimizing in 1-d: finding peaks and valleys
# Smoothness and gravity
Here's where we introduce baby's first automatic differentiation
(inspiration: https://thenumb.at/Autodiff/)

the goal isn't to teach calculus it's to build intuition for how it works, slopes, rates of change, &c.
## Slope of lines
## Everything is a line if you zoom in
## Finding the slopes automatically
## Multiple dimensions
## When all you have is gravity, everything looks like a hill
## Demos
The image de-blurring demo from the autodiff tutorial is a really fun one

# Optimizing: biologically inspired tricks
## Genetic algorithms
# Optimizing: neural networks
The point of this is that we can finally introduce the idea that neural networks are an easy way to turn things into "smooth" operations

# Things that should probably go somewhere but I don't know where
## lo-fi text encoding
A lot of text manipulation involves learning how to encode text.

But how is that done?

There are a number of different ways to embed text, ranging from "bag of words" to actual learned tokenization like modern machine learning.

The problem is that I'm not sure what counts as the "lo-fi" version of it. This is something to investigate because it opens up a huge number of possible creative applications.
## Auto-encoding
This is a related concept to text encoding but also far more wide-reaching

The general principle is that if you can make a way to measure the inaccuracy of compress/uncompressing information then you can come up with an encoder/decoder pair by splitting the process in half

How to present this core concept via intuition?
# Misc references
https://physicsbaseddeeplearning.org/intro.html
https://github.com/johnowhitaker/aiaiart
