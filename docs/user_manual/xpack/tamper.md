!!! note ""
    The 1Panel Website Anti‑Tampering feature is designed to protect websites from unauthorized modification or tampering.

    💎 **Pro Edition Feature**: Website Anti‑Tampering is exclusive to 1Panel Pro Edition.

## 1 Feature Overview

!!! note "Feature Overview"
    - Supports exclusion and protection rules to adapt to various website directory structures.
    - Provides exclusion and protection templates for quick setup across different websites.
    - Allows viewing protection status by file structure.
    - Supports viewing and filtering block logs.

## 2 Usage

```bash
Example directory structure for rule demonstration:
     index
        index.html
        404.html
        test.ts
     log
        access.log
        err.log
```

!!! note "Rule 1"
    - Protected files: `.html`
    - Excluded directories: `log`
    - Behavior:
        - `*.html` files under the `index` directory are restricted from creation and deletion; deletion is blocked directly, and creation generates a block log.
        - `test.ts` under `index` can be freely created or deleted.
        - The `log` directory can be created freely under `index` because it is excluded.
        - The `tmp` directory cannot be created under `index` because it is not excluded; creation generates a block log.
        - The `log` directory and its files can be operated freely.

!!! note "Rule 2"
    - Protected files: `.html ./log/access.log`
    - Excluded directories: `log`
    - Behavior:
        - Compared to Rule 1, `access.log` is restricted from deletion and modification. Explicitly protected files have the highest priority.
        - All other behavior is the same as Rule 1.

## 3 Notes

!!! note "Additional Notes"
    - All files under excluded directories can be operated freely, except for explicitly protected files under those paths, which are still restricted from editing and deletion.
    - Non‑protected files and excluded directories can be created freely under protected directories; otherwise, a block log is generated.
    - Editing and deletion of protected files under protected directories are restricted. Creation and deletion of non‑excluded directories are also restricted.
