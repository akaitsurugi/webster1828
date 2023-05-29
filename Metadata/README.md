# Webster's Dictionary 1828

## Introduction

The purpose for creating this is to preserve, and promote the use of, the 1828 version of Webster's Dictionary. After reviewing several dictionaries, I found this one to have the best definitions, especially for understanding things written during the 17<sup>th</sup>-19<sup>th</sup> centuries. Dictionaries that came out in the 20<sup>th</sup> and 21<sup>st</sup> centuries are lackluster compared to the previous ones, since post-modernists felt that language was another "social construct" that needed to be torn apart and turned into nothing. You can clearly see this by comparing definitions over time, where they become more vague and sometimes even the opposite of what they were originally.

There are already online versions of the 1828 dictionary available, but I wanted some offline options so that I could avoid the massive distraction of the Internet while studying. I also converted the [1844 dictionary](https://codeberg.org/christianlibertyinstitute/webster1844) since the source was available and it isn't that bad, but I will only be updating this version. The 1913 dictionary file was a mess, so I didn't convert that, but there are [StarDict](http://jsomers.net/blog/dictionary) and [Apple](https://github.com/websterParser/WebsterParser) formats for the 1913 dictionary out there already.

## A Work in Progress

I try to work on this when I can, but if you'd like to contribute to this project by fixing some formatting or spelling errors, please open a pull request. There are approximately 600 words that still need to be fixed and added to the `webster1828.csv` file, located in the `words-in-progress.csv` file. To fix these, I usually review the entries in the scans of the original dictionary on archive.org ([Vol. 1](https://archive.org/details/americandictiona01websrich) and [Vol. 2](https://archive.org/details/americandictiona02websrich)). So far, I've noticed a lot of the missing entries are ones that use the same definition as another word, so I just copy the existing definition from `webster1828.csv`. There are also some minor issues like unclosed html tags, but I couldn't find an easy way to clean these.

Note that the `words-in-progress.csv` file contains more columns than the `webster1828.csv` file. Only two columns are used in `webster1828.csv`: one for the word and the other for the definition. The `words-in-progress.csv` has some definitions that may be correct, but are broken between multiple columns. The "word" column is the one used for the word.

## Installation Instructions

- Apple Mac OS X/macOS: Unzip the archive and copy the .dictionary file to `/Library/Dictionaries/` for all users or `~/Library/Dictionaries/` for the current user. If the Dictionary app isn't working properly, you may need to run this in Terminal: `rm ~/Library/Caches/com.apple.DictionaryServices/DictionaryCache.plist` and restart the app to clear out the cache.
- SWORD module: The best way to install is using the official CrossWire repo, but an archive has been provided for local installations.
- KOReader: Unzip the StarDict archive and copy the directory to `/.adds/koreader/data/dict/`
- Amazon Kindle: Unzip the archive and copy the .mobi file to `/documents/dictionaries/` You may need to restart your Kindle before it will work properly.
- Rakuten Kobo: Rename the `webster1828-x.x-kobo.zip` to `dicthtml-pt-en.zip` (which will replace the Portuguese to English dictionary, use another language if you don't want that) and copy it to `/.kobo/dict/`
- Plato: Unzip the StarDict archive and copy the directory to `/.adds/plato/dictionaries/`

This has been tested with:
- The Dictionary.app in Mac OS X Snow Leopard. It may work with earlier versions and should work with whatever garbage OS Apple is putting out now.
- The SWORD module using MacSword and Xiphos.
- KOReader (2023 release) running on a Kobo Aura H2O.
- An Amazon Kindle Paperwhite.
I don't use Kobo's built-in dictionary or Plato, so I cannot vouch for the quality of those.

## Building From Source

I am using [PyGlossary](https://github.com/ilius/pyglossary) to convert the CSV file to the other dictionary formats. The directory `Metadata` contains the files needed to make the title show up correctly on devices.