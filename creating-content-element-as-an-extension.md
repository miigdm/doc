# Creating content element as an extension

### Reference

This documentation is based on the [pxa\_booking](https://github.com/pixelant/pxa_booking) plugin/content-element.

### File structure:

```
.
├── Configuration
│   ├── FlexForms
│   │   └── flexform_booking.xml
│   ├── PageTS
│   │   └── modWizards.ts
│   ├── TCA
│   │   └── Overrides
│   │       └── tt_content.php
│   └── TypoScript
│       ├── constants.txt
│       └── setup.txt
├── README.md
├── Resources
│   ├── Private
│   │   ├── Language
│   │   │   └── Booking.xlf
│   │   └── Templates
│   │       └── Booking.html
│   └── Public
│       ├── Backend
│       │   └── Icons
│       │       └── customElement.svg 
│       └── JS
│           └── bookingForm.js
├── ext_emconf.php
├── ext_localconf.php
└── ext_tables.php
```

### Example files

In the root folder there are three files which are important, without them, it is not recognized by TYPO3 as an extension. \(egentligen bara ext\_emcomf, kanske\)

`ext_emcomf.php` should look something like this:

```
<?php

/***************************************************************
 * Extension Manager/Repository config file for ext: "NAME_OF_EXTENSION"
 *
 * Auto generated YYYY-MM-DD
 *
 * Manual updates:
 * Only the data in the array - anything else is removed by next write.
 * "version" and "dependencies" must not be touched!
 ***************************************************************/

$EM_CONF[$_EXTKEY] = array(
    'title' => 'TITLE OF THE EXTENSION',        <-
    'description' => '',
    'category' => 'plugin',
    'author' => 'YOUR NAME',                    <- 
    'author_email' => 'YOUR EMAIL',             <-
    'author_company' => '',
    'shy' => '',
    'priority' => '',
    'module' => '',
    'state' => 'beta',                        <-
    'internal' => '',
    'createDirs' => '',
    'modify_tables' => '',
    'clearCacheOnLoad' => 0,
    'lockType' => '',
    'version' => '1.0.0',                    <-
    'constraints' => array(
        'depends' => array(
            'extbase' => '7.6',                <-
            'fluid' => '7.6',                <-
            'typo3' => '7.6'                <-
        ),
        'conflicts' => array(
        ),
        'suggests' => array(
        ),
    ),
);
```

Please take note of the arrows, remove them and change the input needed.

`ext_localconf.php` this file points to the flexform file:

```
<?php
defined('TYPO3_MODE') or die();


if (TYPO3_MODE === 'BE') {

    \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addPageTSConfig(
        '<INCLUDE_TYPOSCRIPT: source="FILE:EXT:pxa_booking/Configuration/PageTS/modWizards.ts">'
    );
}
```

`ext_tables.php` this file is where you specify the location and file for the icon, that will be displayed in the backend when selecting the element:

```
<?php
if (!defined('TYPO3_MODE')) {
    die('Access denied.');
}

$contentElementIconFilePrefix = 'EXT:' . $_EXTKEY . '/Resources/Public/Backend/Icons/';

if (TYPO3_MODE === 'BE') {
    /** @var \TYPO3\CMS\Core\Imaging\IconRegistry $iconRegistry */
    $iconRegistry = \TYPO3\CMS\Core\Utility\GeneralUtility::makeInstance(\TYPO3\CMS\Core\Imaging\IconRegistry::class);
    $iconRegistry->registerIcon(
        'content-element-bookingform',
        \TYPO3\CMS\Core\Imaging\IconProvider\SvgIconProvider::class,
        ['source' => $contentElementIconFilePrefix . 'customElement.svg']
    );

    \TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addStaticFile(
        $_EXTKEY,
        'Configuration/TypoScript',
        'Booking content element'
    );
}
```

In the configuration folder there are four folders: `FlexForms`, `PageTS`, `TCA` `TypoScript`.

`FlexForms` folder contains the flexform file, where you can add the necessary fields for input, checkboxes or other.

`PageTS` folder contains the the typoscript file where you can define in which tab the element will be displayed in backend.

`TCA` folder contains another folder `Overrides` which contains the `tt_content.php` file. This file is where the palette is added. An important snippet when creating the new content element palette is:

```--palette--;LLL:EXT:frontend/Resources/Private/Language/locallang\_ttc.xlf:palette.access;access,
locallang_ttc.xlf:palette.access;access,
--div--;LLL:EXT:gridelements/Resources/Private/Language/locallang_db.xlf:gridElements,
tx_gridelements_container,tx_gridelements_columns,
--div--;LLL:EXT:gridelements/Resources/Private/Language/locallang_db.xlf:gridElements
```

Without it, when adding the new element in a grid, the column placement will show `[INVALID VALUE ("-1")]`.

`TypoScript`folder contains the `constans.txt` and `setup.txt` files. In the setup.txt file you can make your new content inherit all properties from the lib.fluidContent, which might be necessary sometimes.

In the Resources folder there are two folders, `Private`and `Public`.

The `Private` folder contains `Language`folder with a .xlf file for the labels, and `Template` folder for the template which will be rendered in frontend.

The `Public` folder has the `Backend` folder with the `Icons` folder, which will contain the icon for your new element when selecting it in the backend. There are other folders which might be needed here, it depends on your element. If you need do add JavaScript or CSS, then it should be put into this folder.

### Instructions

Either clone the [pxa\_booking](https://github.com/pixelant/pxa_booking) and make the necessary changes to the files, or create a new folder with the necessary structure and files.

