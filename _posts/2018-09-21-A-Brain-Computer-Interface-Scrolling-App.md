---
layout: post
title: A Brain Computer Interface Scrolling App
excerpt_separator:  <!--more-->
---
My newest project is a BCI scrolling app.

In short, here's the idea: instead of having to use a mouse or touch a screen to scroll, you scroll _with your mind_.

In order for this to work, here's what I need to do:

1. Purchase EEG equipment from [](www.openbci.com)
2. Figure out a sufficient and reproducible discriminatory threshold that I can use to signal 'scroll' versus 'not scroll'
3. Package it in nice-looking front end and either make it open source or try and sell it as proof-of-concept
<!--more-->
Numbers (1) and (3) are comparatively easy. However, I foresee number (2) having the potential to take me a very long time - I would need to learn digital signal processing from scratch, and design an algorithm to implement the desired functionality.

Fortunately, I am a big fan of the Minimum Viable Product. I'm going to grow the idea step-wise, with the first step being as simple as possible: the transmission of a single bit of information (on vs. off) from the EEG to a computer.

Back in my fourth year of University, I had one professor - let's call him Don - that performed research primarily in magnetoencephalography (MEG) and its utility in seizure detection and markers of autism. He was a digital signal processing ninja, and I was lucky enough to be able to ask him a few questions during office hours one day. I believe the answers to those few questions are what's going to allow me to make this project.

It all boils down to brainwaves. When you put an electrode on a human brain, it shows characteristic fluctuations in voltage - these fluctuations can be broken down into several different 'classes', by which we can presume certain levels of neural activity. Here are a few:

* Alpha waves, which are defined as those that occur with a frequency of between 8-13Hz. These correspond to 'resting' brain states, such as those moments in time when you close your eyes or daydream.

* Beta waves, which are defined as those that occur with a frequency of >15Hz. These correspond to your 'waking' brain states - those that you engage in while performing cognitively demanding tasks.

* Delta waves, which occur in deep sleep and have a frequency of <3-4Hz.

If I was to place several electrodes on different areas of your head, each of those electrodes would be picking up different patterns of neural activity. This is only logical, since each electrode is measuring the activity of different neuronal subpopulations. However, different brain regions perform different functions, and as such change their activities in characteristic ways depending on the task performed. Your occipital lobe, for example, reacts differently to visual stimulus than your temporal lobe. This gives me a potential spatial parameter with which to build a threshold.

Additionally, one can look at the 'power' of different frequency bands. In reality, EEG recordings aren't perfect cycles - they're messy, and several types of waves are typically bundled into a single signal. With digital signal processing technology, one has the capacity to computationally separate these various cycles into their components. The proportion of cycles that are alpha, beta, or delta can then be used as an additional thresholding parameter, allowing me a second method to discriminate between an 'on' and an 'off' signal.

It would thus be perfectly feasible to have a threshold triggered by a decrease in beta power in the right temporal lobe only. This threshold would represent a single bit of information - scroll or don't scroll - which would be transmitted to a computer program (ex a mouse-wheel driver) that would then scroll the page accordingly.

With a single bit of information, I would only have the ability to scroll down at a fixed rate or pixel step. But I don't foresee it being too difficult to grow the project after I prove it with the single-bit MVP. If I can get a single bit, I'm sure I can get two. And if I get two, then I have four potential parameters with which to modulate the scrolling, which is probably more than enough. On/off, up/down. If I make it to three, I can even add fast/slow.

With current technology, we have the capability to measure changes in this voltage on the order of a thousandth of a seconds. Conduction of motor signals to an effector organ (i.e the right hand) is significantly slower. Neurotech thus has the capacity to sense your intention to move before you yourself are consciously aware of it, and I think I can apply this same concept to scrolling as well.

How much more immersive would your reading experience be if you never had to flip a page, or scroll with your mouse? Or, perhaps more importantly, how powerful could such a technology be to those who are physically incapable of moving their limbs, i.e a spinal cord injury (SCI) patient?
