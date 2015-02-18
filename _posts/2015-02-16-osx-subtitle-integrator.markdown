---
layout: post
title:  "OSX Subtitle integrator"
date:   2015-02-16 19:44:22
---

Based on Apple sample code, but modified in order to parse `.srt` subtitles, set language attribute and be used inside your project instead of being a command line tool.

`JAQSubtitlesTextReader` parses the `.srt` file:
{% gist 2f4276e296941a2a9461 %}
{% gist 968c4ae8e1f0377920ed %}

`JAQSubtitleIntegrator` gets the input, the subtitle filepath and the language and writes on the output the input file with the subtitle integrated:
{% gist 5fe742f6d1d780959554 %}
{% gist a9670082d2cdb603e139 %}