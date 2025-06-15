# Reflection

After completing these challenges, take a few minutes to answer the following questions:

1.  How did using Figma designs as references affect your coding process?

Figma design components have specific information including element size, orientation, hexadecimal color, and font.  I used this information to get exact values for variables in the coding process.

2.  What challenges did you encounter when aligning your code with the design specifications?

Bootstrap uses utility classes and premade components that can save users time - but these are sharply limited.  Below sections document some of my exciting adventures in addressing these differences.

3.  How can the feedback and community resources on Frontend Mentor help you improve as a developer?

It looks like Frontend Mentor may have tools to assess accuracy of submitted challenges; I would imagine it would offer specific feedback on what things were missed.  Feedback and community resources are always useful to developers, as getting outside feedback is always useful.

## Summary of Bootstrap Use

The utility of Bootstrap (and CSS frameworks in general) is also its weakness - predefined code.

I can build something with Bootstrap quickly, using Bootstrap's predefined code to speed the process - and accept the limitations Bootstrap imposes.  Or I can build something and write my own CSS, not being subject to Bootstrap's limitations.

Or I can take ten times the time it would take me to write my own CSS to build something in Bootstrap.  With Bootstrap, the more I build to spec, the less I use Bootstrap's native advantages.  The more I build to spec in Bootstrap, the more I must use custom workarounds that take time to implement, that additionally complicate the code and make it less accessible.

With this assignment, I had to choose between meeting design specifications and assignment requirements, given limited time.  With a previous assignment (the ARIA lab), I focused on building an accessible website that I thought fit the requirements.  I came to understand, however, that I needed to be more aggressive about interpreting what assigments require.

The first assignment's first image inside the card is a good example.  Some hours into the assignment, I discovered !important and realized I could use it to override Bootstrap definitions.  I realized, however, that this could be interpreted as contrary to the intent of the assignment, so chose to try to implement SASS, which I thought offered the best chance of using Bootstrap while still fulfilling assignment requirements.

Several hours later, I'd read through documentation and additional articles, installed locally as that was required to use SASS, and implemented the design spec.  I had thought I could implement the rest of the assignment requirements by nesting built components inside components built to meet assignment requirements, but I realized that couldn't really be done.

At this point I'd spent a full day and a half on the assignment, which was quite a lot more than the time I'd allotted, and having looked over the requirements for the SBA which is also due quite soon, I decided to cut things short, instead of trying to re-adapt the project to work with Bootstrap's 12-column system.  At some point, trying to nest divs within divs within divs within divs and doing complicated workarounds completely goes against the entire supposed point of Bootstrap - which is that it's supposed to be easy and fast.

## Reference Notes

Bootstrap version has been updated since lab reference created.  If components do not work, change to current version.

It seems to use custom colors with Bootstrap, that SASS must be used, requiring importing files and modifying.  I think that is beyond the scope of the lab.

https://getbootstrap.com/docs/4.0/layout/utilities-for-layout/
https://getbootstrap.com/docs/5.0/customize/sass/
https://www.freecodecamp.org/news/how-to-customize-bootstrap-with-sass/
https://getbootstrap.com/
https://getbootstrap.com/docs/5.3/getting-started/download/
https://getbootstrap.com/docs/5.3/customize/sass/
https://getbootstrap.com/docs/5.3/utilities/background/
https://sass-lang.com/documentation/breaking-changes/css-vars/
https://sass-lang.com/documentation/variables/
https://getbootstrap.com/docs/4.0/utilities/borders/
https://getbootstrap.com/docs/4.0/utilities/spacing/
https://getbootstrap.com/docs/5.0/content/typography/
https://getbootstrap.com/docs/5.0/utilities/text/
https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing
https://getbootstrap.com/docs/4.0/layout/grid/
https://getbootstrap.com/docs/4.0/components/card/

https://getbootstrap.com/docs/5.1/utilities/spacing/
https://getbootstrap.com/docs/4.0/utilities/vertical-align/
https://getbootstrap.com/docs/4.0/utilities/spacing/
https://getbootstrap.com/docs/5.0/utilities/vertical-align/
https://www.geeksforgeeks.org/how-to-set-vertical-alignment-in-bootstrap/
https://getbootstrap.com/docs/5.0/utilities/api/

https://getbootstrap.com/docs/5.3/layout/grid/
https://getbootstrap.com/docs/5.0/layout/columns/

## Bash Commands

npm i bootstrap@5.3.6
npm install -g sass
sass --watch ./scss/custom.scss ./css/custom.css
sass scss/custom.scss:FirstChallenge/customsass.css

