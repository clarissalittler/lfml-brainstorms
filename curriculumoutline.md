# Purpose of this doc
We're coming up with an outline of concepts, demos, and topics for a set of open modules on lo-fi machine learning
# Open questions
 How many modules should exist?

# Classification vs. Regression
- Identify the differences between classification and regression 
- Discrete categories vs continuous values
- Thresholding continuous values to create discrete categories
- Applications: what are the uses of each for real time interaction

Should this also borrow from the presentation in *Rashid (2016) Make your own neural network*? It's a good text for introducing this as basic curve-fitting.

# Markov processes
## Core concepts
### Math introduced
 - probability
 - graphs? but like as paths that are influenced by the models?
### Context vs. contextless
### Randomness for generation
## Demos
### Text generation
 This is the simplest, most straightforward, use of markov processes. What would be interesting is to experiment, I think, with messier kinds of splits of tokens for artistic reasons. For example, normally you would rip out whitespace but I think instead keeping linebreaks and punctuation as their own tokens will create some chaos.
 
 The library should also have variable context windows to show how the idea can adapt to a very limited sort of state which is still very different than a *real* context like what modern transformers have. Markov processes with a window as state is, basically, a connecting point to the idea of RNNs
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
# DTW, MFCC, Speec/Sound Classification
- "signals" as data, try to visualize a "time series"
- try to define "gestures" broadly to include speech
- problematize gestures (different speeds, different bodies, saying a word twice exactly the same)
- vocab/discuss "dimensionality reduction" and "feature extraction"
- JavaScript code performs fft -> mfcc, assists creating dataset
- try to succesfully recognize a few words
- try to animate an anime character's mouth with phonemes and different images
- Dynamic time warping: fits into optimization thread
- Mel scale feature extraction: ccl has never written this before, is writing the JavaScript implementation within scope?
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
### Concepts
Yet another way to turn a problem into riding along slopes, but this time you're not worrying about questions of smoothness and slope. No, instead you're just trying to find the extrema of measures by using genetically inspired things for search.
### Demos
 - Painting with genetic algorithms, can be done in p5.js even
 - Music generation (user defined fitness functions?)
 - Text generation

# Optimizing: neural networks
The point of this is that we can finally introduce the idea that neural networks are an easy way to turn things into "smooth" operations

# Things that should probably go somewhere but I don't know where
## Principal Component Analysis
This is basically a technique from machine learning that is about finding the most useful basis of a dataset

There's something about it that rhymes without auto-encoding, to me, in that it's about finding a smaller representation automatically from the structure of the data. It's a bit different, though, in that you're not deciding on the dimensional representation in advance by creating a bottleneck. You're building it based off not deeper structure in the data but off the covariance in the numeric data.

Here's a fun use of PCA for artistic purposes:
https://aparico.github.io/

they're using it for image augmentation but I think it's going to be more interesting as a way of processing images

## lo-fi text encoding
A lot of text manipulation involves learning how to encode text.

But how is that done?

There are a number of different ways to embed text, ranging from "bag of words" to actual learned tokenization like modern machine learning.

The problem is that I'm not sure what counts as the "lo-fi" version of it. This is something to investigate because it opens up a huge number of possible creative applications.
## Auto-encoding
This is a related concept to text encoding but also far more wide-reaching

The general principle is that if you can make a way to measure the inaccuracy of compress/uncompressing information then you can come up with an encoder/decoder pair by splitting the process in half

How to present this core concept via intuition?
## The world's tinest CLIP
One thing that would probably make a good module for any class.

The basic concept here is that you build the tinest, tiniest, most scuffed CLIP like system possible.

This means you build an autoencoder for images and an autoencoder for text and make part of the loss maximizing the dot product between the text part and the image part of the encoding

To make this as dead simple as possible I think the easiest thing we can do is make something like 32x32 images of different shapes: triangle, circle, square, ??? things like that

and then we associate them with words and encode the words just as a fixed length descriptor (rather than a true tokenizer) and then building the association in terms of those fixed vectors: just long enough to include certain adjectives in addition to nouns

Then, if everything works correctly, you should be able to not only request shapes with adjectives they didn't specifically have but start using whatever words you want, if they fit, and seeing what shapes come out.

(ccl being weird: okay so this is actually related to the concept of sigil generation but we don't need to frame it that way because it'd sorta get *odd* quickly for folks who aren't expecting computational witchcraft)

I *think* this is small enough we'd be able to actually use it both as a teaching example and also build it entirely in our own machine learning framework
## Transformers
It's the architecture that's changed the world. It feels like it'd probably be worth it to come up with some kind of minimal exam that demonstrates the main concepts:

Namely, a system that looks at the entire context and learns a "weighting" for how to associate pieces.

# Misc references
This is a textbook that covers concepts in deep learning from the perspective of connecting differentiable programming and physics. The natural connection here is that the concept of minimizing the loss is basically the same as minimizing the lagrangian in physics. This is not something to use as direct teaching material but it could potentially be inspiration for visual things
https://physicsbaseddeeplearning.org/intro.html

This is a series of google colab notebooks from the orientation of making small art projects. It's probably one of the best introductions to neural networks in PyTorch and it's the thing that originally got me thinking that differentiable programming might be a good perspective to start taking as a unifying explanation for the reason why neural networks have become so ubiquitous
https://github.com/johnowhitaker/aiaiart

This is a tutorial on building a variational autoencoder that looks actually kinda legit. My hope is that I can take this apart and figure out how to build a very minimal version to use in trying to understand how to build a more interesting version of "baby's first CLIP", one that demonstrates that modern machine learning techniques involve learning representations
https://blog.paperspace.com/how-to-build-variational-autoencoder-keras/

This is the paper that started whole transformer architecture revolution six years ago.
Vaswani, Shazeer & Parmar et al. (2017) Attention Is All You Need, CoRR.
https://arxiv.org/abs/1706.03762

Genetic algorithms for imitating images to be painting-like
https://shahriyarshahrabi.medium.com/procedural-paintings-with-genetic-evolution-algorithm-6838a6e64703
original github https://github.com/anopara/genetic-drawing

Early research on genetic algorithms and art
https://www.researchgate.net/publication/249562088_Genetic_Algorithms_in_Visual_Art_and_Music

Genetic algorithms for music generation:
https://www.researchgate.net/publication/221008730_A_simple_genetic_algorithm_for_music_generation_by_means_of_algorithmic_information_theory

Genetic algorithms for poetry (warning: an entire thesis):
https://era.ed.ac.uk/bitstream/handle/1842/314/IP040022.pdf?isAllowed=y&sequence=1
