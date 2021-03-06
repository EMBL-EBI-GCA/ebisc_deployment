TLS certificates
================

The bastion VM uses [Let's Encrypt](https://letsencrypt.org/) to generate TLS certificates.  The 
certificates expire after 90 days, so the bastion automatically regenerates 
them when they are close to expiry.

A single certificate is generated to cover all of the following subdomains:

* cells.ebisc.org
* cells-stage.ebisc.org
* www.cells.ebisc.org
* cell.ebisc.org
* www.cell.ebisc.org
* catalog.ebisc.org
* www.catalog.ebisc.org
* catalogue.ebisc.org
* www.catalogue.ebisc.org

A job runs on the bastion VM at 11pm every Monday to regenerate certificates if required.  If the bastion fails to automatically regenerate our certificates then Letencrypt kindly emails us to warn us.  If certificates are regenerated OK then we will never hear from Letsencrypt. The emails get sent to vdc-internal@ebi.ac.uk.

You can check on the status of a certificate at this website: https://www.sslshopper.com/ssl-checker.html  Type in the domain name into the box, e.g. cells.ebisc.org
