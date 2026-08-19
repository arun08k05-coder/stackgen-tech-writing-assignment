---
description: Explain how to set up and monitor StackSync AI Connector in StackBuilder.
title: StackSync AI Connector
read_time: 4 min read
customFields:
  ai_index: true
audience:
  - developer
  - DevOps
product_version: '1.0'
---

# StackSync AI Connector Documentation

## Overview
StackSync AI Connector enables asynchronous synchronization of configuration changes from **appStack** to **Cloud2Code**. It provides a way to propagate application configuration updates while allowing users to monitor synchronization activity through **StackBuilder**.

The connector uses an asynchronous webhook trigger to initiate synchronization workflows. When configuration changes occur in appStack, the connector sends a sync request to Cloud2Code instead of performing an immediate synchronous update.

StackSync AI Connector is intended for developers and DevOps teams who manage application configurations, AI indexing metadata, and cluster-related settings across environments.

## Set Up and Usage
To use StackSync AI Connector:
1. Ensure the required configuration changes are available in appStack.
2. Configure the async webhook trigger used by StackSync AI Connector.
3. Verify that the required metadata configuration is available before starting a sync.
4. Open StackBuilder to monitor synchronization activity.
5. Select the sync action to start the process.

> [!NOTE]
> In the upcoming release, the synchronization action button label changes from **Sync Now** to **Run AI Sync**.

### Required Metadata

Before running a synchronization, verify that the `metadata.json` file contains the required fields:

- `ai_index`
- `clusters`

Missing required metadata fields can prevent successful synchronization.

### Try It Out

Use the following Cloud2Code import syntax to initiate a sync:

```bash
cloud2code import \
  --app <APP_NAME> \
  --config <CONFIG_PATH> \
  --environment <ENVIRONMENT_NAME> \
  --connector stacksync-ai
````

Replace the placeholders with your application-specific values:

* `<APP_NAME>`: Name of the application to synchronize.
* `<CONFIG_PATH>`: Path to the configuration source.
* `<ENVIRONMENT_NAME>`: Target environment for the sync operation.

## Troubleshooting

### Metadata Validation Errors

**Issue:** Synchronization fails because required metadata fields are missing.

**Cause:** The `metadata.json` file does not contain the required `ai_index` or `clusters` fields.

**Resolution:**

1. Open the `metadata.json` file.
2. Verify that both required fields are present.
3. Add missing values based on the application configuration.
4. Retry the synchronization.

Example:

```json
{
  "ai_index": true,
  "clusters": [
    "<CLUSTER_NAME>"
  ]
}
```

### Sync Failures

**Issue:** Configuration changes are not synchronized from appStack to Cloud2Code.

**Possible causes:**

* Async webhook trigger is not configured correctly.
* Required metadata fields are missing.
* Sync request was not initiated successfully.

**Resolution:**

1. Verify webhook configuration.
2. Validate the `metadata.json` file.
3. Retry the sync operation from StackBuilder.
4. Confirm the synchronization status in StackBuilder.

### Logging Information

The location and access method for StackSync AI Connector logs are currently unknown. Refer to the confirmed logging documentation when available.

## Assumptions

The following assumptions were made based on the available Slack discussion:

* StackSync AI Connector is responsible for syncing configuration changes from appStack to Cloud2Code.
* StackBuilder provides monitoring capabilities for sync operations.
* The async webhook trigger is configured outside the user workflow described in this document.
* `ai_index` and `clusters` are mandatory metadata fields required for synchronization.
* The exact Cloud2Code import syntax and command options are placeholders until confirmed.
* Log locations and troubleshooting details require additional validation.

## Questions for PM or Dev Team

1. Where can users access StackSync AI Connector logs?
2. What log details are available for failed sync operations?
3. What is the complete setup process for configuring the async webhook trigger between appStack and Cloud2Code?
4. What are the valid values and expected formats for the `ai_index` and `clusters` fields in `metadata.json`?

```
```
