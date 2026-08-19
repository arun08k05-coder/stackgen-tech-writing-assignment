## Overview

StackSync AI Connector helps users keep configuration information synchronized between **appStack** and **Cloud2Code**. It makes it easier to move approved configuration updates between these systems while allowing users to track the progress of synchronization through **StackBuilder**.

When changes are made in appStack, StackSync AI Connector sends the updates to Cloud2Code through an automated synchronization process. This process runs in the background, so users do not need to manually transfer configuration updates.

StackBuilder provides the interface to start and monitor synchronization activities. Users can use StackBuilder to confirm whether configuration changes were successfully processed.

## Set Up and Usage

Before using StackSync AI Connector, ensure that the required configuration information is available and ready for synchronization.

To run a synchronization:

1. Confirm that the required configuration changes have been made in appStack.
2. Ensure the synchronization setup is available for your environment.
3. Open **StackBuilder**.
4. Start the synchronization process using the available sync option.
5. Monitor the synchronization status in StackBuilder.

> [!NOTE]
> In the upcoming release, the sync button name changes from **Sync Now** to **Run AI Sync**.

### Configuration Requirements

Before starting a sync, make sure the configuration metadata file (`metadata.json`) includes the required information:

- `ai_index`
- `clusters`

These fields help StackSync AI Connector understand how the configuration should be processed. If either field is missing, the synchronization may not complete successfully.

If a synchronization fails:

1. Check that the required metadata information is available.
2. Confirm that the configuration changes are valid.
3. Retry the synchronization from StackBuilder.

```

