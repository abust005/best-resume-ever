## Code of Conduct

1. Be respectful and courteous to one another

2. Provide constructive feedback on resume templates

3. Log any template requests as an issue with the 'template request' tag

4. Any requests for new fonts or features should be opened as an issue with the 'enhancement' tag


## Contribution Guidelines

1. If you contribute new templates, please be sure to:
    - Add new template
    - Add new App.vue file
    - Add new package.json (if new packages or fonts)

2. If you update existing templates, please be sure to:
    - Push update as a new template 

3. Do not add any generated files (such as PDFs); the repo should only contain working code.

4. All pull requests should correspond to a previously opened issue; pull requests not 
addressing open issues will not be considered. 

## Adding new templates

Table of Contents

[Templates](#templates)

[Fonts](#fonts)

[Export](#export)

<br><br>

## Templates

In the directory `src/resumes` you will find all existing templates.


### Creating New Templates

1. Create a copy of `src/resumes/template.vue`.

2. Rename file and update template name:
```javascript
let name = 'TEMPLATE-NAME';
```

3. Import the newly added template in `src/resumes/resumes.js`.

<br>
Your new resume will be now reachable at localhost:8080/#/resume/TEMPLATE-NAME.
<br>
<br>

5. Export resumes as PDF with `npm run export`. Verify export of new template.

4. Generate previews by converting PDF-files to PNG-files with `npm run preview`.

5. Add preview to `/src/pages/home.vue`:
```javascript
<div class="preview">
  <router-link v-bind:to="'/resume/TEMPLATE-NAME'">
    <div class="preview-wrapper">
      <img src="../assets/preview/TEMPLATE-NAME.png" />
      <span>left-right</span>
    </div>
  </router-link>
</div>
```

## Fonts

### Icons

This project contains the [Material Design](https://github.com/google/material-design-icons) and [Font Awesome](https://github.com/FortAwesome/Font-Awesome) icon sets.

### Included Fonts

These fonts are included:

- [Open Sans, Open Sans Condensed](https://fonts.google.com/specimen/Open+Sans)

- [Raleway](https://fonts.google.com/specimen/Raleway)

- [Roboto](https://fonts.google.com/specimen/Roboto)

- [Source Sans Pro](https://fonts.google.com/specimen/Source+Sans+Pro)


### Adding a New Font

All fonts are installed via npm. To add a new font, search for the associated npm-module. Add the module to the package.json and install it. Import the css file in `src/App.vue`.
<br>
<br>


## Export

Resumes are being exported with [Puppeteer](https://github.com/GoogleChrome/puppeteer).

### Box Shadows

[Electroshot](https://github.com/mixu/electroshot) uses Electron to generate PDF-files. Since Chrome does not export box-shadows properly, every resume uses [chrome-shadow-fixer](https://github.com/salomonelli/chrome-shadow-fixer).
