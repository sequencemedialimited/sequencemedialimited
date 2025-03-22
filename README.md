# Jonathan Perry

## Senior/Lead Full-Stack Developer

I have thirty years experience building websites and have been creating **JavaScript** applications since 1998.

I use **EcmaScript** and **TypeScript** with **React** and **Node**.

I'm an accessibility advocate and recommend static **HTML** where it's all that's needed.

You can [email me directly](mailto:jonathanperry@jonathanperry.com) or [message me on LinkedIn](https://linkedin.com/pub/jonathan-perry/0/327/822).

My [CV is available on Dropbox](https://www.dropbox.com/scl/fi/p7xxztow6wmkrvjlhtxn4/Jonathan-Perry.docx?rlkey=9f2chcljox2o7wa2wwhecvwbr&st=1vpamj2h&dl=0).

## Sequence Media Limited

The [Sequence Media](https://github.com/sequencemedia) organisation has the majority of my public projects.

The [Modern Poacher](https://github.com/sequencemedia) organisation has some more, which are related to or derived from the **Zashiki Karakuri** platform.

The projects for **Sequence Media** are a sample of both my professional and personal work.

### React

Many of my **React** projects were begun before other, better implementations were available. I continue to maintain them because they have proven their value for edge-cases and emergencies! Some are _class_ components and some use _hooks_ because I have been writing **React** since 2013 and class components still make sense for those projects. (Day-to-day I prefer _function_ components and _hooks_.)

#### Isomorphism

Since **React** can be executed at the server I have always preferred to implement it for both client- and server-side rendering, which led me to create these projects which do nothing more than expose existing features of **React** in an ever-so-slightly more simple way.

These projects have been used in both [Express](https://expressjs.com/) and [Hapi](https://hapi.dev/).

- [`react-render`](https://github.com/sequencemedia/react-render)
- [`react-router-render`](https://github.com/sequencemedia/react-router-render)
- [`react-redux-render`](https://github.com/sequencemedia/react-redux-render)
- [`react-router-redux-render`](https://github.com/sequencemedia/react-router-redux-render)

#### `react-select-element`

At Deutsche Bank during the period between 2001 and 2004 I wrote a **DHTML** `<select />` element. It was hard and it took a long time.

More than ten years later I decided to recreate it in **React**. It was easy and took very little time at all.

I had grown as a developer in that intervening decade or so, and the available tools were _much more_ sophisticated. I also had that prior experience to guide me. At Deutsche Bank the process had been one of discovery _as well as_ implementation: what features does a native `<select />` have, actually? What does our application need? How do I recreate those features for both IE and Netscape?

With **React** I was able to go from nothing to something in an afternoon.

I most recently used [`react-select-element`](https://github.com/sequencemedia/react-select-element) for production in 2023.

#### `react-router-pagination`

An [_example implementation_](https://github.com/sequencemedia/react-router-pagination-io) of the component (using a **Hapi** server) has never been starred but has been forked three times more often than [the component itself](https://github.com/sequencemedia/react-router-pagination). 🤷‍♂️

### Node

#### `music-library` and `music-library-parser`

A favourite project is [Music Library](https://github.com/sequencemedia/music-library) and its dependency [Music Library Parser](https://github.com/sequencemedia/music-library-parser).

These were created for [iTunes](https://en.wikipedia.org/wiki/iTunes) but are now used for [Music](https://en.wikipedia.org/wiki/Apple_Music).

I maintain lots of playlists which are described in `Library.xml`. 

Generating `Library.xml` used to be a setting in **iTunes** but for **Music** I use a standalone tool on a schedule.

My projects transform `Library.xml` into `m3u` format files for consumption by other devices.

- **Music Library** is a command line app in Node to watch for changes in `Library.xml` and initiate its transformation.
- **Music Library Parser** transforms `Library.xml` then writes `m3u` format files to disk. (The transformation uses **Java** and **XSLT**, and can also produce `JSON` files or expose the data to **JavaScript** as other structures.)

These projects have been used with both [Plex](https://www.plex.tv/) and [MinimServer](https://minimserver.com/). **MinimServer** is a gem.

#### `crypto`

I love combining **Node** and **Bash**.

Versions of these **JavaScript** functions were used in a production app. I used **Bash** in development to validate the **JS** and then made it a utility in case of failure. (The likely cause of any failure would be elsewhere, but at the very least it's useful to confirm that _given the correct settings the **JS** will encrypt and decrypt successfully_).

### Modules

#### `center-center`

The description and demonstrations for the [Center Center](https://github.com/sequencemedia/center-center) project offer a different use-case to production.

Here, a target element responds to scroll events to keep itself centred in a container while the container moves.

In production, a target `SVG` child node was identified _by its text content_ from a list, and then it was animated into position so that the child node was centred in the `SVG`, which depended on the viewbox of the `SVG` and its zoom scale and _the position of the container of the `SVG` in the viewport of the page_.

It's very hard to describe and working out the maths for the co-ordinates was harder, but very simple once you know how.

I have **D3** to thank for a crowd-pleasing swoosh once I had those co-ordinates.

### Performance

A lot of my work from before 2012 was preoccupied with performance. You can see the remnants of that in the projects initiated before then (which may have found their way into GitHub only more recently as _curiosities_).

While it's no longer a preoccupation, I find it useful to remain mindful of how the machine works.

For instance, here are two reducer functions which produce an identical result.

#### a)

```javascript
const a = [] // An array of items

const b = a.reduce((accumulator, v) => {
    if (v) accumulator.push(v)
    return accumulator
}, [])
```

#### b)

```javascript
const a = [] // An array of items

const b = a.reduce((accumulator, v) => (v) ? accumulator.concat(v) : accumulator, [])
```

For dozens or hundred of items, both are fine. For many thousands of items, one will be faster than the other, and the slower will become even slower as the array becomes larger.

It may be obvious to you which is which. I prefer one because it looks nicer! But _generally_ I implement the other, unless I am certain that the array is small and no-one is watching.

### Curiosities

From 1999 until around 2007 I maintained a collection of scripts I would hesitate to call a _library_ but which were, in fact, exactly that. Web browsers of the period were glittering examples of human innovation, and also riddled with terrible bugs. That collection of scripts had solutions for many commonly encountered problems or, at least, were an _aide memoire_ to a solution I had previously made.

I'm sure I must have taken those scripts with me on a floppy disk into all sorts of environments without care or thought for security or hygiene.

[Difference Engine](https://github.com/sequencemedia/difference-engine) and [Rasher](https://github.com/sequencemedia/rasher) memorialise some of that code. (**Difference Engine** has code that was developed before 2005 as well as for projects between 2008 and 2012. **Rasher** implements a solution for one issue that I believe was from as early as IE 4, or as late as IE 6. It also has a solution for a production problem encountered in another library from as recently as 2014.)

I continue to manage these projects as _curiosities_.

<hr/>

- [Email me directly](mailto:jonathanperry@jonathanperry.com)
- [Message me on LinkedIn](https://linkedin.com/pub/jonathan-perry/0/327/822)
- My [CV is available on Dropbox](https://www.dropbox.com/scl/fi/p7xxztow6wmkrvjlhtxn4/Jonathan-Perry.docx?rlkey=9f2chcljox2o7wa2wwhecvwbr&st=1vpamj2h&dl=0)
