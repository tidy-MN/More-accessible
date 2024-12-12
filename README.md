# More accessible ✨

Resources to improve accessibility

**Contents**

- [Alt text](https://github.com/tidy-MN/More-accessible/blob/main/README.md#alt-text-for-visuals-images-charts-figures)
    - [For images](https://github.com/tidy-MN/More-accessible/blob/main/README.md#images)
    - [For charts](https://github.com/tidy-MN/More-accessible/blob/main/README.md#charts)

## Alt text for visuals: images, charts, figures

Alt text (alternative text) are short descriptions added to images to describe the meaning of the visual. Assistive technology like screen readers can read the alt text out loud so users can hear a description of the visual content.

- **Template for Alt text** - https://nightingaledvs.com/writing-alt-text-for-data-visualization/
- **Quarto how-to**
    - Images: https://quarto.org/docs/authoring/figures.html#alt-text
    - Charts and tables: https://mine-cetinkaya-rundel.github.io/quarto-tip-a-day/posts/28-fig-alt/
- **Markdown how-to** - https://posit.co/blog/knitr-fig-alt/

<br>

## Examples

### Images

Both of the options below will create HTML that includes alternative (alt) text accessible to screen readers.

```html
<img src="https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg" alt="Logo for the State of Minnesota.">
```

#### Two options

##### Option 1

Add a `\` at the end of the markdown line to use the caption text inside the `[ ]` as the alt text.

```markdown
![Option 1 - Logo for the State of Minnesota. ](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg)\`
```

##### Option 2

Add `{fig-alt="Your alt text here"}` at the end of the markdown line to add unique alt text.

```markdown
![](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg){fig-alt="Option 2 - Logo for the State of Minnesota."}
```

### Caption & Alt text

Captions should generally be different than the alt text or screen reader users will hear the same text repeated twice.

This markdown will include the image with a caption and alt text in the HTML.

```markdown
![I work here!](https://mn.gov/portal/assets/primary-reversed-logo_tcm1077-265309.jpg){fig-alt="Logo for the State of Minnesota."}`
```

---  

## Charts

You can add alt text to a chart or another visual produced by a code chunk by adding  `fig-alt:` to the options for that code chunk.

```` markdown
```{r}
#| fig-alt: Scatterplot alt text...

```
````

```` markdown
```{r}
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
````

<br>

The resulting HTML is shown below and includes alternative (alt) text accessible to screen readers.


```html
<img src="alt-text_files/figure-html/penguins-plot-1.png" alt="Scatterplot of bill depth vs. bill length for individual penguins, colored by species. The relationship is positive for each of the three species: Adelie, Chinstrap, and Gentoo.">
```


