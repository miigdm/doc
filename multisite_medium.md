# Multisite Medium

When working with a multisite installation that are based on the **Medium** value in t3kit. There may be a need to have custom CSS for one of the sites, that can be achieved with the following steps.

By default  t3kit’s TS is using less and css:

```
  page.includeCSS.customLess = fileadmin/custom/css/custom.less
  page.includeCSS.customCss = fileadmin/custom/css/custom.css
```

If the frontend (FE) will need not only to change theme variables in backend (BE). But also modify Less/CSS for specific site then this site typoscript (TS) should override default custom to new:

```
  page.includeCSS.customLess = fileadmin/custom/css/custom_NEWSITE.less
  page.includeCSS.customCss = fileadmin/custom/css/custom_NEWSITE.css
```

The corresponding files should be created in fileadmin/custom/css/ also.