MSS - CSS Preprocessor and Parser written in PHP
=======
[![Latest Stable Version](https://poser.pugx.org/mysheet/mysheet/v/stable.svg)](https://packagist.org/packages/mysheet/mysheet) [![Total Downloads](https://poser.pugx.org/mysheet/mysheet/downloads)](https://packagist.org/packages/mysheet/mysheet) [![Monthly Downloads](https://poser.pugx.org/mysheet/mysheet/d/monthly.png)](https://packagist.org/packages/mysheet/mysheet) [![Latest Unstable Version](https://poser.pugx.org/mysheet/mysheet/v/unstable.svg)](https://packagist.org/packages/mysheet/mysheet) [![License](https://poser.pugx.org/mysheet/mysheet/license.svg)](https://packagist.org/packages/mysheet/mysheet)

**Official website**: http://mss.flydigo.com (not available at the moment)

**Get started**: http://mss.flydigo.com/getStarted (not available at the moment)

**Documentation**: http://mss.flydigo.com/docs (not available at the moment)

**Author**: Alexandr Gilevich 


What is it?
------
MSS is an open-source CSS preprocessor and parser written in PHP with support for extensions / plug-ins. It has full backward compatibility with pure CSS. MSS has been primarily inspired by the simplicity of Stylus for Node.js. It also has some key features from other CSS preprocessors such as SASS and LESS. 


Key Features
---

- Dynamic stylesheet modification at runtime (proving to be useful in building Content Management Systems (CMS) for the use by people with little-to-no prior experience in CSS)
- Extensibility and support of plugins
- Support for variables and math expressions
- Color manipulation with various color systems (HSL, RGB, etc.)
- Mix-ins (common style templates)
- Custom language which uses [indentation style](https://en.wikipedia.org/wiki/Indentation_style) (think of Python)
- Full backward compatibility with pure CSS (i.e. curly-bracket style)


Examples
---

**Example #1 - hierarchical structure**:

    body
        padding 0
        margin 0
        .wrapper
            margin 0 auto
            width 50%

results in the following CSS:

    body {
        padding: 0;
        margin: 0
    }

    body .wrapper {
        margin: 0 auto;
        width: 50%
    }

**Example #2 - mixins**:

    @mixin filter-grayscale(percent)
        -webkit-filter: grayscale($percent);
        -moz-filter: grayscale($percent);
        -ms-filter: grayscale($percent);
        -o-filter: grayscale($percent);
        filter: grayscale($percent);

    img
        filter-grayscale 100%
    img:hover
        filter-grayscale 0%

results in the following CSS:

    img {
        -webkit-filter: grayscale(100%);
        -moz-filter: grayscale(100%);
        -ms-filter: grayscale(100%);
        -o-filter: grayscale(100%);
        filter: grayscale(100%)
    }

    img:hover {
        -webkit-filter: grayscale(0%);
        -moz-filter: grayscale(0%);
        -ms-filter: grayscale(0%);
        -o-filter: grayscale(0%);
        filter: grayscale(0%)
    }

**Example #3 - arithmetic expressions and comments**:

    .object
        color #a50c5b - 50sat /* decrease saturation by 50% */
        background-color #a50c5b + 50lt /* make color lighter by 50 percent */

results in the following CSS:

    .object {
        color: #79385a;
        background-color: #fab6d9
    }

**Example #4 - arithmetic expressions in combine with variables**:

    $wrapper_height = 50%
    .wrapper
        height $wrapper_height
        top $wrapper_height / 2

results in the following CSS:

    .wrapper {
        height: 50%;
        top: 25%
    }

and much much more...

License
---

MSS is open-source project. It is licensed under Apache License, Version 2.0. 
