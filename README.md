[![Build Status](https://travis-ci.com/indic-dict/stardict-sanskrit.svg?branch=master)](https://travis-ci.com/indic-dict/stardict-sanskrit)

Table of content

- [Dictionary user instructions](#dictionary-user-instructions)
   - [Grab latest files to use for with my stardict compatible program.](#grab-latest-files-to-use-for-with-my-stardict-compatible-program.)
   - [Dictionary program recommendations and download help for mobile devices](#dictionary-program-recommendations-and-download-help-for-mobile-devices)
- [Dictionary developer instructions](#dictionary-developer-instructions)
   - [Initial setup.](#initial--setup.)
   - [Update dictionary files](#update-dictionary-files)
     - [To force update dictionary files](#to-force-update-dictionary-files)
   - [Dictionary popularity metrics](#dictionary-popularity-metrics)
   - [Other notes](#other-notes)
   - [Cologne to babylon convertor](#cologne-to-babylon-convertor)

# Dictionary user instructions
## Grab latest files to use for with your stardict compatible program.
Options:
* See tips in <https://sanskrit-coders.github.io/dictionaries/offline/>
* Just download and extract one of the below archives:
  - Usually very outdated [all_dicts_stardict_sanskrit.tar.gz](https://archive.org/download/stardict_collections/all_dicts_stardict-sanskrit.tar.gz)

## Dictionary program recommendations and download help (esp for mobile devices)
* <https://sanskrit-coders.github.io/site/pages/dictionaries/offline.html>

# Dictionary developer instructions
- You can see and replicate the virtual machine setup that travis builds use - See [.travis.yml](https://github.com/indic-dict/stardict-sanskrit/blob/master/.travis.yml) .

## Organization
- Dictionaries are stored in multiple repositories under [indic-dict](https://github.com/indic-dict/), for example: stardict-sanskrit-vyAkaraNa, stardict-kannada etc.. 
- Some external pre-built dictionaries also on archive.org (as in the case of stardict-english).

## Builds
- Dictionaries are built with [travis-ci](https://travis-ci.com/indic-dict) and deployed to gh-pages branch of the repository. For example:
  - [stardict-sanskrit/gh-pages](https://github.com/indic-dict/stardict-sanskrit/tree/gh-pages/) from [stardict-sanskrit](https://github.com/indic-dict/stardict-sanskrit)
  - [stardict-tamil/gh-pages](https://github.com/indic-dict/stardict-tamil/tree/gh-pages/) from [stardict-tamil](https://github.com/indic-dict/stardict-tamil)

## Latest stardict binaries
Sometimes, latest stardict binaries may be required.

- Extract the latest stardict tools package (<https://sourceforge.net/projects/stardict-4/files/3.0.1/stardict-tools-3.0.1.tar.bz2/download>) in ~/stardict/tools directory. Then do `cd stardict/tools` and build it (Run `./configure` and `make` as described in the INSTALL file in the directory - but don't remove the compiled binaries from the src directory.).
  * A shortcut if you are running Linux on a 64 bit computer: Just `git clone --depth 1 https://github.com/sanskrit-coders/stardict` in your home directory.
- Install stardict-tools-git
  - Replaces outdated step: `git clone git@github.com:sanskrit-coders/stardict.git`. Then build it with ./configure, make etc..

## Dictionary popularity metrics
* For properly *release*ed dictionaries, one can get stats as [shown here](http://mmilidoni.github.io/github-downloads-count/).

## Other notes
Recipe to convert decompiled en-head dictionaries from ajita to sa-head dictionaries: ^.+\t(.+?)\.  should be replaced by \1\t

## Cologne to babylon convertor
https://github.com/sanskrit-lexicon/cologne-stardict - make_babylon.py is the workhorse.
