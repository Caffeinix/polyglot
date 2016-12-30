# Polyglot, a conlang wordlist constructor

> NOTE: Polyglot is currently **incomplete**!  I am making it available in the hopes that
> you will find it useful in its current state, but at the time of this writing none
> of the UI is hooked up.

## What it does

Polyglot generates lists of words for constructed languages.  To use it, you first supply a list of existing words that you've come up with to decide the "flavor" of the language,
and specify a set of syntactic rules that define what valid words in the language look like.  Polyglot will then use your seed list to generate potential new words, validating each one against the rules you specify and throwing out any that don't match.

## How it works

Polyglot uses a Markov chain generator, so the words it comes up with will tend to resemble the existing words.  It will invent prefixes, suffixes, and roots that will show up in multiple words, which you can then invent meanings for later.  For this to work well, you should train Polyglot on as many existing words as possible, and try to make them as diverse as possible.  For example, if none of the words in your training list contain the letter "x", Polyglot will assume that letter doesn't exist in your language's alphabet and will not generate any words that contain it, even if you have no rules forbidding it.  When Polyglot comes up with new words you like, you can add them to the training data, but bear in mind that this won't make your words more diverse, so for best results, seed it with some new original words every now and then as well.

If you find the rule builder befuddling, reading up on [Phonotactics](https://en.wikipedia.org/wiki/Phonotactics) may help.  You can also just ignore the rules and manually accept or reject new words as Polyglot comes up with them, but this will get tedious.  Being able to specify rules like "no doubled vowels" will make your life easier.

## How to install it

Polyglot runs in your browser.  I've currently only tested it in Chrome, but it should theoretically work in Firefox as well.  To install it, clone or download this repository and `cd` to the `polyglot` directory.  Make sure [NPM](https://www.npmjs.com/) is installed (either manually or via a package manager like `apt-get` or Homebrew), and then:

```sh
npm install -g polymer-cli
npm install -g bower
bower install
polymer serve
```

Navigate to [localhost:8080](http://localhost:8080) to see the app.
