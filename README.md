# DSM (Synology)
Synology DSM for QRadar

This DSM config will support parsing and alerting for over 30 event types as of the current upload. I'm trying to determine all event types that will be sent over Syslog but it will take some time to map all of these so it's an ongoing process If you have any questions you can create an issue for the GitHub project or open a question/reply on the IBM QRadar CE forms located at: https://ibm.biz/qradarceforums

Note: This was built utilizing DSM 6.2.1 Update 4

# QRCE Changes
1. Create a new custom DSM called (SynologyDSM) using the DSM editor option under the admin settings window.
2. Once the custom DSM has been created close the window and click the Log Source Extensions option in the admin settings.
3. Click Add near the top right corner
4. Enter a name of "SynologyDSM_ext"
5. Select your newly created log source (SynologyDSM) that you created earlier.
6. Click the upload button and select the file "SynologyDSMCustom_ext.xml"
7. Click done and proceed to open the DSM menu and select your log source (SynologyDSM) that you created earlier.
8. You will need to select Event Mappings tab in the DSM editor and create the manual entries located in the file "Event Mappings.txt"
9. Finally, you will need to create a new log source selecting the custom Log source type we just created.

# Change Log
- 02-25-2019 - Mapped 'copied File' and 'copied Folder' event. Mapped custom property 'File Destination Path'.
- 02-24-2019 - Mapped 'System Shutting Down', 'successfully stopped [Rsync]', 'Shared folder was deleted', 'Storage Pool was degrade' and 'Clear [System]' events.
- 02-17-2019 - Mapped 'Software Uninstalled' event.
- 02-17-2019 - Regex adjusted for System events. Mapped 8 additional events.
- 02-16-2019 - Regex changed for connection events. This resolved the issue with the event 'User accessed shared folder'.
- 02-15-2019 - Regex modified to support parsing test events. Mapped 6 additional events.
- 02-15-2019 - Changed the regex for Connection events to allow for mapping failed logins correctly.
- 01-25-2019 - Changed the mapping of 2 Authentication events to a subcategory of "User Login Failure/Success". This was done to make it easier for creating authentication failure rules.
- 01-21-2019 - Mapped 2 additional events and fixed the regex for log source time for 2019.
- 12-22-2018 - Mapped 5 additional events and adjusted regex for the Event ID to support the additional VPN event.
- 12-20-2018 - Mapped 1 additional event.
- 12-17-2018 - Mapped 4 additional events and adjusted regex for the Event ID to support the newly discovered events.
- 12-17-2018 - Mapped 2 additional events.
- 12-14-2018 - New events mapped, regex adjusted for event ID parsing of newly discovered events. Hopefully the way the regex was adjusted will help to be more universal.
- 12-13-2018 - Mapped additional events, tweaked System regex for Event ID to parse VPN events.
- 12-13-2018 - Initial Upload of the source code.
