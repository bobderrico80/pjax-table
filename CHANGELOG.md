# Change Log
All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## [Unreleased][unreleased]
- base ajax plugin in consideration

# [1.4.4] - 2015-07-01
### Changed
- namespace updates to exports and test files

# [1.4.3] - 2015-06-30
### Added
- added an event object to plugins's `options`

# [1.4.2] - 2015-06-29
### Added
- added an optional function "syncQueryFn" for syncing the query state from attributes not explicit in the table js, e.g. search and filter status

# [1.4.1] - 2015-06-08
### Changed
- change data('url') to data('pjax-url') fixing a previous break in compatibility with python

# [1.4.0] - 2015-06-05
### Added
- auto init tables are now configurable through a global config object window.PjaxTableConfig

# [1.3.0] - 2015-06-04
### Added
- a public load method which resembles refresh but accepts load parameters to be used by ajax/pjax
- the public update method now accepts an additional param which is the load paramaters to be used by ajax/pjax

# [1.2.6] - 2015-06-04
### Added
- Added a queryState option so that you can initialize the table with a state that is separate from / in addition to the state synced from data attributes. The use case is for other
page components which drive table state but are not tied directly to the table, such as a date picker that provides a date range.

# [1.2.5] - 2015-05-28
### Changed
- changed the url fallback to be window.location.pathname ( the path without the query string ) which fixes a bug with query arg duplication. Bug was not completely addressed in 1.2.4

# [1.2.4] - 2015-05-28
### Changed
- changed the url fallback to be empty string ( the current base url ) which fixes a bug with query arg duplication

# [1.2.3] - 2015-05-11
### Changed
- fix search element reference

# [1.2.2] - 2015-05-11
### Changed
- change keydown to keyup
### Removed
- preventDefault from keydown which was breaking the input

# [1.2.1] - 2015-05-11
### Changed
- fixes a variable reference bug in table search
- improves the widget constructor for search to match that of pjaxTable

# [1.2.0] - 2015-04-28
### Changed
- updated current-page and current-perpage attribute location to be on the table element, this is an adjustment
similar to 1.1.0, to be consistent with the python library

# [1.1.0] - 2015-04-16
### Changed
- updated current-sort-order and default-sort-order to use "direction" instead of "order", although technically
a breaking change, it is a fix to be in line with the current python library

# [1.0.4] - 2015-03-30
### Added
- added travis-ci integration, .travis.yml and test script in package.json are now configured to run tests on push

### Changed
- moved primary docs from the readme to docs/index.html which is the github pages index
- updated markdown tables to html tables to fix rendering
- update bower.json for publish

# [1.0.3] - 2015-03-29
### Changed
- moved standalone index.html page to the standalone directory and adjusted paths

# [1.0.2] - 2015-03-29
### Added
- undefined reference in closure

### Changed
- allowed method checking uses charAt instead of an array of strings and indexOf
- prevPage handler now prevents negative numbers with Math.max
- total rows parsing now uses bitwise or

# [1.0.1] - 2015-03-24
### Removed
- remove min-height from table-cell-wrapper class

# [1.0.0] - 2015-03-24
### Added
- pjax table now defines its own plugin code
- calling methods through jquery, i.e. $el.pjaxTable('update') only allows
methods defined in the allowedMethods array. All method calls can otherwise 
be accessed by referencing the instance directly.

### Changed
- fiftyTable is now pjaxTable
- data attributes and styles that used "fifty" in the name are now "pjax"
- pjax table now uses the prototype pattern
- event names have be redesigned to follow "table:event" scheme
- push state enabled by default under flag pushState, or data-push-state
- ajax disabled by default under flag ajaxOnly, or data-ajax-only
- pjaxUrl is now just "url" and configurable through options or as data-url attribute
- data-pjax-container now falls back to the id of the table container
- search_id option is now camelCased as searchId
- the markup shown for no table data is now a configurable function, noDataTemplate, which recieves the number of
columns in the table as a param.
- the createSortQuery function is now configurable, so the application can specify a sort query which appropriately
matches the server implementation
- sort-direction is now sort-order

### Removed
- data-table-id and total-rows attribute on the wrapper. A wrapper is no longer required
and all data attributes should be defined on the table element.
- tooltip initialization on load has now been decoupled, and should be done by an initializing
script on the 'table:load' event.
- custom-filters query addition removed, use table:load and updateParameters for customization

# [0.2.0] - 2015-03-10
## Added
- load mask support with spin.js under an enableLoadMask flag
- loadMaskConfig for spin.js configuration

# [0.1.7] - 2015-03-10
## Changed
- widget upgraded to 1.0.0
- widget registration requires flag for the revealing module

