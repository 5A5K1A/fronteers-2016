## Notes on [FRONTEERS Conference 2016](https://fronteers.nl/congres/2016)

Follow on [twitter](https://twitter.com/FronteersConf)<br>
Listen to [soundtrack for Fronteers Conference 2016](http://track.ml.mailersend.com/link/c/YT00NzAxNDgxMzY0NTk4MzA0OTkmYz1wNmgxJmU9NDM3MTgyNyZiPTYzNDgxNzQxJmQ9cThuN3g0Yw==.NqCGWBgCoZvcS8qpwJDc9b7JIyrI4lGHBGQ5fagBx9k)

**Thursday October 6, 2016**
* [Progressive Enhancement and CSS - Ire Aderinokun](#06-0900)
* [Hacking the Visual Norm - Nadieh Bremer](#06-0950)
* [How You Do What You Do Is Who You Are - G. Scott Olson](#06-1110)
* [Offline, Progressive, and Multithreaded: a Peek at the web apps of the future - Nolan Lawson](#06-1200)
* [Multi-user WebVR or: Wait, Who Are These People? - Martin Splitt](#06-1350)
* [Big Data, Big Impact - Lodewijk Nauta](#06-1440)
* [Scaling Front End Development - Monika Piotrowicz](#06-1600)
* [Surveying the Landscape - Peter Gasston](#06-1650)

**Friday October 7, 2016**
* [Adapting to Input - Jason Grigsby](#07-0900)
* [Cheat Sheet to a Lean Website - Barbara Bermes](#07-0950)
* [Building Responsive CSS Components - Zell Liew](#07-1110)
* [CSP STS PKP SRI ETC OMG WTF BBQ - Scott Helme](#07-1200)
* [Functional Animation - Sarah Drasner](#07-1350)
* [World-Wide Web, not Wealthy Western Web - Bruce Lawson](#07-1440)
* [Technologic (Human Afterall): Accessibility Mix - Léonie Watson](#07-1600)
* [Joining Up the Dots - Heydon Pickering](#07-1650)

<a name="06-0900"></a>
## What about CSS? Progressive Enhancement and CSS - Ire Aderinokun
> __Ire Aderinokun__ |
 [Twitter](https://twitter.com/ireaderinokun) |
 [GitHub](https://github.com/ireade) |
 [Website 1](https://bitsofco.de/) & [Website 2](https://ireaderinokun.com/) |

> _When we speak of Progressive Enhancement, we usually talk about making our sites functional with limited or no Javascript. But what about CSS? Progressive enhancement is about taking into account the sometimes limited capabilities of browsers, and this includes their support for CSS features._

> _In this talk, we go over the difficulty of writing progressively enhancive CSS, and some tips on how to overcome it._

[Inclusive Web Design for the Future - Stephen Champeon (at SXSW)](http://hesketh.com/publications/inclusive_web_design_for_the_future/)<br>
Problems graceful degredation (according to this talk)
- Doesn't straddle technology inflection points well
- Many designers only test one version back
- Does not address the different needs of different audiences
- It's expensive to retrofit to new alternative devices
- Whatever is 'good enough' usually rules

### 5 Guidelines for Progressive Enhancement
- Basic content and functionality should be accessible to all web browsers.
- Sparse, semantic markup should contain all content. Content should be defined in plain text in the markup.
- Enhanded layout can be provided by CSS stylesheets.
- Enhanced behavior can be provided by unobtrusive JS.
- End-user web browser preferences should be respected.

More browsers, versions, technologies, people online

### Progressive Enhancement & JS
- Make the website functional without JS.
- Detect feature support.<br>
```javascript
if( 'service worker' in navigator ) {
	// Do stuff with service worker
}
```
- Polyfill unsupported features.<br>
```javascript
if( !('Promise' in self) ) {
	loadScript('promise-polyfill.js')
}
```

### Progressive Enhancement & HTML
- Add aria roles<br>
`<header role="banner">`<br>
`<main role="main">`

selector, property & value

### Progressive Enhancement & CSS
- Start with sensible HTML<br>
Progressive Enhancement M&M (Dave Stewart)
[![alt text](http://alistapart.com/d/understandingprogressiveenhancement/m-m.jpg "http://alistapart.com/d/understandingprogressiveenhancement/m-m.jpg")](http://alistapart.com/article/understandingprogressiveenhancement)

- Take advantage of the cascade (fallback eerst declareren)
- Go "mobile-first"<br>
min-width > max-width<br>
start with `%`, later one can use `px`
**Read more:** [How to be Successful with Responsive Sites ](http://www.slideshare.net/Koombea/how-to-be-successful-with-responsive-sites-koombea-nginx-english)

- Use flexblox<br>
first `display: table-cell;`<br>
later `display: flex;`

- Seperate stylesheets<br>
Last resort<br>
**Read more:** [BBC News on responsive design](http://responsivenews.co.uk/post/18948466399/cutting-the-mustard)

### What about feature queries?
```css
@supports ( display: flex ) and/or ( /* something */ ) {
	.foo { display: flex; }
}
```
```css
@supperts not ( display: flex ) {
	.foo { display: table; }
}
```

CanIUse.com says one cannot use this in IE and Opera Mini<br>
Other browsers/versions DO support `@support`<br>
**Read more:** [Jen Simmons - Using feature queries in CSS](https://hacks.mozilla.org/2016/08/using-feature-queries-in-css/)

Use feature queries as a progressive enhancement; make use of the cascading effect of CSS and code with a fallback.

**Slides: 	[speakerdeck.com/ireade](https://speakerdeck.com/ireade/what-about-css-progressive-enhancement-and-css)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194815985)**

============================================================
<a name="06-0950"></a>
## Hacking the Visual Norm - Nadieh Bremer
> __Nadieh Bremer__ |
 [Twitter](https://twitter.com/NadiehBremer) |
 [GitHub](https://github.com/nbremer) |
 [Béhance](https://www.behance.net/nbremer) |
 [Website](http://www.visualcinnamon.com/) |

> _There are so many visualization tools out there today, most with a pre-made set of charts. But trying to wrangle your data to fit (uncomfortably) into the default charts is not the right mindset. Adjust the visual to your data, not the other way around. You don't necessarily have to be a code wizard to let your creativity run free. Even with the defaults, you can become creative by using them in a different way, combining layouts or chart types to create something new, or even changing small pieces of code from existing visualization frameworks._

> _During this talk, Nadieh will take you through several of her data visualization projects, both from the business environment of her day job and the experiments made in her evenings. Hopefully, by the end you’ll want to step outside of your "visualization" comfort zone and create (custom) charts that best display the insights in the data._

Amazing data visualisation skills!!

Worked at [Adyen](https://www.adyen.com/).<br>
Uses [voronoi diagrams](https://en.wikipedia.org/wiki/Voronoi_diagram).<br>
Collaborates with [Shirley Wu](http://sxywu.com/) on [data sketch|es](http://www.datasketch.es/).<br>
**To do:** check out [D3.js](https://d3js.org/) and [bl.ocks.org](https://bl.ocks.org/)

**Slides: 	[nbremer.github.io/hackingthevisualnorm](https://nbremer.github.io/hackingthevisualnorm/)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194817475)**

============================================================
<a name="06-1110"></a>
## How You Do What You Do Is Who You Are - G. Scott Olson
> __G. Scott Olson__ |
 [Twitter](https://twitter.com/gscottolson) |
 [GitHub](https://github.com/gscottolson) |
 [Website](https://paper.fiftythree.com/scott) |

> _React JS makes it easy to build rich, maintainable web applications. But once you are up and running, there are a handful of less-documented tweaks that you can implement to improve the UX and DX of your project._

> _Over the past 2.5 years, my team at FiftyThree has been building and maintaining the React web experience for [Paper](http://paper.fiftythree.com). We have focused our energy to make developing and using our React app more enjoyable for everyone. Preloading images, optimistically rendering the user interface and linting your code may sound like small details, but adding them up can drastically improve how users and fellow developers perceive of your app. We have been in the trenches, fighting the good fight, and now I’m ready to share our successes, mistakes and experiences._

Some nifty stuff & gadgets: [Paper](https://www.fiftythree.com/paper), [Pencil](https://www.fiftythree.com/pencil) and [Mix](https://www.youtube.com/watch?v=BjKtCyXNSTg) \#like

Which parts need to be seamless, and for which pages it is OK to have a full refresh. How to manage placeholders in React. Also read the [blogpost on this matter](http://making.fiftythree.com/fluid-text-inputs/).<br>
Seen from a **a11y** point of view, this isn't really the best solution though :-(

**Slides: 	...**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194830777)**

============================================================
<a name="06-1200"></a>
## Offline, Progressive, and Multithreaded: a Peek at the web apps of the future - Nolan Lawson
> __Nolan Lawson__ |
 [Twitter](https://twitter.com/nolanlawson/) |
 [GitHub](https://github.com/nolanlawson) |
 [Website](https://nolanlawson.com/) |

> _In recent years, the web has been evolving at a blistering rate. Phrases like "progressive web app", "offline-first", and "server-side rendering" are tossed around with abandon. What are all these technologies, though, and why should we care?_

> _In this talk, I'll explore work that's being done in open-source JavaScript tooling to make the web faster, more responsive, and more reliable, as well as a glimpse under the covers of the Edge browser, and how we plan to ride this wave in the coming years._

Factors to keep in mind when building an application:
* Offline
* Progressive
* Multithreaded

### Offline
Build websites offline first. Not only for people in metros or planes.
Use of local cache makes site faster.<br>
[Latency numbers every programmer should know](https://gist.github.com/hellerbarde/2843375)

### Progressive
"In 2016, it's okay to build a website that doesn't work without JavaScript."<br>
Loads of big sites don't work with JS.<br>
> Video: **Tom Dale - Responsive Field Day 2015**<br>
> [![Tom Dale - Responsive Field Day 2015](http://img.youtube.com/vi/puOrC7cfjRI/0.jpg)](https://youtu.be/puOrC7cfjRI)

### Multithreaded
Why? Janky/slow... Mobiles nowadays have 4+ cores, so let's make use of that.

> Video: **Nordic.js 2016 • Evan You - Demystifying Frontend Framework Performance**<br>
> [![Nordic.js 2016 • Evan You - Demystifying Frontend Framework Performance](http://img.youtube.com/vi/Ag-1wmHWwS4/0.jpg)](https://youtu.be/Ag-1wmHWwS4)

Excerpt: "Offline first!"

**Slides: 	[nolanlawson.github.io/fronteers-2016](https://nolanlawson.github.io/fronteers-2016/#/)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194834593)**

============================================================
<a name="06-1350"></a>
## Multi-user WebVR or: Wait, Who Are These People? - Martin Splitt
> __Martin Splitt__ |
 [Twitter](https://twitter.com/g33konaut) |
 [GitHub](https://github.com/AVGP) |
 [Website](http://geekonaut.de/) |

> _Thanks to WebGL we've got interactive 3D content with the ease-of-use and the openness of the Web. Add WebRTC on top of that and we'll see interesting collaborative applications that play out in three-dimensional space right from within our browsers. Paraphrasing the movie Tron: “But then, we got in”. WebVR allows us to hook up the browser to a new universe of VR hardware and immersive experiences._

> _Let's explore what we can do together by combining the technologies to create a universe that we can explore together and what is yet uncharted land that we can discover._

Cool VR stuff & lots of demo's \#like

Links/ things to try out:
- [webvr.info](https://webvr.info/)
- [A-Frame](https://aframe.io/)
- [SceneVR](http://www.scenevr.com/)
- [Archilogic](https://spaces.archilogic.com/)
- [Sketchfab](https://sketchfab.com/)

**Slides: 	[docs.google.com](https://docs.google.com/presentation/d/1h1JeRFoxL_Vp4hFQrsqvGe-tM-02PPMG5p9tBwpW-bQ/edit)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194875227)**

============================================================
<a name="06-1440"></a>
## Big Data, Big Impact - Lodewijk Nauta

> _Using examples from real life Big Data cases Lodewijk Nauta is going to talk about how his team made a bigger impact at their clients by changing the way they presented their results. When your clients want their business to evolve towards a more data-driven way of operating, the delivery of visualizations has to evolve as well. The data that is used in the analyses includes fitbit movement data, email usage but also tracking how people move through a restaurant._

Basically just a sales pitch for KPMG<br>
(a rather poor one in my opinion: it lacked in decent research - not factoring in all the usefull elements - & was filled with random assumptions and conclusions)

**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194877685)**

============================================================
<a name="06-1600"></a>
## Scaling Front End Development - Monika Piotrowicz
> __Monika Piotrowicz__ |
 [Twitter](https://twitter.com/monsika) |
 [GitHub](https://github.com/mpiotrowicz) |

> _As a discipline, front end development (FED) has recently seen enormous growth with new focus areas like performance, design patterns, build tools, and frameworks emerge and mature. There’s a lot of new excitement for all things client-side, but how do these new technologies fit alongside a traditional Engineering team and an existing code base?_

> _At Shopify, we’ve been exploring the dynamic more closely as our FED team continues to grow company-wide. In this talk, I will share my perspective on how FED can work alongside other disciplines to form robust, creative product teams at scale. Shared tools like coding standards, processes, and style guides, can make it possible for all developers to confidently build UI, while specialist FED build those systems and solve unique use cases. By investing in in tools and process, we’ve been able to find common focus for our team and a stronger understanding of our role across disciplines._

### Defining FED
Front end nowadays is so much more than just `HTML`, `CSS` and `JavaScript`.

### Building a Craft
**1) Language styleguides**
- Shared coding standards
- Consistency is key
- Helps team members read each other’s code
- Helps you read your own code 6 months from now

Examples:
- http://cssguidelin.es/
- http://sass-guidelin.es/
- https://github.com/Shopify/javascript
- https://github.com/rwaldron/idiomatic.js/
- https://google.github.io/styleguide/javascriptguide.xml

**2) Code reviews**
- Support & grow your guide
- Standards to make things easier
- If hard to enforce, it might not be useful
- Shared deﬁnition of quality
- Builds a culture of feedback and knowledge sharing

**3) Pattern libraries**
- A way to pool our efforts
- Make it possible to share code automatically
- A starting point for new projects

Think about:
- A common stack(s)
- Responsive guidelines - easy defaults for breakpoints, ﬂexible grids, starting points for styling and behavior, testing standards
- Performance standards & language tooling
- Accessibility best practices

### Building a Culture
- Have more conversations
- Continue to scale
- Find & follow opportunities for impact

Excerpt: "Teach, build, review."

**Slides: 	[slideshare.net/mpiotrowicz](http://www.slideshare.net/mpiotrowicz/building-scaling-a-front-end-practice-team)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194961049)**

============================================================
<a name="06-1650"></a>
## Surveying the Landscape - Peter Gasston
> __Peter Gasston__ |
 [Twitter](https://twitter.com/stopsatgreen) |
 [GitHub](https://github.com/stopsatgreen) |
 [Website](https://www.broken-links.com/) |

> _As it approaches a degree of maturity as a telecomms channel, the web is going through some changes. Using extensive reference and research, Peter will be taking a big-picture view of some of the trends in publishing and information consumption on the web, looking at the demands of the millions of new users in emerging markets, and the way that technology is adapting to accommodate them._

> _This talk will raise and try to answer questions such as: what is the role of the web in the new landscape? And what are the threats to, and opportunities for, the open web and web development?_

...

**Slides: 	[speakerdeck.com/stopsatgreen](https://speakerdeck.com/stopsatgreen/surveying-the-landscape-fronteers)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194961226)**

============================================================
<a name="07-0900"></a>
## Adapting to Input - Jason Grigsby
> __Jason Grigsby__ |
 [Twitter](https://twitter.com/grigs) |
 [GitHub](https://github.com/grigs) |
 [Website](https://cloudfour.com/thinks/) |

> _Responsive Web Design has forced us to accept that we don't know the size of our canvas, and we've learned to embrace the squishiness of the web. Input, it turns out, is every bit as challenging as screen size. We have tablets with keyboards, laptops that become tablets, laptops with touch screens, phones with physical keyboards, and even phones that become desktop computers._

> _In this session, Jason will guide you through the input landscape, showing you new forms of input like sensors and voice control, as well as new lessons about old input standbys. You'll learn the design principles necessary to build web sites that respond and adapt to whatever input people use._

...

**Slides: 	[speakerdeck.com/grigs](https://speakerdeck.com/grigs/adapting-to-input)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194967832)**

============================================================
<a name="07-0950"></a>
## Cheat Sheet to a Lean Website - Barbara Bermes
> __Barbara Bermes__ |
 [Twitter](https://twitter.com/bbinto) |
 [GitHub](https://github.com/bbinto) |
 [Website](http://www.bbinto.me/) |

> _Barbara recently published her first book ”Lean Websites”. Her talk focuses on one of the most important chapters of the book called ”Performance Cheat Sheet”, a set of about dozen exercises to guide you in practicing web performance. Barbara believes that the more frequently you apply these tips, the better you’ll get at mastering performance issues and creating fast, and lean websites._

> _Join Barbara’s talk to learn more about these tips, as well as the performance point system, and how to split your website into measurable performance modules._

Excerpt: "Buy the book."<br>
More info: [Other talk from Barbara on energy efficient websites](http://www.slideshare.net/bbinto/building-energyefficient-websites)

**Slides: 	[slideshare.net/bbinto](http://www.slideshare.net/bbinto/cheat-sheet-to-a-lean-website)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194962379)**

============================================================
<a name="07-1110"></a>
## Building Responsive CSS Components - Zell Liew
> __Zell Liew__ |
 [Twitter](https://twitter.com/zellwk) |
 [GitHub](https://github.com/zellwk/) |
 [Website](https://zellwk.com/) |

> _In an age of responsive websites, learning how to build components that can be reused in multiple areas without adding much complexity to your code is crucial._

> _Have you wondered how it is possible to accomplish this feat in pure CSS without making your CSS into a bloated mess of hacky code? What naming conventions should you use? How do you structure and code your CSS? How do you deal components that have to be placed in wildly different areas?_

> _In his talk, Zell aims to share with you his experiences and approach on building responsive, reusable components. He goes deep into the granular level (and even discusses what units he recommends you to use)._

`rem` versus `em`
- `rem` is based on root font size (of the body)
- `em` is based on the containing element

**Slides: 	[github.com/zellwk](https://github.com/zellwk/responsive-css-components-slides)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194962824)**

============================================================
<a name="07-1200"></a>
## CSP STS PKP SRI ETC OMG WTF BBQ - Scott Helme
> __Scott Helme__ |
 [Twitter](https://twitter.com/scott_helme) |
 [GitHub](https://github.com/ScottHelme) |
 [Website](https://scotthelme.co.uk/) |

> _The sane version of my talk title would be 'Modern Web Security Standards' but I wanted to make light of the fact that sometimes there can be too many to keep up with._

> _In this talk I'm going to introduce you to some awesome features that allow us to quickly and easily boost security and offer better protection to our visitors. From mitigating Cross-Site Scripting (XSS) to enforcing the use of HTTPS or protecting ourselves against rogue Certificate Authorities and Content Delivery Networks, these are just some of the things that are possible._

> _If you were to implement even one of the standards I'm going to talk about today, you'd probably be doing better than your bank!_

...

**Slides: 	[CSP STS PKP SRI ETC OMG WTF BBQ.pdf](https://scotthelme.co.uk/static/talks/CSP%20STS%20PKP%20SRI%20ETC%20OMG%20WTF%20BBQ.pdf)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194961863)**

============================================================
<a name="07-1350"></a>
## Functional Animation - Sarah Drasner
> __Sarah Drasner__ |
 [Twitter](https://twitter.com/sarah_edo) |
 [GitHub](https://github.com/sdras) |
 [Codepen](http://codepen.io/sdras/) |
 [Website](http://sarahdrasnerdesign.com/) |

> _Animation is captivating. Our brains are trained to respond most intently to movement. For this reason, animation in a user experience is extremely important, and also very easy to overdo. Carefully considered animation can compose spatial maps to guide users. Animations can be responsive, resolution-independent, and make a site function intuitively._

> _In this session Sarah will cover a myriad of use cases, from both design and technical implementation standpoints._

...

**Slides: 	[slides.com/sdrasner](http://slides.com/sdrasner/functional-fronteers#/)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194963386)**

============================================================
<a name="07-1440"></a>
## World-Wide Web, not Wealthy Western Web - Bruce Lawson
> __Bruce Lawson__ |
 [Twitter](https://twitter.com/brucel) |
 [GitHub](https://github.com/brucelawson) |
 [Website](http://www.brucelawson.co.uk/) |

> _As the population and economies of the West stay static, the developing economies are seeing huge expansion, and a rising youthful population that have grown up with the Web. But there are challenges to web access in Asia and Africa that we need to understand if we want to reach the next 4 billion people with fast, performant sites._

> _Bruce will bring facts and figures from his years living in Asia and from working for Opera (often the only browser that people can use) to show you how to bring your brands to new markets._

![alt text](https://img.buzzfeed.com/buzzfeed-static/static/2015-02/27/15/enhanced/webdr14/anigif_enhanced-14643-1425068912-32.gif "You've been rickrolled! :-)")

Just watch the [video](https://youtu.be/uqVRz8CteAg)

**Slides: 	[speakerdeck.com/brucel](https://speakerdeck.com/brucel/parisweb-paris-30-september-2016)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194968584)**

============================================================
<a name="07-1600"></a>
## Technologic (Human Afterall): Accessibility Mix - Léonie Watson
> __Léonie Watson__ |
 [Twitter](https://twitter.com/LeonieWatson) |
 [GitHub](https://github.com/LJWatson) |
 [Website](http://tink.uk/) |

> _With a little help from Daft Punk, Léonie will explain accessibility mechanics in the browser, why CSS isn't just about looking good, and what tools you can use to get ahead of the game._

> _When you use HTML the browser handles a lot of things for you. It exposes semantic information to accessibility APIs on the platform, and provides focus and interaction. But what do you do when using proper HTML isn't possible?_

> _Once upon a time CSS let us separate design and structure, but in recent years the streams have started to cross again. CSS can change the way content is exposed by the browser, often with unexpected consequences. But does this matter in the real world?_

> _When you're sprinting for a deadline, rapidly iterating code and using frameworks and build tools to make it happen, accessibility can feel like one thing too many. So how the hell do you keep your code accessible as you go?_

...

**Slides: 	[ljwatson.github.io](http://ljwatson.github.io/decks/2016/fronteers/index.html)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194964027)**

============================================================
<a name="07-1650"></a>
## Joining Up the Dots - Heydon Pickering
> __Heydon Pickering__ |
 [Twitter](https://twitter.com/heydonworks) |
 [GitHub](https://github.com/Heydon) |
 [Website](http://www.heydonworks.com/) |

> _Brain function, language and the World Wide Web are all systems constituted by dots - notions, signifiers, locations - joined up with lines - synapses, relationships, links. In fact, the expression "connecting up the dots" is synonymous with making and completing something meaningful._

> _This talk explores the Web as the ultimate outcome of our impulse to make systems of shared meaning, and addresses threats to the Web's public and interconnected nature from within and without its technical development. Deforestation, Hegelian dialectics, sharks, Waldorf salads, positivism and Kanye West are all part of the talk's precarious, though still ultimately interconnected, content._

...

**Slides: 	[slides.com/heydon](http://slides.com/heydon/joining-up-the-dots#/)**
**Video: 	[vimeo.com/fronteers/videos](https://vimeo.com/194964404)**

============================================================
### More info/ other notes from attendees:
* [Nienke Dekker](https://github.com/nienkedekker/fronteers-2016)
* [Pim Derks - day one](https://gist.github.com/PimDerks/d2b339d567ab0759fc2e648dcd3c4c19)
* [Pim Derks - day two](https://gist.github.com/PimDerks/fc2b3c30e8b7a985a496512eda705079)
* [Ruben Janssen - day one](https://github.com/RubenJnl/Fronteers/blob/master/Fronteers16/%23Fronteers16%20day%20one.md)
* [Ruben Janssen - day two](https://github.com/RubenJnl/Fronteers/blob/master/Fronteers16/%23Fronteers16%20day%20two.md)
