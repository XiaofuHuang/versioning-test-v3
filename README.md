# Versioning Test for docfx v3

## Moniker Tree

* versioning-test-v3 (Family)
  * test-client (Product)
    * test-client-1.0
    * test-client-1.1
    * test-client-2.0
    * test-client-3.0
  * test-server (Product)
    * test-server-1.0
    * test-server-2.0

## Folder structure

-- legacy/: < test-client-2.0
-- active/: >= test-client-2.0 || >= test-server-1.0

## Content

* index.md - Available for all monikers in folder.
* overivew.md - Available for all monikers in folder; configured with moniker zones and shared content.
* fallback.md - Available for some monikers, all other version should fallback to the latest version.
* quickstarts - Folder should have at least one item available for all monikers.
  * quick-start-1.md - Available only for some monikers; configured through file-level metadata.
  * quick-start-2.md - Available only for some monikers; configured through file-level metadata.
* resources - Available for all monikers in folder; reference to resource with same assetId but different version.

```
├───active
│   │   fallback.md (test-client-2.0, test-server-1.0)
│   │   index.md (test-client-2.0, test-client-3.0, test-server-1.0, test-server-2.0)
│   │   overview.md (test-client-2.0, test-client-3.0, test-server-2.0)
│   │   toc.yml
│   │
│   ├───quickstarts
│   │       quick-start-1.md (test-client-2.0, test-server-1.0)
│   │       quick-start-2.md (test-client-3.0, test-server-2.0)
│   │
│   └───resources
│       │   resource.md (test-client-2.0, test-client-3.0, test-server-1.0, test-server-2.0)
│       │
│       └───media
│               a.png
│
└───legacy
    │   fallback.md (test-client-1.0)
    │   index.md (test-client-1.0, test-client-1.1)
    │   overview.md (test-client-1.0, test-client-1.1)
    │   toc.yml
    │
    ├───quickstarts
    │       quick-start-1.md (test-client-1.0)
    │       quick-start-2.md (test-client-1.1)
    │
    └───resources
        │   resource.md (test-client-1.0, test-client-1.1)
        │
        └───media
                a.png
```