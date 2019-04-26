Mod Security Openshift Examples
==

This repository contains an example build template for the [mod-security container image](https://gitlab.corp.redhat.com/it-eai/httpd-container).


Templates:
-- 

 - [build_httpd.yaml](https://gitlab.corp.redhat.com/it-eai/mod-security-examples/blob/master/build_httpd.yaml) - Builds the httpd base image with mod_security and the default OWASP rules baked in
 - [deployment.yaml](https://gitlab.corp.redhat.com/it-eai/mod-security-examples/blob/master/deployment.yaml) - A sample deployment, configured to point to "http://helloworld:8080/" as the backend service. Example deployment notes are below.
  
Example Deployment Notes:
-- 

In order for deployment.yaml to be deployed, you will need the following secrets within your OpenShift project:

 - rhitcert - This should contain a "trust-chain.crt" file with your trusted CA chain in PEM format. This is required if you are using client certificate passthrough.
 - mod-security-waf-tls - This should contain the files "tls.crt" and "tls.key" with your certificate and private key.
 
 NOTE: The specific secret names and filenames are configurable within the deployment template. Further documentation is available within the [mod-security container image mod_security readme](https://gitlab.corp.redhat.com/it-eai/httpd-container/blob/mod_security/README_mod_security.md).
