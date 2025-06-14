# Reflection

After completing these challenges, take a few minutes to answer the following questions:

1.  How did using Figma designs as references affect your coding process?

Figma design components have specific information including element size, orientation, hexadecimal color, and font.  I used this information to get exact values for variables in the coding process.

2.  What challenges did you encounter when aligning your code with the design specifications?

Bootstrap uses utility classes and premade components that can save users time - but these are sharply limited.  


3.  How can the feedback and community resources on Frontend Mentor help you improve as a developer?

It looks like Frontend Mentor may have tools to assess accuracy of submitted challenges; I would imagine it would offer specific feedback on what things were missed.  Feedback and community resources are always useful to developers, as getting outside feedback is always useful.

## Reference Notes

Bootstrap version has been updated since lab reference created.  If components do not work, change to current version.

It seems to use custom colors with Bootstrap, that SASS must be used, requiring importing files and modifying.  I think that is beyond the scope of the lab.

https://getbootstrap.com/docs/4.0/layout/utilities-for-layout/
https://getbootstrap.com/docs/5.0/customize/sass/
https://www.freecodecamp.org/news/how-to-customize-bootstrap-with-sass/
https://getbootstrap.com/
https://getbootstrap.com/docs/5.3/getting-started/download/
https://getbootstrap.com/docs/5.3/customize/sass/

## Bash Commands

npm i bootstrap@5.3.6
npm install -g sass

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
| display: flex; | d-flex |
| height: 100vh; | vh-100 |
| justify-content: center; | justify-content-center |
