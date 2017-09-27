# Datica Platform - Microsoft Teams to EHR Data #

A collection of Mirth Connect channels to facilitate creating Microsoft Teams cards from HL7 messages built for a demo from Datica for MS Ignite 2017. 

Mirth Connect is an open-source healthcare interface engine, designed to facilitate data transformation specific to the healthcare industry. It can manage protocols from HL7, which is the organization that manages the "comprehensive framework and related standards for the exchange, integration, sharing, and retrieval of electronic health information that supports clinical practice and the management, delivery and evaluation of health services." With a permissive license, a modern JavaScript engine to script transformations and strong community, it's the best product to use to get started with healthcare integration. While Mirth ultimately needs to be run in a HIPAA compliant environment like the [Datica Platform](https://datica.com/platform/), it's easy enough to experiment with Mirth by either deploying locally or installing it on a Linux VM. If you're interested in trying Mirth out, I've written a gist on how to deploy Mirth on linux here: https://gist.github.com/molsches/322bce27f21b65768f12

There are currently two channels in the Repo, which can be added to your Mirth Connect environment using the "Import Channels" functionality. The channels are written in Mirth 3.4.1, so you may need to manage dependenies to install the channels in an older version of Mirth. Here is a description of the channels. 

**Datica - ADT to Microsoft Teams**

Uses Mirth to parse some information out of an HL7 message and to push the data to Teams. The process of getting the HL7 message is a bit involved, and you can read more about it in this guide: https://datica.com/academy/how-to-integrate-with-epic-or-any-ehr/

To fully implement this, you need to setup:
- Deploy the **Datica - Microsoft Teams to Allscripts** channel and note that IP address and port. You may decide to put this in front of a DNS address for simplicities sake.
- A Incoming Webhook Channel for your connector
- In production, setup authentication to Teams for compliance purposes.

**Datica - Microsoft Teams to Allscripts**

Uses Mirth to parse the body of a Teams Card Task and sends the data into an EHR. Integrating with Allscripts requires signing up for their Authorized Development Partner network, which is easy to do from their developer portal: https://developer.allscripts.com/. 

To fully implement this, you need to:
- Setup variables and credentials from your own Allscripts app
- In production, build the process to validate the MSFT JWT token sent in the header of the request from teams

We hope this helps super charge your efforts to use Office 365 in healthcare. Submit an issue or email us at hello@datica.com if you have any questions. 
