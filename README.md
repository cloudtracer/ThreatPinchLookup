# ThreatPinchLookup

## Introduction

ThreatPinch Lookup creates informational tooltips when hovering oven an item of interest on any website. It helps speed up security investigations by automatically providing relevant information upon hovering over any IPv4 address, MD5 hash, SHA2 hash, and CVE title. It’s designed to be completely customizable and work with any rest API.

![](https://cloud.githubusercontent.com/assets/6827829/19833788/3c4df320-9e1d-11e6-8c4e-1095e3cc1ac6.png)

_A sample of the type of data that can be displayed when hovering over an IPv4 address._

## Current IOC Support
- IPv4
- MD5
- SHA2
- CVE
- Add your own in the options with regex!

## Current Integrations
- ThreatMiner for IPv4, MD5 and SHA2 lookups.
- Alienvault OTX for IPv4, MD5 and SHA2 lookups.
- IBM X-Force Exchange for IPv4 lookups.
- VirusTotal for MD5 and SHA2 lookups.
- Cymon.io for IPv4 lookups.
- CIRCL (Computer Incident Response Center Luxembourg) for CVE Lookups.
- Add your own in the developers options page!

## Support

Check out the [Wiki](https://github.com/cloudtracer/ThreatPinchLookup/wiki) for documentation.

Please log an issue with any questions/comments. We'll respond as soon as possible. 

## Chrome Web Store

You can download the ThreatPinch Lookup extension directly from the [Chrome Web Store](https://chrome.google.com/webstore/detail/threatpinch-lookup/ljdgplocfnmnofbhpkjclbefmjoikgke)

## Release Notes
1.0.0.17 - 2016-12-10 - Improved preformance, added top level IOC pivots, threat indicators and tactics to saved requests for use in CouchDB/ELK aggregations
1.0.0.10 - 2016-11-02 - Initial Public Release  
