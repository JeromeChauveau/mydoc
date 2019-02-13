[https-every-developer-must-know](https://app.pluralsight.com/library/courses/https-every-developer-must-know/table-of-contents), troy hunt

# Overview
 - In 2016, more than 50% of page loads were encrypted in HTTPS
 
## MiTM attack
 - insertion points : device (wireless router for instance), ISP, Internet backbone (states...)...

## Confidentiality, integrity, authenticity
 - Example of flaws : 2010 : Firesheep allowed to watch unprotected com' through public wireless connexions + facebook did not protecte auth' cookies ; 2011 : Tunisia gov added a keystroke logger to login page of Facebook
 - Authenticity : DNS hijacking, phishing, malicious host files, cross-site attacks example. 
 
## Barriers to setup https 
 - As perceived: Cost, Complexity to setup, speed (encryption/de-encryption), compatibility
 
# HTTPS Fundamentals
## Certificate authorities
CA is an entity that issues digital certificates. Huge number of CAs.
Local list of trusted CAs (windows) : certmgr.msc = local certificate manager --> trusted root certification authorities.
Note : Firefox manages its own list.
CA only issues certificate to the owner of the domain the certificate references.
 
## SSL and TLS
ssl (Secured Socket Layer) v3 released in 1996, and POODLE attack in 2014 was it's death knell. 
tls = Transport Layer Security, défined in 1999 as an upgrade of ssl v3. 1.2 in 2008 (1.3 still draft in 2017).

Protocol used in a com' is chosen by negociation between client and server.

HTTPS uses TLS.

## TLS Handshake
see graph.

## Issuing certs for development
When testing locally for dev, you do not need to have a certificate validated against a valid CA.

Windows : run powershell (à revoir quand besoin)

# Securing the application
## HTTP to HTTPS


        

