# Reflection

After completing these challenges, take a few minutes to answer the following questions:

1.  How did using Figma designs as references affect your coding process?

Figma design components have specific information including element size, orientation, hexadecimal color, and font.  I used this information to get exact values for variables in the coding process.

2.  What challenges did you encounter when aligning your code with the design specifications?

Bootstrap uses utility classes and premade components that can save users time - but these are sharply limited.  Below sections document some of my exciting adventures in addressing these differences.

3.  How can the feedback and community resources on Frontend Mentor help you improve as a developer?

It looks like Frontend Mentor may have tools to assess accuracy of submitted challenges; I would imagine it would offer specific feedback on what things were missed.  Feedback and community resources are always useful to developers, as getting outside feedback is always useful.

## Summary of Bootstrap Use

Bootstrap's fine if not working to spec.  But where custom colors and custom sizes need be used, Bootstrap really requires either SASS, or slapping !important all over the place, or changing design away from specs to meet Bootstrap's premade settings.

I could have thrown design specs out, or used !important, but instead I used SASS to be consistent with design specs without using a load of overrides that would make using Bootstrap fairly pointless.

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

For following, used !important to override.

Color is set to a wide yet limited range of specific colors.
Width and height are set to 25% increments of parent element.

background-color: #D5E1EF
width: 320px;
height: 499px;

## CSS to Bootstrap Class Reference

| CSS | Bootstrap |
|:--------------------------|:--------------|
| align-items: center; | align-items-center |
| background-color: white | bg-white |
| display: flex; | d-flex |
| height: 100vh; | vh-100 |
| justify-content: center; | justify-content-center |
| text-align: center; | text-center |
