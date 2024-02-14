http://dynalon.github.io/mdwiki/#!download.md

## Adding a navigation

Create a `navigation.md` file in the same directory as the `mdwiki.html` and put in the links that make up your menu:

```
# Your wiki name

[Home](home.md)
[About](about.md)
[Download](download.md)
```

The first line is a Markdown heading, which will be used as the website brand in the navbar. Standard Markdown links are to be used for the navbar entries.

For more complex menus, nesting submenu items as a list and using horizontal lines that will be rendered as dividers is also possible:

```
# Brand name

[Menu Item 1]()

  * # SubMenu Heading 1
  * [SubMenu Item 1](subitem1.md)
  * [SubMenu Item 2](subitem2.md)
  - - - -
  * # SubMenu Heading 2
  * [SubMenu Item 3](subitem3.md)
  - - - -
  * # SubMenu Heading 3
  * [SubMenu Item 3](subitem3.md)

[Menu Item 2](item2.md)
- - - -
[Menu Item 3](item3.md)
```

If a bulleted list of links is supplied as in the above example, the list will become a dropdown in the navigation bar displaying a submenu. In order for this to work, the toplevel link has to have an empty target (see Menu Item 1 in the above example). Dropdown headings are also possible by prepending a single `#` in front.

## Creating links

Links to anywhere in the web are done via regular Markdown links:

```
[Google](http://www.google.com)
```

Links within the wiki are just plain relative links:

```
[Go to download](download.md)
```

Internal links will be prefix automatically with the `#!` hashbang:

## Images

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

Images are regularly placed as in standard markdown using the `![alt](href "title")` notation. MDwiki will create a nice highlight-like popup if you click an image. You can group images together by **not** putting an empty line in between them.

Example:

```
![](http://placekitten.com/g/1200/300 "A kitten")

![](http://placekitten.com/g/550/450 "First of two kittens")
![](http://placekitten.com/g/550/450 "Second of two kittens")

![](http://placekitten.com/g/400/350)
![](http://placekitten.com/g/400/350)
![](http://placekitten.com/g/400/350)
```

### Images as Links

To use an image as a link, use the following syntax:

```
[![ImageCaption](path/to/image.png)](http://www.linktarget.com)

Example:
[![A kitten](http://placekitten.com/g/400/400)](http://www.placekitten.com)
```

# Gimmicks

To use Gimmicks, all you have to do is include some specially crafted link into your markdown file. For example, if you want to embed a Youtube video (instead of linking to it), you just have to insert a link to the video:

```
[](http://www.youtube.com/watch?v=RMINSD7MmT4)
```

Gimmicks are realized via Javascript and work out of the box.

Gimmicks are designed to always chose sane default values when no parameters are given, therefore *most* gimmicks do not require any parameters to work.

Note: Gimmicks will usually load code or stylesheets from the internet, therefore they won't work in offline mode

## Google Maps

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

