-> Edit Group Policy -> **_Computer Configuration -> Administrative Templates -> Windows Components -> Windows Updates ->_**

		->**_Configure Automatic Updates_** _->_ Enable the policy and select the following "Configure automatic updating" in the "Options" section:
- _Auto download and notify for install_

		->**_Specify intranet Microsoft update service_** _->_ Enable the policy and set both URL’s in the "Options" section:
 [_http://Your_WSUS_Server_Hostname:8530_](http://wsusserverip:8530/) 
    - Note: if [using SSL](https://kc.jetpatch.com/hc/en-us/articles/360043618872-Enabling-SSL-on-WSUS-) use **https** and **8531**

		-> - **_Automatic Update detection frequency_** _->_ Enable the policy and set "Check for updates at the following interval (hours)" in the "Options" section:
    - _4 hours_

		->- **_Allow signed updates from an intranet Microsoft update service location_** _->_ Enable the policy
    - **This is required** in order to install non-Microsoft [3rd Party Software Updates](https://kc.jetpatch.com/hc/en-us/articles/360054473392-3rd-Party-Software-Solution-Overview) and when [SSL](https://kc.jetpatch.com/hc/en-us/articles/360043618872-Enabling-SSL-on-WSUS-) has been configured on the WSUS server.


		->- Enable the execution policy by going to **_Computer Configuration -> Administrative Templates -> Windows Components -> Windows PowerShell_** _->_
    - _**Turn on Script Execution** -> Enable the policy and set "Allow local scripts and remote signed scripts" in the "Options" section_



_**Optional Policy**_

- Restrict users not to pause the updates in the endpoints enable this policy.
    - _**Computer Configuration -> Administrative Templates -> Windows Components -> Windows Updates ->**_ _**Remove Access to "Pause updates" feature** -> Enable the Policy._