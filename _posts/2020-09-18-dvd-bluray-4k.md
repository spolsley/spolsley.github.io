---
layout: post
title:  "Upscaling from BluRay to 4K but What of DVD?"
date:   2020-09-18
categories: 
---

As an avid Star Trek fan, I was recently re-watching some of the TNG, DS9, and VOY series.  Comparing the BluRay release of TNG to something like the DVD version of VOY, I felt a bit sad that the latter has so much lower quality and [is unlikely to ever get a proper HD release](https://treknews.net/2017/02/02/why-ds9-voyager-not-on-blu-ray-hd/).

While the above article does a good job explaining several key factors of why we're unlikely to see a first-party BluRay release of Star Trek: Voyager (some of which we'll recap below), the more I contemplated this, I was left with the following question:

**If we see so many "[fake 4k](https://4kmedia.org/real-or-fake-4k/)" releases that are really just upscales from BluRay, why don't we see BluRays that are upscales from DVD?**

To answer this, let's discuss in three parts:

- Background explaining the terms
- The technology making BluRay to 4k possible
- The limits of DVD upscaling

As a bonus, there will be mention of a couple specific issues that call back to the above article regarding film vs. digital and post-processing.

## Background of Terms

Let's look at the relative sizes of DVD (in this blog, I will only consider what we call NTSC DVD format), BluRay (or standard HD), and 4k (I'll interchangeably say UHD / "Ultra" HD, even though there are mild aspect ratio distinctions from "true 4k").  We can see just how significant the differences in scale are, both visually and in terms of total numbers of pixels:

- DVD (NTSC: 480p): 720x480 = 345,600 pixels
- BluRay (HD: 1080p): 1920x1080 = 2,073,600 pixels
- 4k (UHD: 2160p): 3840x2160 = 8,294,400 pixels

<div style="text-align: center;">
<img src="{{ site.baseurl }}/posts/images/upscaling-hd-bluray/sizes_comparison.png" width="600" alt="A visualization that shows the comparison of the different sizes relative each other. 4k is the outer box, with BluRay being a smaller blue box in the lower right corner, and DVD is the much smaller black box in the lower right corner of both.">
</div>

<div style="text-align: center;">
<img src="{{ site.baseurl }}/posts/images/upscaling-hd-bluray/pixel_comparison.png" width="600" alt="A bar chart showing how the total number of pixels grows from DVD to 4k, going from about 300 thousand to over 8 million.">
</div>

Actually, even though 4k looks like a significant jump on this linear chart, it's "only" 4x the number of pixels of BluRay, while BluRay is 6x the number of pixels of DVD.  If we plot this on a logarithmic scale, we can see how the differences are not that extreme, but the slightly larger gap between 1080p and 480p is a bit more apparent:

<div style="text-align: center;">
<img src="{{ site.baseurl }}/posts/images/upscaling-hd-bluray/logpixel_comparison.png" width="600" alt="On a log scale, we see values of 5.5, 6.3, and 6.9 for DVD, BluRay, and 4k, respectively">
</div>

## Core Technological Distinctiveness

Beyond just the number of pixels, there are several key features of BluRay that offer advantages over DVD.  BluRay generally uses the superior H.264 compression format versus MPEG-2 compression found in DVDs.  It uses 10 bits for color encodings versus 8.  It also has better dynamic range for color and higher [chroma subsampling](https://en.wikipedia.org/wiki/Chroma_subsampling) (typically 4:4:4 or 4:2:2 as opposed to 4:2:0 in DVD).

4k UHD is much more similar to BluRay technologically, e.g., rich color encodings and dynamic ranges, which make it relatively easier to "upscale" HD to UHD.  In fact, as referenced above, it is common practice to upscale 4k releases, and there exist [entire websites](https://4kmedia.org/real-or-fake-4k/) devoted to tracking real or fake (upscaled) 4k.

Most people don't readily notice the difference!  In a [study by Puget Systems](https://www.pugetsystems.com/labs/articles/can-you-see-the-difference-with-a-4k-monitor-729/) looking at a variety of monitor resolutions, the authors examined different ideal viewing distances for resolutions versus visual acuity.  For the best vision they considered, 20/30, they recommend a viewing distance of 42 inches for 4k screens.  When we contextualize this with the fact that most people mount their TV screens farther from them than their monitors, we begin to see how the density of 1080p versus 2160p becomes less critical in a TV.

## Limits to DVD Upscaling

So a lot of it comes down to the vast differences in technology and the raw amount of content.  BluRay and 4k are fairly compatible aside from pixel density, while DVD has so many compression issues.

Still, we're just talking 6x versus 4x upscales, right?  Well, the last critical piece to consider is just how much information is stored in the original medium.  This [CNET article by Geoffrey Morrison](https://www.cnet.com/tech/home-entertainment/can-4k-tvs-make-1080p-look-better/) does a good job of visualizing just how much data is lost in a DVD master.

<div style="text-align: center;">
<img src="{{ site.baseurl }}/posts/images/upscaling-hd-bluray/upscale_example.png" width="600" alt="A snippet from a CNET article demonstrates that the 1080p version of an image of a starry night is rich with data, while the 480p compressed version loses a vast amount of visual data">
</div>

Credit: [Geoffrey Morrison](https://www.cnet.com/tech/home-entertainment/can-4k-tvs-make-1080p-look-better/)

## Closing Comments

A closing question may be: why is it easy to make HD versions of very old content, like TOS, but not for newer shows like DS9.  This gets to the differences of film vs. digital and post-processing.  Film doesn't have an exact resolution but has more definition than a 480p NTSC master, such as the versions made to process visual effects for television broadcast.  This is why The Original Series of Star Trek (all shot in camera) could just be rescanned at a higher definition from film, but The Next Generation required both rescanning film and re-rendering certain digital effects.  The later shows become even more effects heavy!  Robert Meyer Burnett does a good job covering these aspects in the [Trek News article](https://treknews.net/2017/02/02/why-ds9-voyager-not-on-blu-ray-hd/), and they are generally true of most media during the early digital era.

**At the end of the day, to address our core question, DVD is sadly too limited to easily upscale and create something as visually appealing as BluRay.**  I predict we'll continue to see more "fake" 4k upscales, but we'll never see first-party HD releases from DVD upscales in the same way, although perhaps AI will change that in the future.

On that note, we do have a huge library of training data between the original TOS and TNG DVD releases and their corresponding BluRays.  Theoretically, one could train a specialized "Star Trek" upscaler matching the overall franchise visual tone to create HD versions of DS9 and VOY.  Depending on how AI upscaling progresses, perhaps we'll see this happen some day... until then, I'll continue to enjoy Star Trek in the forms we have!