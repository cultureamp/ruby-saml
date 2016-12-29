# Ruby SAML [![Build Status](https://secure.travis-ci.org/onelogin/ruby-saml.png)](http://travis-ci.org/onelogin/ruby-saml) [![Coverage Status](https://coveralls.io/repos/onelogin/ruby-saml/badge.svg?branch=master%0A)](https://coveralls.io/r/onelogin/ruby-saml?branch=master%0A) [![Gem Version](https://badge.fury.io/rb/ruby-saml.svg)](http://badge.fury.io/rb/ruby-saml)

## Updating from 1.3.x to 1.4.X

Version `1.4.0` is a recommended update for all Ruby SAML users as it includes security improvements.

## Updating from 1.2.x to 1.3.X

Version `1.3.0` is a recommended update for all Ruby SAML users as it includes security fixes. It  adds security improvements in order to prevent Signature wrapping attacks. [CVE-2016-5697](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-5697)

## Updating from 1.1.x to 1.2.X

Version `1.2` adds IDP metadata parsing improvements, uuid deprecation in favour of SecureRandom, refactor error handling and some minor improvements

There is no compatibility issue detected.

For more details, please review [the changelog](changelog.md).

## Updating from 1.0.x to 1.1.X

Version `1.1` adds some improvements on signature validation and solves some namespace conflicts.

## Updating from 0.9.x to 1.0.X

Version `1.0` is a recommended update for all Ruby SAML users as it includes security fixes.

Version `1.0` adds security improvements like entity expansion limitation, more SAML message validations, and other important improvements like decrypt support.

### Important Changes
Please note the `get_idp_metadata` method raises an exception when it is not able to fetch the idp metadata, so review your integration if you are using this functionality.

## Updating from 0.8.x to 0.9.x
Version `0.9` adds many new features and improvements.

## Updating from 0.7.x to 0.8.x
Version `0.8.x` changes the namespace of the gem from `OneLogin::Saml` to `OneLogin::RubySaml`.  Please update your implementations of the gem accordingly.
>>>>>>> 1.4.0

## Overview

Supports multiple X509 certificates in metadata.
Stores fingerprints and certs in an array.
Validate response against array of fingerprints/certs.

The primary differences between this and the official gem are

- `IdpMetadataParser` will parse ALL X509 certificates in the metadata
- it stores fingerprints in `idp_cert_fingerprint_multi`
- it stores certificates in `idp_cert_multi`
- `idp_cert_multi` and `idp_cert_fingerprint_multi` are arrays
- it calls `is_valid_multi_cert?` to validates against multiple fingerprints or certs
