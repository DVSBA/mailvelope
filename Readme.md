# Mailvelope

Mailvelope is a browser extension for Google Chrome and Firefox that allows secure email communication based on the OpenPGP standard. It can be configured to work with arbitrary Webmail provider.

## OpenPGP backends

Mailvelope uses the following OpenPGP implementation

  - [OpenPGP.js](http://openpgpjs.org/) for the Chrome Extension and for the Firefox Addon

## Status

  - Chrome Extension: _beta_
  - Firefox Addon: _beta_

## Installation

Mailvelope is available in the Chrome Web Store:
https://chrome.google.com/webstore/detail/kajibbejlbohfaggdiogboambcijhkke

Check the [releases](https://github.com/toberndo/mailvelope/releases) section for latest builds of Firefox and Chrome installation packages.

## Build instructions

If you don’t have grunt and bower installed, yet:

    npm install -g grunt-cli bower

and then get and build the sources:

    git clone git://github.com/toberndo/mailvelope.git
    cd mailvelope
    git submodule update --init
    cd dep/chrome/openpgpjs
    npm install && grunt
    cd ../../firefox/openpgpjs
    npm install && grunt
    cd ../../..
    npm install && bower install && grunt

#### Chrome

    grunt dist-cr

The extension will be in `dist/mailvelope.chrome.zip`.

#### Firefox

    grunt dist-ff
    
This will get you the latest firefox addons-sdk to build the addon.

The addon will be in `dist/mailvelope.firefox.xpi`.

#### Development

Update your local repository:

    # inside mailvelope folder
    cd dep/chrome/openpgpjs
    git pull origin master && grunt
    cd ../../firefox/openpgpjs
    git pull origin master && grunt
    cd ../../..
    grunt
    # continue with 'grunt dist-cr' or 'grunt dist-ff'

There are a few more tasks available through grunt:

* watch source code for changes and recompile if needed:

    grunt watch

* reset repository

    grunt clean

## Website

http://www.mailvelope.com

## Licence

Use of this source code is governed by the GNU AFFERO GENERAL PUBLIC LICENSE that can be found in the LICENSE file.

## About

written by Thomas Oberndörfer <toberndo@yarkon.de>  
Blog: http://www.chasinclouds.com/  
follow me on [Twitter](https://twitter.com/#!/toberndo)  