To this point, I'd downloaded Bootstrap files locally, npm installed sass, I think unsuccessfully run --watch, created various abortive custom.scss files.  Ran above while in 2025-06-14-Lab-3-3, with subdirectories scss and FirstChallenge.  custom.scss was in scss folder.  FirstChallenge contained bulk of files for FirstChallenge and did not have any customsass.css file.  customsass.css and customsass.css.map files created.  Reference bootstrap guide.

## Bootstrap Reference History

Originally Bootstrap was run off remote host files.

Lab references:

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>


Bootstrap references (updated):

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.6/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-4Q6Gf2aSP4eDXB8Miphtr37CMZZQ5oXLH2yaXMJ2w8e2ZtHTl7GptT4jmndRuHDT" crossorigin="anonymous">

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.6/dist/js/bootstrap.bundle.min.js" integrity="sha384-j1CDi7MgGQ12Z7Qab0qlWQ/Qqz24Gc6BM0thvEMVjHnfYGF0rmFCozFSxQBxwHKO" crossorigin="anonymous"></script>

Last link href reference takes precedence, so if I listed my original link href after the Bootstrap reference, mine would overwrite (possibly replace entirely) any earlier link href reference by Bootstrap.  Similarly, listing Bootstrap last would overwrite earlier css.  However, I could list my default css first and use !important; anything with !important would override even the later Bootstrap reference.

After reading I couldn't use custom colors without SASS, and that I'd need to install Bootstrap files locally and do various other things to use SASS, I initially used !important in CSS to override CSS.  The assignment is odd in that we didn't really cover using SASS (though it was mentioned in class, we didn't go through any walkthrough of use), yet we're supposed to use Bootstrap which will require SASS.

Require, because though using Bootstrap presets to match colors might work out more or less, presets on size must be 25 percent increments of the parent component.  There might be some way to use Bootstrap's preset media query breakpoints to achieve custom sizing

https://getbootstrap.com/docs/4.1/layout/overview/

but that's frankly too much work for too-specific code that can't be reused.

After downloading Bootstrap files locally, I ended up using multiple references to "bootstrap.min.css".  I might reflect on exactly why I shifted files around, but I won't get into that.

I also had multiple locations and files for custom.scss, which I eventually used to create a "customsass.css" file that I then used as a reference.  That file was generated from a bash command input, which looked at the custom.scss file I'd created, read the import command, and then did a lot of stuff to create a very lengthy customsass.css file.

## Rewriting custom.scss

After each rewrite, I'd run the bash command to regenerate customsass.css.

### Initial

@import "../node_modules/bootstrap/scss/bootstrap";

$slate900: #1F314F;
$slate500: #68778D;
$slate300: #D5E1EF;

Fail.  Running short of time, I tried overwriting existing properties.
https://getbootstrap.com/docs/5.0/utilities/background/

$primary: #1F314F;
$secondary: #68778D;
$success: #D5E1EF;

Fail.  Re-referenced

https://www.freecodecamp.org/news/how-to-customize-bootstrap-with-sass/

noticed I had imported at the start of the file instead of the end, changed order.

Success.

Attempted modifying custom.scss

$primary: #1F314F;
$secondary: #68778D;
$success: #D5E1EF;

$mistercoal: #1F314F;
$misterslate: #68778D;
$misterfog: #D5E1EF;

.prismaticcoal {
  background-color: $mistercoal;
}

.prismaticslate {
  background-color: $misterslate;
}

.prismaticfog {
  background-color: $misterfog;
}

Applying HTML class prismaticcoal did nothing, as expected.  Ran sass scss/custom.scss:FirstChallenge/customsass.css in bash, then worked.

## CSS to Bootstrap - What Can't Be Done

For following, could use !important to override.

Color is set to a wide yet limited range of specific colors, unsuitable for meeting most design specs.

Width and height are set to 25% increments of parent element, unsuitable for meeting most design spec.

margin-top is set to fractions of $spacer; default 1rem = 16 pixels.  But the sizes I use don't work with the fractions available, and rem's actual pixel size may change depending on user settings.

font-family, font-size, font-weight do not use measurements that allow design specs to be accurately created.  line-height documentation does not seem to offer any measurement that allow design specs to be accurately created.  letter-spacing seems not to be available in Bootstrap (Fast Bootstrap seems to be a custom addon but were I using resources not advised in the assignment I'd create React components myself).

## CSS to Bootstrap Class Reference

| CSS | Bootstrap |
|:--------------------------|:--------------|
| align-items: center; | align-items-center |
| background-color: white | bg-white |
| border-radius: 10px; | rounded (cannot specify px) or rounded-circle |
| display: flex; | d-flex |
| flex-direction: column; | flex-column |
| height: 100vh; | vh-100 |
| justify-content: center; | justify-content-center |
| margin: (?) | (set to $spacer, based on ?rem) |
| overflow: hidden; | overflow-hidden |
| text-align: center; | text-center |
| width: auto; | w-auto |