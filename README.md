# Global Rail Transit: Infrastructure, Progression & Geographic Reach

**INFSCI 1520 — Information Visualization — Final Project**

## Overview
Four-figure visualization of global rail infrastructure using World Bank time-series data and Natural Earth geometry. Covers rail density, network growth/decline, regional clustering, and high-speed rail connectivity gaps.

## Data Sources
| Source | What | Access |
|--------|------|--------|
| World Bank Open Data | Rail km, population, area, urban % — 180+ countries, 1990–2022 | `wbgapi` Python package |
| Natural Earth 10m | Railroad line geometry, country polygons | Built into `cartopy` |
| UIC 2023 Yearbook | High-speed rail km by country | Hardcoded from Wikipedia/UIC |

## Figures
| File | Description |
|------|-------------|
| `main_figure.png` | World choropleth + NE rail lines · Bubble: density vs urbanization · Bars: growth/decline |
| `network_figure.png` | Country clusters by region, node size = √(rail km), color = growth trend |
| `pca_figure.png` | Parallel coordinates (top 30 countries) + diverging bar (growers vs decliners) |
| `hsr_figure.png` | Global HSR map with Europe/East Asia/USA insets, hub cities, gap zones |

## Course Module Coverage
| Week | Topic | Implementation |
|------|-------|----------------|
| 3 | Streaming / one-pass | World Bank indicator loop with progress counter |
| 4 | Scatter | Bubble chart: rail density vs urban % |
| 7–8 | Network | Country clusters, 2-nearest-neighbor edges |
| 10 | Time series | Growth/decline diverging bar chart |
| 11 | Maps | Cartopy Robinson projection, choropleth + line overlay |
| 12 | PCA | Parallel coordinates (normalized 5-variable profiles) |

## Setup
```bash
pip install wbgapi cartopy geopandas scipy scikit-learn networkx matplotlib
```

Run all cells top-to-bottom in Google Colab or Jupyter. Each cell is self-contained and prints progress.

## Output
Cell 8 downloads all four figures. Total runtime ~5 minutes (World Bank fetch is the slowest step).
