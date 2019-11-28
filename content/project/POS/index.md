+++
# Date this page was created.
date = "2016-04-27"

# Project title.
title = "The minority language typing experience"

# Project summary to display on homepage.
summary = "How much work is it to type languages with tonal markers in their orthographies?"

# Optional external URL for project (replaces project detail page).
external_link = ""

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["maps", "pos"]


# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = ""
  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Center"
  
  # Show image only in page previews?
  preview_only = true



# Does the project detail page use math formatting?
math = false

# Optional featured image (relative to `static/img/` folder).
#[header]
#image = "headers/bubbles-wide.jpg"
#caption = "My caption :smile:"

+++
**Previous work**:

This project follows and builds upon the project where [keyboard layouts for Meꞌphaa and Sochiapam Chinantec](/project/2012-mexico-keyboards/) were produced. This project uses data from Meꞌphaa and Sochiapam Chinantec but purposely extends the scope of the analysis to include Latin and Cyrillic script languages, particularly focusing on those with diacritics which express tone.

**Goals**:

The goal of this project is to bring 'natural', intuitive, and easy to use typing experiences in the form of keyboard layout designs to minority language users. These language users often do not type in their own languages, but rather experience technology through languages other than their first language. This is in part because of the perception that their language is complex or not easy to type, which is often not an invalid observation. However, with these languages which have different and sometimes more characters than English, what does a good layout look like?
The objectives of this project are threefold:

1. To establish a consistent method to evaluate the appropriateness of a keyboard layout for a specific language situation given a specific text sample. This needs to include `deadkeys` and `alt` states.
 * This needs to account for monolingual situations
 * This needs to account for multi-lingual situations where each language has its own keyboard
 * This needs to account for multi-lingual situations where only a single keyboard is used
2. Provide a best fit solution recommendation when provided the following:
 * A corpus of text encoded in UTF-16 or UTF-8 in any language
 * A user selected choice between a physical keyboard layout of ANSI, ISO, or JIS
The application providing the best fit solution needs to be able to suggest a better layout, inclusive of `alt` states and `deadkey` options.
3. Assess and analyze real user feedback. That is, measure the impacts of keyboards on users. Speed of typing, speed of keyboard acquisition, error rate, and results such as language choice when typing.

<span class="fa fa-github fa-2x"></span> Project resources are split into three repos: [MLKA](https://github.com/HughP/MLKA), [MLKA-Bash-data](https://github.com/HughP/MLKA-Bash-data), and [MLKA-Test-Data](https://github.com/HughP/MLKA-Test-Data).
