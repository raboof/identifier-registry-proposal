# Apache Software Identification

There are several ways to identify software products, for example
when sharing information about which software is present in a system,
or when sharing information about (potential) security issues in software:

* ecosystem-specific names (such as Linux distribution package names, names on public repositories such as [Maven Central](https://maven.org/), etc)
* [CPE](https://nvd.nist.gov/products/cpe) prefixes
* [Package URLs](https://github.com/package-url/purl-spec) (`purl`s)

This registry is meant to correlate corresponding identifiers from
the various types:

* `community.json` contains mappings for which we assigned a tentative name because there was a need for it, but which have not yet been confirmed by their respective PMC's.
* Other `.json` files, named after their PMC id, contain mappings that have been confirmed by the PMC.

## Granularity

Different artifacts that represent the same body of code (such as the
source module and the binary module, or the same module compiled for
different Scala versions) may have the same basic name, and be
distinguished by adding qualifiers.

Artifacts that (also) contain different software, such as Docker
containers or binary packages that also include 3rd-party dependencies,
should have unique names even without taking into account qualifiers.

## Format

Identifiers start with the (P)PMC ID (without any 'incubator'/'incubating' indicators). 

They are further formatted so they can be trivially used as `purl` by adding the `pkg:asf/` prefix, meaning they may be amended with a single `/` followed by a name consisting of alphanumeric characters, dashes and dots. After that, a `?` and optional qualifiers may be included.

## `purl` mapping

Each entry maps to exactly one `purl` of the `asf` type, and may in the
future be associated with additional `purl` names in other types.

## `CPE` mapping

Ideally each entry would correspond to a single CPE prefix, however in
practice some CPE's span multiple entries.

## Ecosystem mapping

Ideally each entry maps to a single name in each ecosystem where it is
relevant.
