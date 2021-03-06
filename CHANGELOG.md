# Changelog

## 1.0.0
 - BUGFIX: fixed an exception after a file with imports was deleted
 - Making this 1.0.0 because no major issues have surfaced in the alpha and I think the public API is fairly stable. My outstanding TODO list is all either additive or internals-only for compatibility with ember-cli canary.

## 1.0.0-alpha.0
 - ENHANCEMENT: we now run a single Webpack build for an entire application, regardless of how many addons and/or the app itself are using ember-auto-import. This provides the best possible deduplication and minimal size. 
 - BREAKING: the build customization options have changed. It's no longer possible to customize webpack per-module, since we're running a single global webpack build. I also removed documentation on how to swap out the webpack bundler with something else, because in practice we'll want addons to be able to standardize on one strategy.
 - I'm making this a candidate for a 1.0 release because our public API is now where I want it and it seems unlikely to need breaking changes in the near future. This is an endorsement of public API stability, not implementaiton stability, which I expect to keep improving as more people adopt and report bugs.

## 0.2.5
 - BUGFIX: ensure our import analyzer always runs before babel has a chance to transpile away the imports

## 0.2.3
 - BUGFIX: switch to enhanced-resolve to get correct entrypoint discovery semantics for every case of `browser` and `module`

## 0.2.2
 - PERFORMANCE: add rebuild caching. 

## 0.2.1

 - BUGFIX: fix an exception when the app has no vendor directory

## 0.2.0

 - ENHANCEMENT: respect `module` and `browser` fields in package.json
 - ENHANCEMENT: work inside addons
 - ENHANCEMENT: add option for ignoring specific modules
 - ENHANCEMENT: use the ember app's babel settings to configure our babel parser to match
 - ENHANCEMENT: support importing non-main entrypoint modules from arbitrary NPM packages
 - ENHANCEMENT: make bundler strategies pluggable
 - ENHANCEMENT: switch default bundler strategy from Rollup to Webpack