Allows to embed a basic map from [Google Maps](http://maps.google.com/), centering at any given address specified via the link target.

Example Code:

```
[gimmick:googlemaps](Madison Square Garden, NY)

[gimmick:googlemaps(maptype: 'terrain', zoom: 9, marker: 'false')](Eiffel Tower, Paris)

[gimmick:googlemaps(maptype: 'satellite', zoom: 17)](Colloseum, Rome, Italy)
```

Arguments:

- **maptype**
  - is one of [ 'terrain', 'roadmap', 'satellite', 'hybrid' ]
  - defined the type of the map
- **zoom**
  - Defines the zoom level of the map (default: 11)
  - The minimum/maximum zoomlevel depends heavily on the **maptype**. Best way to find a fitting value is just try'n'error.

## UML Diagrams via yUML.me

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

Embeds diagrams from the excellent [yUML.me](http://yuml.me/) service (see their website for documentation).

Embeds diagrams from the excellent [yUML.me](http://yuml.me/) service (see their website for documentation).

Examples:

![](http://yuml.me/diagram/plain;dir:LR;scale:100/class/[HttpContext]uses%20-.-%3E[Response])

```
[gimmick:yuml]( [HttpContext]uses -.->[Response] )
```

## Youtube

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

Whenever you insert a regular link with an empty caption that points to a video on `youtube.com` or `youtu.be`, the link is automatically turned into an embedded iframe, which will display a preview thumbnail of the video on your website.

Example:

```
This will show the video preview on your website:
[](http://www.youtube.com/watch?v=RMINSD7MmT4)
```

To omit the preview and just get a regular link, add a caption:

```
[Click to see an awesome video](http://www.youtube.com/watch?v=RMINSD7MmT4)
```

[Click to see an awesome video](http://www.youtube.com/watch?v=RMINSD7MmT4)

- [Page layout](http://dynalon.github.io/mdwiki/#!layout.md#Page_layout)
- [Image floating](http://dynalon.github.io/mdwiki/#!layout.md#Image_floating)

## Page layout

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

All pages should start with a 1st heading, which is turned into the page title. To devide the page into sections, use 2nd degree headings. All 2nd degree headings will end up in the side menu for in-page navigation:

```
Heading=======

Section 1---------

[...]

Section 2---------

[...]
```

---

## Image floating

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

Standard Markdown provides no way to influence the layout of your resulting website, like floating of images. To enable you to do so anyway, MDwiki interprets the presence (or absence) of blank lines between images and paragraphs in a special way that allows text flows like in newspapers.

### Floating to the left

If the image(s) are placed at the top of the paragraph, *without* any blank line between the image(s) and the paragraph, the image(s) will float left.

```
![](http://placekitten.com/g/800/800)
The above image floats left to this text.
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
```

### Floating to the right

If the image(s) are placed at the bottom of the paragraph, *without* any blank line between the image(s) and the paragraph, the image(s) will float right.

```
The images below float right to this text.
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
![](http://placekitten.com/g/600/600)
![](http://placekitten.com/g/600/600)
```

### No floating

A blank line before or after the image(s) disables any floating.

Source:

```
![](http://placekitten.com/g/600/350)
![](http://placekitten.com/g/600/350)

This text is preceded by two images, that span across the whole Page width.
```

### Mixing floats it all together

## Theme chooser

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

There is a special gimmick `ThemeChooser` that will add a submenu entry to the navigation bar with all available themes. Enable it by adding

```
[gimmick:themechooser](Choose theme)
```

to the `navigation.md` (or into each page individually).

### Selecting a theme

You can manually set a specific theme that will be used if the ThemeChooser gimmick is not used or set to the default theme:

```
[gimmick:theme](flatly)
```

This will set the default theme to `flatly`. You can see a list of the theme names in the `ThemeChooser` gimmick or on this page (select `Change theme` in the navbar).

To apply the theme globally for all files, put the entry into `navigation.md`. You can also switch the "inverse" mode, which will change colors for some themes (see [http://www.bootswatch.com/](http://www.bootswatch.com/) for details)

```
[gimmick:theme (inverse: true)](flatly)
```

Note: Only the default `bootstrap` theme is bundled with MDwiki and available offline. All other themes require internet connection, as the styles are dynamically loaded on demand.

## Configuration

[[ ↑ ]](http://dynalon.github.io/mdwiki/#md-page-menu)

You can create a `config.json` file in the same folder as the `mdwiki.html` file which is then used for configuration. The file has to be valid JSON. Currently these options are available:

- `"useSideMenu": false` - disable the side navigation
- `"lineBreaks": "original"` - Instead of using the [GFM](https://help.github.com/articles/github-flavored-markdown) line breaks, use the original line breaking as [introduced by John Gruber](http://daringfireball.net/projects/markdown/):
  - line breaks in the markdown files are ignored, except if a line ends with two spaces
  - Default is `lineBreaks: "gfm"` (line breaks in markdown will create a new paragraph)
- `"additionalFooterText": ""`
  - Can be used to add text to the copyright footer at the bottom, like custom copyright notices.
  - Example: `additionalFooterText: "All content and images &copy; by John Doe"`
  - Default: `""` (empty string)
- `"anchorCharacter": "&para;"`
  - The character/text displayed and used as a hyperlink when hovering over headings.
  - Unicode characters can be used in HTML notation. Example: `&#x2693;` will render as ⚓
  - Default: The pilcrow (paragraph) sign: ¶
- `"title": "ACME Industries Wiki"`
  - Changes the title of the webpage.
  - Default: `"MDWiki"`
  - Note - this parameter does not change the title of your wiki in Google search results. Edit `mdwiki.html` directly to correct this. ([Issue #58](https://github.com/Dynalon/mdwiki/issues/58))

A sample `config.json` might thus look like this:

```
{
    "useSideMenu": true,
    "lineBreaks": "gfm",
    "additionalFooterText": "All content and images © by John Doe",
    "anchorCharacter": "#"
}
```

Note: More configuration options will be available in future versions of MDwiki.

Hint: It is adviced that you create an empty config.json in each cases, to avoid 404 errors which will not get cached by your browser. Having an `config.json` file present thus will speed up page loading (even if its empty).
