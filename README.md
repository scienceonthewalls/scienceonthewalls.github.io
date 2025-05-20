# Science on the Walls website

This repository contains the Science on the Walls webpage, which is hosted on GitHub.

Science on the Walls is a science outreach initiative that empowers children in underserved communities to explore scientific concepts through artistic and creative practices.

## Documentation and how to contribute

### Layout

`_config.yml`: the configuration file - this contains essential information about science on the walls (e.g. social media handles) which will be used for the side banner, headers and footers of the default webpages.

---

`_data/navigation.yml`: header outline file - Outlines the visible webpage links.

This requires a "title" for the header button and an "url" path. By default this starts in the `_pages/` directory.

> *Example:* We want to include the webpage `_pages/vision.md` and the button to this page is called "Our Vision".
```markdown
main:
    - title: "Our Vision"
      url: /vision/
```

These pages can be `.md` or `.html` files but the preample at the top of the page should have a `permalink` matching the url path. Such as:

```markdown
---
permalink: /vision/
title: "Our Vision"
author_profile: true
redirect_from: 
  - "/our_vision/"
  - "/vision.html"
---
```

---

`_pages/`: Where the main webpages are stored

`about.md`: Homepage - About us, who we are, who supports us already, advertising to join us. Images in this page are stored in `images/homepage/` and videos in `videos/`. 

> Note: the permalink for the homepage is `permalink: /`

`vision.md`: Our goals - highlighting our manifesto

`achievements.md`: Our Achievements - highlighting statistics of our impact with our past events.
<!-- (TODO: add feedback forms scientific impact) -->

`team.md`: Our team - illustrate core members of the initiative. To add a new member. Ensure their photo is of square format and saved in `/images/team/v2/MEMBER_NAME.png`. 

This page is formatted by a 2x5 table. Where the first row is the thumbnail of the person and the second is their name. Details to add a team member can be found [here](#updating-our-team)

`timeline.html`: Our history - outlining in brief different events hosted by science on the walls since the start.


`year-archive.html`: Our blog - Have individual markdown pages describing an event or news about SOTW. These posts are stored in `_posts/` directory and the file will be labelled with the date e.g. `_posts/[yyyy]-[mm]-[dd]-name-of-activity.md`.

> NOTE: You don't need to edit anything in the `year-archive.html`, this will automatically look into the `_posts/` directory and pull out all the blogs. See [Adding a blog post](#adding-a-blog-post) for details on how to make a post.

`images/`

---

### Updating home page

Everything in the homepage is self contained in the `about.md`. If you want to insert pictures. Make sure to save them in the `images/homepage/` directory, and you are pointing to them correctly e.g. `/images/homepage/cdm.jpeg`.

To add text you can follow Markdown syntax [here](https://www.markdownguide.org/cheat-sheet/), or html syntax for specific style (might be easier for images).

### Adding a blog post

The make a blog post here are some simple instruction

1. Create a markdown file in `_posts/` names as `[yyyy]-[mm]-[dd]-name-of-activity.md`
2. At the top of the file fill in the preamble, like the exmaple below:
```markdown
---
title: 'Summer Camp 2024'
date: 2024-08-29
permalink: /posts/2024/08/summer-camp/
excerpt: "Short description of portfolio item number <br/><img src='/images/blog_posts/2024_summer_camp_ceramics.jpeg' style='width: 50%;'>"
tags:
  - Summer Camp
  - Street art
  - Cova da Moura
---
```
3. Below the preamble, write a few sentences detailing the post. Feel free to add images, but the images should be save with their date prefixed and stored in the `/images/blog_posts/` directory.

#### General comments:

* tags - can be used to help the reader navigate and find other similar posts
* excerpt - doesn't have to contain an image (as in the example above) but it provides a summary that the user will see on the main blog page before clicking on a specific post.
* permalink - make sure the post follows the structure e.g. `post/yyyy/mm/name-of-event/`

### Updating Our Team

To make a new row of members copy the code from:

```markdown
<table style="border-collapse: collapse; width: 100%; text-align: center; border: none;">
    ...
</table>
```

`events.md`: Our events - outlining the various events organised. The layout of this is a table, to add more, add another row to the table. Essentially, duplicate all code from:
```markdown
<tr>
    ...
</tr>
```
And, ensure it's inside the 
```markdown
<table style="border-collapse: separate; border-spacing: 10px; width: 100%; border: none;">
    ...
</table>
```

### Adding events on the Our History timeline page

The section `<header>` describes different objects we can use for the html file. We don't need to change any of this.

The only area you need to add is within the code that starts `<body>`.

To ***add an event on the left***, you need to copy, inside the indentation of code that says `<div class="timeline">`, this:
```html
<!-- -->
        <div class="event left">
            <img src="/images/timeline/202409_Summer_camp.png" alt="Summer camp">
            <div class="event-text">
                <h3>September 2024</h3>
                <p>Summer camp</p>
                <p><i>Cova da Moura</i></p>
            </div>
        </div>
```
Then you replace `September 2024`, `Summar camp`, `Cova da Moura` with the relevant date, event and location. Also, replace the image source that say `/images/timeline/202409_Summer_camp.png` to the relevant `.png` file you want to share.

***To add an event on the right***, is the exact same, but replace `<div class="event left">` with `<div class="event right">`

***To add a new year***, make sure to be ourside of the class `"timeline"` and on a new line write `<h2>2022</h2>`.

Now to write events in new section you have to make a new timeline, e.g.

```html
    <h2>2025</h2>
    <div class="timeline">
        <!-- -->
        <div class="event left">
            <img src="/images/timeline/202503_name.png" alt="Easter camp">
            <div class="event-text">
                <h3>March 2025</h3>
                <p>Easter Sustatinability camp</p>
                <p><i>Cova da Moura</i></p>
            </div>
        </div>
        <!-- -->
        <div class="event right">
            ...
        </div>
        <!-- -->
        ....
    </div>
    <!-- 2025 events up hereee -->
```