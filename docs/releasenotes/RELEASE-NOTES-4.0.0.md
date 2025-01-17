# Semantic MediaWiki 4.0.0

Not released yet - under development

## Summary

This release mainly brings support for recent versions of MediaWiki.
A small number of fixes and enhancements where also made. Anyone using MediaWiki 1.35
is recommended to upgrade. Using versions of SMW older than 4.0 on MediaWiki 1.36 or
above is not supported.

## Compatibility

* Dropped support for MediaWiki older than 1.35
* Dropped support for PHP older than 7.4
* Improved support for MediaWiki 1.35
* Added support for MediaWiki 1.36 and MediaWiki 1.37
* Improved compatibility with MediaWiki 1.38, though this version still has many issues

For more detailed information, see the [compatibility matrix](../COMPATIBILITY.md#compatibility).

## Upgrading

Calling `wfLoadExtension` is now required in `LocalSettings.php`. Example:

```php
wfLoadExtension( 'SemanticMediaWiki' );
enableSemantics( 'example.org' );
```

There is no need to run `update.php` or any of the rebuild data scripts.

When a triplestore is used with the SPARQL feature `SMW_SPARQL_QF_COLLATION`, the script
`maintenance/updateEntityCollation.php` must be run (the collation sort key algorithm was changed).

## New features

* [Added namespace flag to dumpRDF.php to allow dumping a list of namespaces](https://github.com/SemanticMediaWiki/SemanticMediaWiki/issues/5031)

## Enhancements

* [Special properties of type Page are now displayed consistently](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/5111)
* [The maintenance page is no longer indexed my search engines](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/4967)
* [Improved performance on multi-database setups](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/5002)
* [Improved support for recent ElasticSearch versions](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/4976)
* [Updated the logo](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/5013)

## Bug fixes

* [Fixed the collation key for triplestores with the SPARQL feature `SMW_SPARQL_QF_COLLATION`](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/4997)
* [Fixed occasional type errors in the ElasticStore](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/5033)
* [Fixed boolean property support on PostgreSQL](https://github.com/SemanticMediaWiki/SemanticMediaWiki/pull/5098)
