# ThreatPinch Lookup

## Introduction

ThreatPinch Lookup creates informational tooltips when hovering oven an item of interest on any website. It helps speed up security investigations by automatically providing relevant information upon hovering over any IPv4 address, MD5 hash, SHA2 hash, and CVE title. It’s designed to be completely customizable and work with any rest API.

![](https://cloud.githubusercontent.com/assets/6827829/19833788/3c4df320-9e1d-11e6-8c4e-1095e3cc1ac6.png)
_A sample of the type of data that can be displayed when hovering over an IPv4 address._

![](https://github.com/cloudtracer/ThreatPinchLookup/blob/master/talosblog2.gif)

_See it in action on Cisco Talos Blog._


## Current IOC Support
- IPv4
- MD5
- SHA1
- SHA2
- CVE
- FQDN (EFQDN is for Internet FQDN, IFQDN is for internal domains)
- Add your own in the options with regex!

## Current Integrations
- ThreatMiner for IPv4, FQDN, MD5, SHA1 and SHA2 lookups
- Alienvault OTX for IPv4, MD5, SHA1 and SHA2 lookups
- IBM XForce Exchange for IPv4, EFQDN lookups
- VirusTotal for MD5, SHA1, SHA2 and FQDN lookups
- Cymon.io for IPv4 lookups
- ThreatCrowd for IPv4, FQDN and MD5 lookups
- CIRCL (Computer Incident Response Center Luxembourg) for CVE lookups.
- PassiveTotal for FQDN Whois lookups
- MISP for MD5 and SHA2 (If you want more submit an issue in this github)
- Censys.io for IPv4 lookups
- Shodan for IPV4 lookups
- Add your own in the developers options page!

## Need a new integration?
- Log a github issue or reach out to [@ThreatPinch](https://twitter.com/ThreatPinch) on twitter.
- Try your luck at creating your own requests with the API Wizard. Check out the Youtube video to see [how its done.](https://www.youtube.com/watch?v=XM_eRM7pYos)

## Support

Check out the [Wiki](https://github.com/cloudtracer/ThreatPinchLookup/wiki) for documentation.

Please log an issue with any questions/comments. We'll respond as soon as possible. 

Follow [@ThreatPinch](https://twitter.com/ThreatPinch) on Twitter.

Youtube channel with [Demos](https://www.youtube.com/channel/UCuhYaI1qbb-exuhzscp3HBQ).

## Chrome Web Store

You can download the ThreatPinch Lookup extension directly from the [Chrome Web Store](https://chrome.google.com/webstore/detail/threatpinch-lookup/ljdgplocfnmnofbhpkjclbefmjoikgke)

## Where is my data stored?

There is no backend server or database for ThreatPinch Lookup. All data is stored in locally used PouchDB databases. It all exists in your browser. Previously Chrome remote storage was used for some configuration items, this proved too challenging due to limitations on the storage. Going forward the Pouch databases will allow for some more interesting functionality.

Optionally, in the developers options you can configure a CouchDB server to sync your API responses with. See the [Wiki](https://github.com/cloudtracer/ThreatPinchLookup/wiki) for more details.

## Release Notes
- 2.0.0: 2017-05-14 - Blocker button addition, enhanced wizard functionality, shareable custom integration links, removed span wrapping of obseravables, improved iframe support by moving popovers to active window instead of iframe, JSONPath support, style updates, minor bug fixes.
- 1.0.53: 2017-04-10 - Minor updates to popover styles.
- 1.0.51: 2017-04-09 - Added custom API integration wizard, be careful its still early stages and no validation!
- 1.0.50: 2017-04-05 - Fix for REST API responses which return with content type HTML. Added ThreatCrowd Lookups for IPV4, EFQDN and MD5. Added API group for ThreatCrowd for future API rate limiting, ThreatCrowd does not require an API key.
- 1.0.49: 2017-04-04 - Refectored some functionality to tighten extension permissions. Created [ThreatPinch Lite](https://chrome.google.com/webstore/detail/threatpinch-lite/jcjcflihdgdhapkadakfahkplbafobbi) build which is essentially the same plugin without the inject.js file to create the on hover tool tips.
- 1.0.46: 2017-04-03 - Another update to the migration code (sigh). Things will be smoother on Pouch in the future.
- 1.0.43: 2017-04-02 - Updates to configuration migration code to new PouchDB configuration store.
- 1.0.41: 2017-04-02 - Partial migration to React JS for options pages, added a graph relation explorer using pivot references in API requests (Still lots to do here). All configuration settings are now soley hosted in a locally stored PouchDB (using chrome storage became a big pain). Added Shodan API group settings. Implemented 24 hour request caching for successful lookups which means if you look up the same observable in less than 24 hours it won't cost you any extra API requests (next version this will be user configurable and trackable).
- 1.0.38: 2017-03-13 - Fix for bulk lookups interface which was broken by Chrome update 57.0.2987.98
- 1.0.37: 2017-02-22 - Added Shodan IPv4 Lookup and API group, enhancements to bulk lookup interface, added pivot API related items to Request Lookup & Lookup Type schemas.
- 1.0.35: 2017-02-14 - Updates to config pushing.
- 1.0.31: 2017-02-13 - Added options for case sensitive API requests.
- 1.0.30: 2017-02-13 - First attempt at API Groups for quick API key management. Bulk search page updates, SHA1 IOCs and lookups, edge case fixes for popover, Censys.io lookup for IPv4 addresses, added a number of observable detection regex for future use, added context menu highlight select and send to search page.
- 1.0.29: 2017-01-23 - Options interface make over, basic bulk lookup functionality, some fixes to improve observable detection and prevention in editable html elements.
- 1.0.28: 2017-01-04 - Performance improvements for pages with large quantities of observables.
- 1.0.26: 2017-01-02 - Break fix for local storage of lookup types.
- 1.0.25: 2017-01-01 - MISP integrations, disable buttons in options, moved lookup types to local storage (regex for EFQDN is too big to save in sync), enhancements to EFQDN lookups, lots of refactoring.
- 1.0.24: 2016-12-18 - Fix for delete buttons in options page.
- 1.0.23: 2016-12-14 - Fixes to CouchDB top level metadata, fix to IPv4 regex to filter out in-addr.arpa, fix to EFQDN to filter out URLs (URL IOC will come later..), added EFQDN lookups for IBM X-Force and VirusTotal
- 1.0.19: 2016-12-11 - Added FQDN support, regex updates, PassiveTotal support for FQDN/Whois, ThreatMiner FQDN, support for de-fanged IOCs
- 1.0.17: 2016-12-10 - Improved preformance, added top level IOC pivots, threat indicators and tactics to saved requests for use in CouchDB/ELK aggregations
- 1.0.10: 2016-11-02 - Initial Public Release  
