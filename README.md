# Prototype @ NPR
Using my prototyping framework, [Jekyons](http://tinychime.github.io/jekyons), my goal is to create a prototyping kit & component library for NPR.org. This is an NPR [Serendipity Days](http://www.npr.org/sections/inside/2011/10/14/141312774/happy-accidents-the-joy-of-serendipity-days) project.

## Setup
```
git clone https://github.com/joshosbrn/prototype-npr.git your-project
cd your-project
rm -rf .git
npm install
bundle install
jekyll build
gulp
```

## Challenges
### Folder Structure for Includes
The first snag I hit was in the folder structure of the ```_includes``` directory. Usually includes in a Jekyll project (at least times I've used them) contain larger chunks of code, like headers & footers. I wanted to break up the ```_includes``` directory to map back to the [inventory document](https://docs.google.com/spreadsheets/d/1fqBpl9GF1trXtA7bKYkqaWf69FIBJuGX7Bsq-1BqVaU/edit?usp=sharing) I created on Wednesday morning.

This ended up being a pretty easy fix. Including markup by doing something like ``` {% include directory/module.html %} ``` works perfectly. Thanks, Jekyll.

The other tough thing here was figuring out a good way to render a full list of components. I'm pretty happy with the solution in index.html but I'm sure there's a much better way to do this.

### Maintainable Style Overrides
One of the biggest blockers for this idea in the past has been the idea of maintaining the list of NPR.org SASS variables in a smart way. Since Todd's accesiblity-focused refactor of the colors a few months ago, I don't think they'll be changing any time soon so I'm officially removing this as a blocker. I may come back during housekeeping or a future Serendipity to make updates if necessary.

### Prototyping With Data
My idea here was to create a .yml file with ~10 stories worth of metadata to pull into the different components. Using for loops & limits, I can power all of them using the same data source: ```_data/stories.yml```

## Helpful Links
[Jekyll & Liquid Cheatsheet](https://gist.github.com/smutnyleszek/9803727) — Quick guide to the Liquid syntax. Helpful in the context of this project for reminders about for-loops and filters.

[Jon Gold on functional CSS](http://www.jon.gold/2015/07/functional-css/) — a good in-defense-of blog post on functional CSS.

[Functional CSS Pros/Cons](https://github.com/chibicode/react-functional-css-protips) — a guide from Chibicode that focuses on the ups and downs of Functional CSS with a focus on React. Not incredibly relevant to this project, but it showed me the merits of OOCSS.
