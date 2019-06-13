---
layout: post
title: 'Package Versioning'
date: 2016-07-15 08:44
comments: true
category: Development
---

> The content originates from [Xie's blog](http://yihui.name/en/2013/06/r-package-versioning/)

Here are some consistent rules helping us to make version numbers comprehensible if we should modify my versin numbers.

Format: `major.minor.patch`

- Major is incremented when the release contains breaking changes, all other numbers are set to 0.
- Minor is incremented when the release contains new non-breaking features, patch is set to 0.
- Patch is incremented when the release only contains bugfixes and very minor/trivial features considered necessary.

The dev notation refers to the next release, i.e.: `5.0.0-dev` is the development version leading to `5.0.0`.

For package development:

1. a version number is of the form `major.minor.patch` (`x.y.z`), e.g., `0.1.7`
2. only the version `x.y` is released to CRAN
3. `x.y.z` is always the development version, and each time a __new feature__ or a __bug fix__ or a __change __is introduced, bump the patch version, e.g., from `0.1.3` to `0.1.4`
4. when one feels it is time to release to __CRAN__, bump the minor version, e.g., from `0.1` to `0.2`
5. when a change is crazy enough that many users are presumably going to yell at you (see the illustration above), it is time to bump the major version, e.g., from `0.18` to `1.0`
6. the version `1.0` does not imply maturity; it is just because it is potentially very different from `0.x` (such as API changes); same thing applies to `2.0` vs `1.0`
