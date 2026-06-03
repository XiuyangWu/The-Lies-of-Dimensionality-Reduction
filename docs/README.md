# The Lies of Dimensionality Reduction

An interactive diagnosis of distortion in high-dimensional data visualization.
Fashion-MNIST (784-D) flattened to 2-D by six projection methods (PCA, MDS,
Isomap, t-SNE, UMAP, PaCMAP), then audited for where each map lies.

**Live demo:** open `index.html` (the 4-tab explorer) or `story.html` (a scrollable narrative).

## What's inside

| File | What it is |
|------|------------|
| `index.html` | Main entry: 4 tabs (hero shot, linked explorer, six-way overview, perplexity animation) |
| `story.html` | Scrollable narrative walking through the whole argument |
| `dashboard_linked.html` | Six linked maps: click a point to see true (blue) vs false (red) neighbors; lasso to brush all six |
| `fig1_overview.html` | Six projections of the same 784-D data, hover for class and distortion counts |
| `anim_perplexity.html` | t-SNE perplexity sweep 5 to 100: the shape mutates while the score stays ~0.98 |
| `hero_galaxy_*.png`, `fig*_pub.png`, `fig6_frontier.png` | Static figures used by the pages |

## Key findings

- A bag's 11 nearest map-neighbors are all sneakers (the map invents neighbors).
- t-SNE pairwise-distance fidelity is rho = 0.72, lower than plain PCA at 0.87.
- Local and global honesty are anti-correlated across the six methods, r = -0.89.

## Notes

- The interactive pages load Plotly from `cdn.plot.ly` at runtime, so an internet
  connection is needed. On GitHub Pages this works out of the box.
- The `.nojekyll` file tells GitHub Pages to serve files as-is.

## Data

Fashion-MNIST (Zalando), 3000 images, 300 per class, raw 784-D pixels. Public dataset only.
