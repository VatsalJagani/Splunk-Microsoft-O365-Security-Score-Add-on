# Microsoft Graph Security Score Add-on for Splunk

### Download from Splunkbase
TODO


OVERVIEW
--------
The Microsoft Graph Security Score Add-on for Splunk is a Splunk App that allows users to collect Azure Security Score from Microsoft Security Graph API. It consists of python scripts to collect the data alongside configuration pages in UI to configure the account information.


* Author - CrossRealms International Inc.
* Version - 1.0.0
* Build - 2
* Creates Index - False
* Compatible with:
   * Splunk Enterprise version: 8.2, 8.1, 8.0
   * OS: Platform Independent
   * Browser: Google Chrome, Mozilla Firefox, Safari



TOPOLOGY AND SETTING UP SPLUNK ENVIRONMENT
------------------------------------------
This app can be set up in two ways: 
  1. Standalone Mode: 
     * Install the `Microsoft Graph Security Score Add-on for Splunk`.
  2. Distributed Mode:
     * The Add-on can be installed on search head but it is not required. The Add-on contains a dashboard to show Microsoft Graph Security Score.
        * The Add-on configuration is not required on search head.
     * Install the `Microsoft Graph Security Score Add-on for Splunk` on the heavy forwarder.
        * Configure the Add-on to collect the required information from the Microsoft Graph API on the heavy forwarder.
        * The Add-on do not support universal forwarder as it requires python modular inputs to collect the data from Microsoft Graph API.
     * The Add-on do not require on the Indexer.


DEPENDENCIES
------------------------------------------------------------
* The Add-on does not have any external dependencies.


INSTALLATION
------------------------------------------------------------
The Add-on needs to be installed on the Search Head and heavy forwarder.

* From the Splunk Web home screen, click the gear icon next to Apps. 
* Click on `Browse more apps`.
* Search for `Microsoft Graph Security Score Add-on for Splunk` and click Install. 
* Restart Splunk if you are prompted.


DATA COLLECTION & CONFIGURATION
------------------------------------------------------------
### Configuration Required on Azure###
* Configure Tenant(Directory) ID, Application(Client) ID, Client Secret in Azure.
* Make Sure this Application has "Microsoft Graph" Permission.
* Reference - https://www.inkoop.io/blog/how-to-get-azure-api-credentials/


### Configure Data Input ###
* Navigate to ``Microsoft Graph Security Score Add-on for Splunk`` > `Input` on Splunk UI.
* Click on `Create New Input`.
* Add below parameters:

| Parameter | Description |
| --- | --- |
| Name | An unique name for the Input. |
| Interval | Interval in seconds, at which the Add-on should collect the latest data from Graph API. Ideal value is between 3600 (1 hour) to 14400 (4 hour). |
| Index | Select/Type the index name in which Graph API data will be stored in Splunk.  |
| Azure AD Tenant ID | Tenant(Directory) ID received from Azure  |
| Application Id | Application(Client) ID received from Azure  |
| Client Secret | Client secret received from Azure |


* Click on `Save`.



UNINSTALL APP
-------------
To uninstall app, user can follow below steps:
* SSH to the Splunk instance.
* Go to folder apps($SPLUNK_HOME/etc/apps).
* Remove the `TA-microsoft-graph-security-score` folder from `apps` directory.
* Restart Splunk.


RELEASE NOTES
-------------
Version 1.0.0 (Aug 2021)
* Created Add-on by UCC Splunk-Python library.
* Added Add-on configuration pages.



OPEN SOURCE COMPONENTS AND LICENSES
------------------------------
* The Add-on is built by UCC framework (https://pypi.org/project/splunk-add-on-ucc-framework/).


CONTRIBUTORS
------------
* Bhavik Bhalodia
* Vatsal Jagani
* Usama Houlila
* Preston Carter



SUPPORT
-------
* Contact - CrossRealms International Inc.
  * US: +1-312-2784445
* License Agreement - https://d38o4gzaohghws.cloudfront.net/static/misc/eula.html
* Copyright - Copyright CrossRealms Internationals, 2021
