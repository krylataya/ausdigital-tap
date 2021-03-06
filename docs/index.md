**[Back to AusDigital.org](http://ausdigital.org/)**

# 1/TAP

## ADBC Transaction Access Point (TAP) Specification

 * ![raw](http://rfc.unprotocols.org/spec:2/COSS/raw.svg)
 * Editor: Chris Gough
 * Contributors: Steve Capell

##Glossary:

phrase | Definition
------------ | -------------
ausdigital-tap/2 | Version 2 of the [AusDigtial](http://ausdigital.org) [TAP](http://ausdigital-tap.readthedocs.io/) specification
ausdigital-tapgw/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [TAPGW](http://ausdigital-tap-gw.readthedocs.io/) specification
ausdigital-bill/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [BILL](http://ausdigital-bill.readthedocs.io/) specification
ausdigital-dcl/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [DCL](http://ausdigital-dcl.readthedocs.io/) specification
ausdigital-dcp/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [DCP](http://ausdigital-dcp.readthedocs.io/) specification
ausdigital-nry/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [NRY](http://ausdigital-nry.readthedocs.io/) specification
ausdigital-idp/1 | Version 1 of the [AusDigtial](http://ausdigital.org) [IDP](http://ausdigital-idp.readthedocs.io/) specification

This document describes a protocol for exchanging formal documents (such as invoices)
between businesses. TAP is a secure, decentralised, peer to peer architecture where gateways
are optional and minimally trusted.

This specification aims to support the Australian Digital Business Council
[eInvoicing initiative](https://ausdigital.github.io), and is under active development
at [https://github.com/ausdigital/ausdigital-tap](https://github.com/ausdigital/ausdigital-tap).


## Licence

Copyright (c) 2016 the Editor and Contributors. All rights reserved.

This Specification is free software; you can redistribute it and/or modify it under the
terms of the GNU General Public License as published by the Free Software Foundation; 
either version 3 of the License, or (at your option) any later version.

This Specification is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program;
if not, see [http://www.gnu.org/licenses](http://www.gnu.org/licenses).


## Change Process

This document is governed by the [2/COSS](http://rfc.unprotocols.org/spec:2/COSS/) (COSS).


## Language

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT",
"RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in
RFC 2119.
