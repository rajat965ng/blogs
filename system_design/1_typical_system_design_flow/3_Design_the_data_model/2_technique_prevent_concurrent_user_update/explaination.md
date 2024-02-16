*User Alice Editing:* Alice clicks on the Edit button, triggering a PUT request to the backend with her credentials. The backend retrieves the unix_locked time from the database and attempts to lock the configuration. If successful, a success response is returned to the UI, allowing Alice to proceed with her edits. If the configuration is already locked, a failure response is returned, indicating to Alice that the configuration is being edited by another user.

*User Bob Editing Concurrently with Alice:* Bob attempts to edit the configuration while Alice is still editing. Similar to Alice's interaction, Bob's PUT request is sent to the backend, but since the configuration is already locked by Alice, the backend returns a failure response. The UI displays a notification to Bob indicating that the configuration is locked by Alice.

*Alice Saving Changes:* After making her edits within the time limit, Alice saves her changes by sending a PUT request to the backend with her edited values. The backend updates the row with Alice's edits and unlocks the configuration.

*Bob Editing After Alice Saves Changes:* Bob attempts to edit the configuration again after Alice saves her changes. This time, the backend successfully locks the configuration for Bob since it's no longer being edited by Alice. The UI enables the Edit button for Bob to proceed with his edits.

