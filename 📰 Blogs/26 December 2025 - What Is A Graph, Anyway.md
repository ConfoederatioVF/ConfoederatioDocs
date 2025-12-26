```diff
+ And other assorted dev progress.
  
Vis Tacitus
- 26 December 2025
```

#blogs #confoederatio #Y2025

![[vercengen_datavis_suite_prototype.png]]
<div align = "center">ve.DatavisSuite as it currently stands.</div>

**Merry Christmas!** As a software/tooling provider, it is naturally our humble duty to present new components and applets on this joyous occasion. Much progress has been made towards a **1.0** of [[Vercengen]] by introducing new ve.DatavisSuite, ve.Graph, and ve.ObjectInspector components, whose ergonomics, UI and polish are still a work in progress (WIP) but fully functional nonetheless.

I had been busy reading Leland Wilkinson's *The Grammar of Graphics*, and I must say that its grammar is so terribly complicated that our favourite feline programmer (who may or may not be named Aust) had to lay down with a whiff of catnip. Upon awakening from their nap, they told me of fluffy yarnballs and a different approach:

> *'Variables, Algebra, Scales, Statistics, Geometry, Coordinates, Aesthetics, Renderer! It's so complicated.*
> 
> *Any good graph is an image. Aren't graphs just data transformed into lines projected in different ways? Then each line simply has a symbol that determines its look with the given renderer'.*

And thus [[Vercengen DatavisSuite|ve.DatavisSuite]] was born.
## Lines Projected In Different Ways

But what does this actually look like, apart from the image seen above? Simply put, selections in a 2D dataframe are grouped into 'series', and if multiple data columns are selected, the lines are grouped together (for line graphs this means stacking, for bar charts this means grouping, etc).

Each series then has a symbol that styles it. What is its colour? What is its fill? How should it be projected onto the graph? Finally, graphs themselves are made of multiple charts that can be repositioned and freely overlaid one atop the other. Because graphs are fundamentally images, this sort of schema covers everything.

*'But what about scatterplots?'* I hear you ask. Points are simply a degenerate sort of line which has only one vertex, or multiple vertices in which the line segments in between have a transparent stroke. On the other hand, polygons are demarcated by a line to begin with, making the symbol applicable in the first place.

For instance, choropleths are also patterned lines like everything else - it is only that the fill colour represents the value of the data instead of being symbolic instead.

## Delivering the Vision

![[vercengen_ObjectInspector.png|600]]
<div align = "center">The new ObjectInspector. It's like Chrome DevTools, but in your DOM!</div>

Most of the legwork in getting a functional version of ve.DatavisSuite has already been added, and the only thing that remains is some backend refactoring, polish, and adding additional content. We had projected that the actual legwork would take about a week in total, but it has only been two days, and already it is largely done.

Of course, a 1.0 without polish would be very rough indeed (and we are not game developers, you know), and so we have been busy flagging ergonomic issues with different components and attempting to fix them before release. These are not fundamentally breaking, but lead to an overall sense of jank and UX inconsistency which we would like to address.

Finally, Telestyle theming needs more work since there are no global stroke variables applied to Features (yet!), which is a problem if you want a light theme but have a website with a white background. Currently, you simply have to apply the `.style` option for strokes to every single feature individually.

If we can get a good ve.DatavisSuite component in before 31 January 2026 (which is our New Year's commitment and deadline), we will be able to work on sorting jank out and much more with the remaining days. The majority of what we intend to polish is documented in [[Vercengen Polish 1]].