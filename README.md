#GTP Vulnerabilities Skillets 

There are two skillets available:

GTP vulnerabilities initialization - _InitializeAndEnableGTPvulnerabilities_; and
 
GTP vulnerabilities floods threshold adjustment - _AdjustfloodThreshold_.

## InitializeAndEnableGTPvulnerabilities Skillet Description

The Skillet enables and initializes all GGSN Tunnel Protocol (GTP) flood attributes, while leaving the flood threshold values to their respective default values. This is advisable to do during the initial setup, unless a respective MNO provides the corresponding threshold values to deploy. In many instances, however, MNOs don’t have the attributes and rely on our expertise. It is, therefore, is a good idea to maintain the default threshold attributes for couple of weeks, while observing the corresponding GTP messages’ behavior on our platform, which is positioned within the MNO’s core network. Once established, Skillet named “AdjustfloodThreshold” may be used to adjust GTP flood attributes accordingly. 

This configuration is required for RAN/EPC and/or roaming security for MNOs or MVNOs. Specifically, it may be used while provisioning stateful GTP security for these interfaces → S11, S5, S8, Gn, Gp. 

By default, all GTP vulnerabilities attributes are disabled. GTP vulnerabilities are configured within the Security Profiles → Vulnerability Protection level of configuration. 

The GTP vulnerabilities include the following threats:

39084 - GTPv1-C Create PDP Context Request Message;

39085 - GTPv1-C Update PDP Context Request Message;

39086 - GTPv1-C Delete PDP Context Request Message;

39088 - GTPv1 Echo Request Message; 

39575 - GTPv2-C Create Session Request Message;

39608 - GTPv2-C Delete Session Request Message;

39609 - GTPv2-C Modify Bearer Request Message;

39610 - GTPv2-C Release Access Bearer Request Message;

39611 - GTPv2-C Echo Request Message;

40054 - GTPv1-C Create PDP Context Request Flood;

40055 - GTPv1-C Update PDP Context Request Flood;

40056 - GTPv1-C Delete PDP Context Request Flood;

40057 - GTPv1-C Echo Request Flood;

40063 - GTPv1-C Create Session Request Flood;

40064 - GTPv2-C Delete Session Request Flood;

40065 - GTPv2-C Modify Bearer Request Flood;

40066 - GTPv2-C Release Access Bearer Request Flood; and

40067 - GTPv2-C Echo Request Flood.

Upon the execution of the InitializeAndEnableGTPvulnerabilities Skillet, all aforementioned GTP vulnerabilities, including the flood ones with their respective threshold values, are enabled within the configuration of our firewall.

## AdjustfloodThreshold Skillet Description

This Skillet is a Stage 2 of the InitializeAndEnableGTPvulnerabilities one. 

Once you observe GTP behavior for a period of time within an MNO’s production network, you may need to adjust the default GTP flood threshold attributes. Alternatively, you may adjust those attributes, as per MNO’s provided values. 

This configuration is required for RAN/EPC and/or roaming security for MNOs or MVNOs. Specifically, it may be used while provisioning stateful GTP security for these interfaces → S11, S5, S8, Gn, Gp. 

It is assumed that you’ve executed EnableGTPFloodAttributes Skillet first, which results in enabling GTP flood threats. GTP flood attributes are configured within the Security Profiles → Vulnerability Protection level of configuration. 

The GTP flood attributes include the following threats:

40054 - GTPv1-C Create PDP Context Request Flood;

40055 - GTPv1-C Update PDP Context Request Flood;

40056 - GTPv1-C Delete PDP Context Request Flood;

40057 - GTPv1-C Echo Request Flood;

40063 - GTPv1-C Create Session Request Flood;

40064 - GTPv2-C Delete Session Request Flood;

40065 - GTPv2-C Modify Bearer Request Flood;

40066 - GTPv2-C Release Access Bearer Request Flood; and

40067 - GTPv2-C Echo Request Flood.

Upon the execution of the AdjustfloodThreshold Skillet, you will adjust one or more GTP flood attributes within the configuration of our firewall.

## How to Run a Skillet

You must perform the following steps to run a skillet:

1. Go to here - https://github.com/gpildush/GTPvulnerabilitiesSkillets/tree/c8b5ed5f3be181e45e300452dd5dd731fb778d13
2. Click on _Clone or download_ dropdown.
3. Clone with HTTPS the displayed URL and go to Panhandler.
4. From the top-left window of the Panhandler select _Import Skillets_.
5. Enter a Repository Name, related to the Skillet's name for ease of reference. In our case this could be _GTP Vulnerabilities_.
6. Within the Git Repository HTTPS URL space, paste the cloned URL. Branch should be _master_.
7. Click _Submit_.
8. From the top-left window of the Panhandler select _Skillet Collections_.
9. Find the collection name which you gave in step (5), which is a Repository Name. In our example, it is _GTP Vulnerabilities_.
10. Click _Go_ button.
11. Next, within the _Skillet Collection: GTP Vulnerabilities_ press _Go_ button again.
12. Within the _PAN-OS Configuration_ window you will see the configuration changes, as per skillet. Click _Submit_.
13. Enter the management IP address of the firewall, the firewall username and password (your credentials to log into the firewall). 
14. You may select _Perform Commit_ and/or _Perform Backup_. 
15. Click _Submit_. 
16. Wait until Panhandler acknowledges that the configuration was pushed successfully.

*Note* You require to run Docker before you run Panhandler. You will open Panhandler within Docker. 

## Support Policy

The code and templates in the repo are relegit ased under an as-is, best effort, support policy. These scripts should be seen as community supported and Palo Alto Networks will contribute our expertise as and when possible. We do not provide technical support or help in using or troubleshooting the components of the project through our normal support options such as Palo Alto Networks support teams, or ASC (Authorized Support Centers) partners and backline support options. The underlying product used (the VM-Series firewall) by the scripts or templates are still supported, but the support is only for the product functionality and not for help in deploying or using the template or script itself. Unless explicitly tagged, all projects or work posted in our GitHub repository (at https://github.com/PaloAltoNetworks) or sites other than our official Downloads page on https://support.paloaltonetworks.com are provided under the best effort policy.