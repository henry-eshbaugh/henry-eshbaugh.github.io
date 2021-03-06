---
permalink: /
title: "Nothing beats the smell of fresh hardware in the morning"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a programmer and electrical engineer with specific interest in embedded systems and instrumentation.

If you have any leads as to possible PhD projects in the spacecraft instrumentation or bioengineering fields, please don't hesitate to contact me at `he915@ic.ac.uk`!

Sorry for the wall of text - my eyesight is terrible (blind in an eye etc) and so have never been much of a visual person. Plus, technical accomplishments are difficult to describe without writeup. Now, excuse me while I talk about myself...

Spacecraft magnetometry
=====
In the summers, I work at the [Space Magnetometer Laboratory](http://www.imperial.ac.uk/space-and-atmospheric-physics/research/areas/space-magnetometer-laboratory/) as an [instrument engineer](http://www.imperial.ac.uk/space-and-atmospheric-physics/people/), with a focus on COTS anisotropic magnetorestive (AMR) sensor electronics for space weather applications, including the characterization of magnetic multipoles of interplanetary spacecraft, and scientific data from small, low-power, low-cost craft such as cubesats and nanosatellites.

Specifically, I work on [RadCube](https://www.radcube.hu/en/), a joint venture from the Hungarian Academy of Sciences Center for Energy Research (MTA EK) and the European Space Agency; the primary scientific payloads are MTA EK's particle sensor and our magnetometer. We are moving towards a critical design review in late 2018/early 2019 and delivery of the flight magnetometer next year; our launch is scheduled for 2020. I am responsible for the design and calibration of the electronics for the sensor, including scripting support software and interacting with contractors.

I have also spent time working on various other projects for the lab, including a fully-digital AMR sensor proof-of-concept (implementing the front-end analog signal chain on an FPGA), and various debug tools for the [JUpiter ICy moons Explorer (JUICE)](http://sci.esa.int/juice/) magnetometer (J-MAG); specifically, I designed a simulator board for the J-MAG instrument control board, featuring LVDS buffers and off-board connectors mimicking the design of the proper instrument, such that collaborating institutions (the University of Braunshweig, and the Austrian Academy of Sciences at Graz) could debug their hardware.

I have also developed a small but powerful Python framework called Magpie, which allows for easy management and live graphing of test data. This data is specified to arrive appended to CSVs; arbitrary transforms on the data can be specified, and particular data columns (or transforms thereof) can be redirected to graphs on a web page in an arbitrary layout. This framework relies heavily on the Bokeh framework; however, while Bokeh may need hundreds of lines of code to specify a single interface to test data, a quick script to serve such web pages amounts to a few lines of Python with the Magpie framework. Though initially developed for JUICE debugging two years ago, I am currently using this framework to test and calibrate the RadCube magnetometer.

I am a coauthor of two abstracts for presentations:

[1] Chiara Palla, Patrick Brown, Henry Eshbaugh, Tim Oddy, Jonathan P. Eastwood. *MAGIC: a miniaturised magnetometer for space weather monitoring with CubeSats* In: Open Source CubeSat Workshop. 2018.

[2] Chiara Palla, Patrick Brown, Henry Eshbaugh, Tim Oddy, Jonathan P. Eastwood. *Low resource magnetometer for space weather applications and implementation on RadCube*. In: European Space Weather Week (track: Space Weather Instrumentation). 2018.


Living Observatory
=====
While in high school, I participated in the [Living Observatory](http://www.livingobservatory.org/) project in Plymouth, Massachusetts. The site is a former large-volume cranberry bog, which was taken out of production and is now undergoing a process of ecological restoration into a wetlands habitat. Ordinary duties included botany - identifying and removing invasive plant species, work in a greenhouse, and so on. The site is a hotbed for ecological research; during my time there, I assisted in geohydrological surveys of the site, including OFDR distributed temperature sensing, well-water isotope sampling, and numerous other scientific tasks. I even got a [shout-out](https://scholarworks.umass.edu/cgi/viewcontent.cgi?referer=https://www.google.com/&httpsredir=1&article=1161&context=masters_theses_2) in the acknowledgements section of Danielle Hare's master's thesis!

As part of this experience, I spent time at the MIT Media Laboratory, where Gershon Dublon and Brian Mayton [were working on the Tidmarsh project](https://tidmarsh.media.mit.edu/) under Joseph Paradiso as PhD students. I assisted in the development and assembly of prototype sensor nodes deployed around the property. These nodes exist in a mesh network, and include various sensors of interest (volumetric water content of soil, temperature, humidity, ambient light, electrolyte sensors, etc). This experience was formative and pivotal to my decision to pursue electronics engineering in university.

Programming experience; personal and university projects
=====
I nagged my dad into buying my first textbook on programming (in the Python language) at the age of 12. I am something of a polyglot and have experience in many languages, including C/++, x86(-64)/ARM/AVR assembly languages, Java, Haskell, Common Lisp, F# (though, between you and me, I resent .NET), Bash, MATLAB/Octave, Julia, and more. Over my decade of programming experience, I have developed a knack for technical design, and can quickly spin new ideas into workable prototypes. I am most interested in firmware and low-level programming, including Linux kernel development. I have followed [LKML](https://lkml.org/) chatter at least weekly for the past eight years.

Speaking of Linux - I am a fanboy. I run [Arch Linux](https://www.archlinux.org/) with the [i3-gaps](https://github.com/Airblader/i3) window manager, using [pywal](https://github.com/dylanaraps/pywal) for terminal themes matching my wallpapers and [dunst](https://github.com/dunst-project/dunst) for notifications.

In terms of electronics CAD, I have a passionate love for KiCAD (and not just for my love of all things open-source), but have used Altium at the Mag Lab for a few years.


Virtualization obfuscation
-----
Interesting personal projects included an attempt at submitting a paper to DEF CON in the field of binary obfuscation. I was interested in virtualization obfuscation (in which machines are emulated, such that reverse engineers would have to understand both the target architecture and the emulated architecture in order to understand the functionality of the program) - specifically, my proposal was on the subject of recursive virtualization obfuscation - in which machines emulate machines emulating machines emulating machines, creating layers that must be peeled back before the reversing can conclude. The core goal of binary obfuscation, of course, is to frustrate your opponent - though such approaches are necessarily flawed, as with enough time, the program will be understood, the concept is to make the program much more frustrating to reverse than other programs. Indeed, virtualization obfuscation is presently employed on Blu-Ray players to protect their encryption schemes. A cornerstone of the project would be auto-generating random computer architectures with a template assembly language implemented in the flex/bison lexer/parser generator framework, and porting a fully-featured compiler back-end, such as LLVM, to such a "template" architecture. In this way, multiple different secret architectures could be created.

[My paper](https://github.com/henry-eshbaugh/henry-eshbaugh.github.io/blob/master/virtualization-obfuscation.docx) (regrettably written before I knew how to use LaTeX) was rejected; according to the referees, they prefer speakers to be 21+. However, one reviewer called the submission "bad-ass."

Real-time pitch identification via Fourier transforms: naive DSP
-----

The next year, for my high-school science fair project, I developed a program called GSynth, which sought to identify pitch in real-time from stringed instruments and emit MIDI data to a "plug-board" server such as JACK. I ran my bass guitar through an external amplifier into my computer's line-in; the samples were zero-padded, and Fourier transforms were taken. To eliminate the overtone series and isolate the fundamental frequency, the spectrum was downsampled by factors of two and three; these three resulting spectra were multiplied together to produce a large peak at the fundamental. A peak-detection algorithm then ran to identify the corresponding frequency and associate it with a musical note. Finally, the note was output to the JACK server as MIDI, into a DAW such as Ardour. The code was fully multithreaded (using the POSIX standard pthreads library - another reason I hate .NET and Windows programming in general, lack of POSIX compliance) and written in C for optimal performance, using a pipelined flip-buffer architecture. Even in such a Spartan, verbose language, the program was less than 1000 lines of code.

Though the program had much promise for electric guitars (which I did not test with), the key flaw in the plan was the tradeoff between latency and granularity of frequencies in the fast Fourier transform. Musicians need a low-latency signal path; however, such low latency means that notes which are close together in the frequency domain are difficult to discriminate. This was the conclusion of my science fair presentation; the reviewers were not happy, but my physics teacher was quite proud. I next encountered these results four years later, during my third-year digital signal processing module. Discussion with my professor has ignited interest in the so-called "zoom transform," which may produce better results.

I lost the paper, but while trying to find it, [I did stumble across the code](https://github.com/henry-eshbaugh/henry-eshbaugh.github.io/blob/master/gsynth.zip), or at least an old version of it. There are definitely problems (I cheesily wanted separate function names for each flip buffer to represent the fact that they were in separate subsystems - something I'd never do nowadays), but overall I am quite proud of the effort.

Education
=====
In high school, I completed 9 AP modules, earning '5's on each - in Calculus AB, Calc BC, Physics B, Physics with calculus: mechanics, Physics with calculus: electromagnetism, English literature, English language, US history, and Computer Science A (in the Java language). I completed coursework for a tenth (AP biology), but exam clash forced me to favor the Physics C papers. I was recognized as the top student in AP biology. I was active on the debate team - my best showing was breaking to quarterfinals at the NJFL national tournament in the 8th grade. I was also the news editor for the newspaper; I was awarded the American Scholastic Press Association award for outstanding non-school-related article, for my coverage of the shooting of Mike Brown in Ferguson, Missouri. I studied Latin for five years - obtaining three perfect papers and two gold medals on the National Latin Exam.

University projects
=====

Here's a picture of the [braille signer](https://github.com/henry-eshbaugh/henry-eshbaugh.github.io/blob/master/36632254_1709939089059111_6828926669823148032_n.jpg); the framework isn't rendering it like it's supposed to. Sorry!

In second year, I collaborated with a team to work on a tactile-braille-signing glove. The braille cell is made of six points, each indented or left flat, essentially encoding a chracter in six bits. With deaf-blind individuals, conversation proceeds via stimulation of six points in the hand. We built a small glove with motors to do this stimulation.

I take great responsibility for a major failure of the project - I was inexperienced with PCB design at the time, and attempted to solder the device together (using surface-mount 0603 resistors and SOT-23 transistors, not as an array, but as individual transistors) using large irons in the labs. Naturally, this ended quite badly. Due to funding limitations, we only had a single PCB; we also built the thing far too late, and at that point the turnaround time to a new PCB was past the deadline for the project. In proper student fashion, we hacked the circuit together on perfboard the night before the presentation with the nRF dev board (pictured). I am, by-and-large, responsible for this failure, and have learned from this experience the importance of time management and the dangers of hubris (my CAD skills were but fledgeling then).

I find this similar to the "hurry up and wait" phenomenon in movies - ensuring the work is done and ready to go weeks before the deadline is key, so manufacturing lead times can't disrupt the project, even with significant overruns.

In third year, I worked on a number of interesting courseworks. One included an IoT sleep monitor (we were randomly allocated an accelerometer); I pushed my group to develop our web end around Flask, such that raw/processed data could be trivially funneled into web pages using a RESTful API, thus greatly expanding the functionality of the device (from appliance monitor to networked electronic drum-head). In the same module, we implemented a motor controller that searched for nonces producing zeroes in SHA-256 hashes, a la Bitcoin mining - the idea was that the contradictory goals of real-time control and intense CPU demand would give a measure of the efficiency of the code.

Another included pipelining of a complicated floating-point expression including trigonometry within a sum, and a high (N>25,000) number of terms in the sum, on an FPGA - and integrating this sum with the Nios II soft processor. I was specifically interested in the evaluation of trigonometric functions in digital logic; I derived and implemented Chebyshev and Taylor series of the cosine function and evaluated them against the Verilog modules Alex had written for floating-point addition and multiplication - specifically, in their utilization of the FPGA's resources. Though slower to converge, the fixed-point CORDIC algorithm is far superior in this context, as the required floating-point hardware required for a fully-pipelined implementation (analytically determined by yours truly) was infeasible even for low-order expansions.

Finally, I self-proposed a Scheme interpreter (such are trivial to implement due to the simple nature of the syntax - Lisp can implement Lisp in some 200 lines) for a third-year functional programming module - I think Lisp (spoken of here as a monolithic entity, despite the multitude of dialects) is a beautiful language with an incredibly expressive syntax focusing on *homoiconicity* - that is, it is a language for operating on linked lists that is itself a notation for linked lists, and so it operates *on itself* ("metaprogramming") in a beautiful way. My experiences fooling around with the language (and perhaps some indoctrination into programming lore - including [the "Lisp Curse"](http://www.winestockwebdesign.com/Essays/Lisp_Curse.html), an accurate take that suggests that the language itself is so powerful that it discourages collaboration, thus hindering standardization and broad acceptance of techniques [1]) I wanted to implement a subset of [R7RS scheme](http://www.larcenists.org/Documentation/Documentation0.98/r7rs.pdf), specifically, which is small and well-defined - sample implementations under 500 lines of code are available online as proof of the viability of this idea. Unfortunately, my professor insisted that I was incapable of writing such a "difficult" program, and had our group implement an ARM assembler/emulator instead. So, I wrote another VM; in light of the virtualization obfuscation work I did in high school, this isn't particularly interesting.

I am still tremendously disappointed that I was prevented from pursuing this project.

[1] This cannot be understated; consider the Common Lisp Object System (CLOS), which, to date, is arguably the most (subjectively) beautiful implementation of object-oriented programming practices (concepts from which, e.g. multi-method dispatch over function calls as a way to do type-generic programming, have recently been revived in the wonderful [Julia language](https://julialang.org/), which I find superior to similar tools like MATLAB and Python). LISP was around 30 years before Alan Kay even coined the term OOP. The inherent mutability of the syntax enabled this to happen with relatively little work in the implementation - just a simple articulation of these syntactic ideas in *Lisp itself*.

Extracurricular activities & teaching
=====
After graduating from high school, I returned for a week over summer to teach a programming module - I had signed up to TA, but the teacher pulled out of the arrangement at the last minute. I did live-coding exercises in front of the group in the Processing "language" (it's more a Java framework focusing on visual programming for newbies). Interesting examples during the project included visualization of the Mandelbrot set (by evaluating the series and declaring divergence if the sum ended up greater than 16 - which gives surprisingly good results), and a numerical solver for the Lorentz attractor during a student-sparked discussion of chaos theory (those were some bright kids) - such is trivial if one is willing to reject the "abuse of notation" that is treating differentials as deltas, something physicists have no problem with doing.

As part of the experience, I would have remarkable lunchtime conversations with Mr Morehouse, the chemistry teacher at my high school. One I particularly remember regards my calculus teacher, Mr Foresta, who (as we both agreed) had the remarkable ability to "crystallize" concepts in people's minds, by trying plain-language explanation after plain-language explanation, each orthogonal to the last, until suddenly the concept would be plain as day in the eyes of the student. To date, he is the best teacher I've ever had, and his approach to teaching is something I very much hope to embody someday.

For the past two years, I have ran [ICSEDS Electronics](https://www.union.ic.ac.uk/guilds/icseds/projects/electronics/), the, um, electronics branch of the student space society at Imperial. Historically, we've been short on funding (usually scraping together a hundred quid or so from membership fees) - so instead, I've taken the opportunity to lecture a condensed series on electronics design, including explanations of common circuits and when they're used (H-bridges, how to wire up a microcontroller, etc). Next year will be the culmination of this effort; I am preparing lectures that delve deeply into the challenges of electronics in space, including the effects of radiation on semiconductor, heater control, space weather instrumentation, and so on. Last year, a third-year group project and a final year project (FYP) were obtained by working on a rover for competition. 

I am co-editor of the music section of *Felix*, Imperial's student newspaper. [My writing is available here](http://felixonline.co.uk/authors/he915/). Undoubtably the piece I am proudest of is [I, for one, hail our faceless corporate overlords](http://felixonline.co.uk/articles/2017-12-01-i-for-one-hail-our-faceless-corporate-overlords/), my five-star review of *Now That's What I Call Music! 98*.

Hobbies
=====
I've recently rekindled an old love of fiction with Thomas Pynchon's *Gravity's Rainbow*. I have great fondness for the works of Joseph Heller and Ernest Hemingway.

I am a philosophy nerd stemming from my debate days. I'm very interested in Marxist thought *with a mind towards its Hegelian/German idealist context* and particularly enjoy [the political/cultural theory of Slavoj Zizek](https://www.iep.utm.edu/zizek/), where he refines the classic conception of ideology as societal superstructure via a Hegelian reading of psychoanalyst Jacques Lacan; his works [The Sublime Object of Ideology](https://en.wikipedia.org/wiki/The_Sublime_Object_of_Ideology), [For They Know Not What They Do: Enjoyment as a Political Factor](https://philpapers.org/rec/IEKFTK), [The Parallax View](https://en.wikipedia.org/wiki/The_Parallax_View_(book)), and Absolute Recoil: Towards a New Foundation for Dialectical Materialism are my personal favorites. Fortunately, Zizek teaches across town at Birkbeck - I have a few friends there, and we enjoy going to the lectures and drinking together.

Netflix is great.
