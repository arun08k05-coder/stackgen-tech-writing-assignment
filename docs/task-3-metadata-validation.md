# StackSync AI Connector Metadata Validation

## Fixed Metadata Block

The metadata validator errors were caused by:

- Missing `clusters` field in the document metadata.
- Invalid `read_time` format. The value must follow the pattern: `\d+ min read`.

The corrected metadata block is:

```yaml
---
description: Explain how to set up and monitor StackSync AI Connector in StackBuilder.
title: StackSync AI Connector
read_time: 4 min read
customFields:
  ai_index: true
  clusters:
    - stackbuilder
audience:
  - developer
  - DevOps
product_version: '1.0'
---
````

## Metadata Field Usage

### ai_index

The `ai_index` field determines whether the document content is included in AI-powered indexing and retrieval features in StackGen documentation. When enabled, the document can be discovered and used by AI-based search and assistance capabilities. It improves the ability of users and AI tools to find relevant documentation content.

### clusters

The `clusters` field defines the product area or documentation group associated with the document. It helps organize content for indexing, categorization, and validation within StackGen documentation systems. This ensures that documentation is mapped to the correct feature or product category.

### read_time

The `read_time` field specifies the estimated amount of time required to read the document. It must follow the validated format, such as `4 min read`, to ensure consistency across documentation pages. This helps users estimate the time needed to review the content before opening the document.

```
```
