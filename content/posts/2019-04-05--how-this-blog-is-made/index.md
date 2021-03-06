---
title: How this blog is made
tags: ["meta", "how-to", "web", "i-made-thing"]
cover: paul_zoetemeijer_machinery.jpg
author: atte juvonen
---

<re-img
    src="paul_zoetemeijer_machinery.jpg"
    title="Photo by Paul Zoetemeijer on Unsplash"
    href="https://unsplash.com/photos/QuiM1c65QM4"
    >
</re-img>

<<<<<<< HEAD


=======
>>>>>>> develop
### Why this blog is statically generated

GatsbyJS is a static web site generator. This means that my blog is generated into HTML,JS,CSS at _build time_ and I don't have a costly server dynamically generating pages. The main advantages of a static site generator are:
- Hosting the blog **costs nothing** at providers like Netlify
- Improve loading times to most places on earth because assets can be **delivered by CDN** (instead of a single server in a single location, you have many servers in many locations and any request is routed to the nearest one).
- **No server maintenance** is required

I write my blog posts in **Markdown**. It's really easy to format and my content will not be married to any platform. For example, if I want to ditch Gatsby in the future and create my own static site generator, I can do that knowing that transforming Markdown isn't going to give me too much trouble.

### Why GatsbyJS specifically

There are many static web site generators out there. I didn't do a comparison. I like that Gatsby is made for React (instead of reinventing the wheel in that aspect). Their developer community seems active and friendly. But the main thing that attracted me to Gatsby was its promise of delivering performance out of the box. If you have any non trivial website and you want good performance, you have to do a ton of optimizations to get that. The idea that a framework can do those optimizations for you is really appealing. Gatsby does a lot of cool things, but this promise didn't really turn out to be true (I ended up spending a lot of time optimizing the performance and some things still don't work as they should. For example, Gatsby generates duplicates of some images, so when an image is used on multiple pages, the user downloads the same image multiple times from different paths without leveraging browser's cache). Despite its faults, this site now has pretty sweet performance with the help of Gatsby:
- The website is **visible and functional after only 1 round trip and ~20kB of data**.
- Internal links are prefetched on hover, giving the UX that **subsequent pageloads load instantly**.
- Autogenerated **tracedSVG image placeholders** are stylized to create a smooth look and transition as the image loads without the page jumping around.
- **Also works for users who have JS disabled**. A static version of the website is generated, which is rendered on first load, and then the page is hydrated into React (for users who have JS).

On one hand I want to try making my own static site generator after tinkering so much with Gatsby. On the other hand I'm really excited to see what the future holds for Gatsby and where the developers will take it within a few years.