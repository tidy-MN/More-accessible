# More accessible

Resources to improve accessibility

## Image alt text

Alt text (alternative text) are short descriptions added to images to describe the meaning of the visual. Assistive technology like screen readers can read the alt text out loud so users can hear a description of the visual content.

- **Chart template** - https://nightingaledvs.com/writing-alt-text-for-data-visualization/
- **Quarto how-to**
    - Images: https://quarto.org/docs/authoring/figures.html#alt-text
    - Charts and tables: https://mine-cetinkaya-rundel.github.io/quarto-tip-a-day/posts/28-fig-alt/
- **Markdown how-to** - https://posit.co/blog/knitr-fig-alt/

<br>

## Examples

### Images

Both of the options below create the following HTML that includes the image with alternative (alt) text accessible to screen readers.

```html
<img src="https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg" alt="Logo for the State of Minnesota.">
```

#### Two options

**Option 1**
`![Option 1 - Logo for the State of Minnesota. ](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg)\`

### Option 2
`![](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg){fig-alt="Option 2 - Logo for the State of Minnesota."}`

### Caption & Alt text

Captions should generally be different than the alt text or screen reader users will hear the same text repeated twice.

This markdown will include the image with a caption below and alt text in the HTML.

`![I work here!](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg){fig-alt="Logo for the State of Minnesota."}`

---  

## Charts and tables

Add `fig-alt` as a code chunk option like below:

```r
#| fig-alt: Scatterplot alt text...
```

```r
#| label: penguins-plot
#| warning: false
#| fig-alt: |
#|   Scatterplot of bill depth vs. bill length for individual penguins, colored by species.
#|   The relationship is positive for each of the three species: Adelie, Chinstrap, and Gentoo.  

library(tidyverse)
library(palmerpenguins)

ggplot(penguins, 
       aes(x = bill_length_mm, y = bill_depth_mm, color = species)) +
  geom_point() +
  scale_color_viridis_d()
```

<br>

The resulting HTML is shown below and includes alternative (alt) text accessible to screen readers.

```html
<img src="alt-text_files/figure-html/penguins-plot-1.png" alt="Scatterplot of bill depth vs. bill length for individual penguins, colored by species. The relationship is positive for each of the three species: Adelie, Chinstrap, and Gentoo.">
```


