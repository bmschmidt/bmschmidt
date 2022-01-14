---
title: Sonic Word Clouds - a Digital History Project
authors:
- Daniel Ruten
layout: post
categories: posts
date: 2017-06-19
---

My name is Daniel Ruten, and I have just finished my undergraduate studies majoring in History at the University of Saskatchewan. During my last term, I took a course on Digital History (HIST396) with Dr. Jim Clifford. In it, I became familiarized with the various emerging digital tools and methodologies that are becoming increasingly important for historians to learn. The course also required that I create some kind of digital history project myself. For my project, I took inspiration from one lesson in particular featured on the Programming Historian website: [historian Shawn Graham’s lesson on data sonification](/lessons/sonification). Building off of what this lesson taught me, I developed my own method to represent and analyze textual data through sound, which I have termed Sonic Word Clouds. In this post I will briefly explain this method of sonification, while reflecting a bit on the learning process that both inspired the idea for this project and allowed me to make it a reality.

At first, I was somewhat at a loss of what I should do for my digital history project. While scanning the various lessons on the Programming Historian website in order to get some ideas, one lesson in particular caught my eye. It was entitled “The Sound of Data (a gentle introduction to sonification for historians),” by Shawn Graham. I hadn’t really known that data sonification was a thing, much less a method that could be used by historians, and so my curiosity was piqued. In [the lesson](/lessons/sonification), Graham provides an introduction to the theory of data sonification, before detailing some of the sonification methods and resources that are available to historians. In particular, he discusses some methods to convert historical data into MIDI notation that can then be mapped to instrumentation. Some of these tools, such as [Musicalgorithms](http://www.musicalgorithms.org/3.2/) and the [MIDITime package for Python](https://pypi.python.org/pypi/miditime), were particularly designed with time-series/quantitative data in mind. But Graham also provides an example of the potential of MIDITime to analyze historical texts, as he uses it to sonify topic modelling data from John Adams’ diaries. By [mapping the resultant MIDI data to different instruments in Garageband](https://www.youtube.com/watch?v=ikqRXtI3JeA&feature=youtu.be), he offers us a means to hear the relative occurrence of different topics in the diaries over a 50-year period. Being able to listen to the relations between these different concepts over time this way provided a very unique and intriguing representation of a textual narrative. As Graham emphasizes, the choices one makes regarding how to represent data sonically in this fashion reveal the ways in which we privilege, condense and transform information as historians. The lesson gave me an idea: what if there was a way to sonify this kind of textual data in a more readily intelligible way? This set the stage for my own project.

The idea for my project was essentially to develop a method to take a given historical text, determine the 25 most frequent words in it, and then use MIDITime to convert each word’s occurrences throughout the text into MIDI data. From there, all 25 resultant MIDI files would be brought into music sequencing software and mapped to instrumentation. Up to this point, the idea is very similar to what Graham demonstrated in the lesson. The key difference is that instead of using conventional instruments, I planned to assign the MIDI data to samplers.  (A [sampler](https://goo.gl/1nfuuo) is a kind of digital instrument that plays back any audio file that is loaded into it.) From there, each sampler would be loaded with a Text-to-Speech audio file of its corresponding word. The MIDI notation would then tell each sampler when to trigger its spoken word, corresponding to the occurrences of the word in the text. When all of this is combined, then, we would be able to hear the linear frequency of multiple spoken words over time in a text in a sort of sonic word cloud, thus quickly getting a sense of both shifting patterns of common word usage as well as the relations between the usage of different words over time.

In making this idea a reality, the most daunting part was becoming familiar enough with the programming language Python to code a script that could take care of the first half of the project. In the end, through lessons on the Programming Historian and [Codecademy](https://www.codecademy.com/), a bunch of threads on [StackOverflow](https://stackoverflow.com/), and lots of trial-and-error, I was able to put together a Python script that takes a given text file and quickly outputs both MIDI files (using MIDITime) and text-to-speech audio files (using [Google Text-to-Speech](https://pypi.python.org/pypi/gTTS)) for each of the 25 most common words in the text. From there, these files just had to be combined in music sequencing software, which I did using [Ableton Live](https://www.ableton.com/en/live/) and its built-in Samplers. It took some time to refine this vital second half of the process, but I eventually managed to reach a point where I was reasonably happy with the result. I first tested this method out on a WWI soldier’s war diaries, and here is the resultant Sonic Word Cloud:

<iframe width="100%" height="450" scrolling="no" frameborder="no" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/317630807%3Fsecret_token%3Ds-ncIEE&amp;auto_play=false&amp;hide_related=true&amp;show_comments=true&amp;show_user=false&amp;show_reposts=false&amp;visual=true"></iframe>

Through this method of data sonification, one can quickly get a sense of the broad patterns of common word usage in a given historical text. Furthermore, one can also hear the relations between the usage of different words in the text over time. The temporal linearity inherent to forms of sonic representation means that aspects of textual narrative are preserved in Sonic Word Clouds to an extent unmatched by visual word clouds. The ability to hear not only broad trends, but also the outliers in word usage could also lend sonic word clouds a potential advantage over comparable forms of data visualization.

Overall, I have learned a lot throughout the process of putting this project together. First, I have learned valuable skills in basic coding and text mining, skills that are more useful than ever for historians to become familiar with. Second, I have learned firsthand some of the difficulties and limitations involved in techniques of distant reading, specifically in regards to how they decontextualize textual data. This has instilled for me that digital tools should always be used with a strong awareness of their limitations. Finally, I found myself having to make choices of how to filter, organize and transform data in order to sonically represent it in a more useful and comprehensible fashion. For instance, I had to decide what stopwords to ignore in texts (I ended up including numbers and certain generic verbs in addition to the typical 'a', 'the', etc) so that the twenty-five words represented in the sonic word cloud would be more useful for analysis. I also gave each word a separate panning position in the stereo field in order to make the sonic word clouds more comprehensible; the decisions of 'where' to group different words together in the stereo field could potentially influence how the end result is processed and interpreted. These decisions highlight the process of how we as historians privilege certain types of information, organize it and decide what is and is not significant to convey. All of this has reinforced for me Shawn Graham's original point in the lesson regarding sonification's value as a reflective exercise for historians, whose novelty can reveal both patterns of data and patterns of practice that we typically would not recognize in a more familiar context. In any case, I enjoyed the process of learning and navigating these challenges as I put the project together.


A more in-depth explanation of the project can be found in this series of blog posts:

[Sonic Word Clouds: An Experiment With Data Sonification](https://danielruten.wordpress.com/2017/04/15/sonic-word-clouds-an-experiment-with-data-sonification-part-i-introduction/)