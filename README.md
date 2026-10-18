# doc-sync

A reusable agent skill that synchronizes documentation with verified implementation across programming languages and frameworks.

通用文件同步技能：根據程式、介面、設定、測試與執行證據更新文件，並在寫入位置尚未指定時主動確認目的地。

## Install in Codex

Ask Codex to install this skill from:

https://github.com/GildShen/doc-sync

Alternatively, clone it into your personal skills directory. For the default Codex home:

```sh
git clone https://github.com/GildShen/doc-sync.git ~/.codex/skills/doc-sync
```

PowerShell:

```powershell
git clone https://github.com/GildShen/doc-sync.git "$env:USERPROFILE\.codex\skills\doc-sync"
```

If you use a custom `CODEX_HOME`, clone into its `skills/doc-sync` directory instead. If that destination already exists, inspect the existing installation before replacing it. Start a new Codex session if the skill is not yet visible.

Other agents that support `SKILL.md` can use the same instructions through their own skill installation mechanism.

## Use

```text
Use $doc-sync to update the documentation for the configuration changes.
```

```text
使用 $doc-sync 核對 API 文件與目前實作，先列出落差。
```

If you have not specified where to write, the skill asks a question such as:

> 文件要寫到哪裡？建議更新既有的 docs/api.md；也可以指定其他檔案或目錄。

The agent can investigate and prepare content while waiting, but must wait for your answer before writing documentation. If you already specified a path or established a project preference, it uses that destination without asking again. An audit-only request does not require a write destination.

**Installing a skill does not execute it.** Destination confirmation happens when the skill is used for documentation work, not during installation. The skill does not persist your preference by editing its own installation. Session-to-session persistence requires an available project preference mechanism and your request to save it.

## Behavior

- Verify claims against relevant implementation, tests, schemas, configuration, and operational evidence.
- Distinguish observed behavior, intended specifications, and unresolved mismatches.
- Update existing documents around features, contracts, and operations; avoid one document per source file.
- Follow the project's documentation language, layout, metadata, and ownership conventions.
- Keep implementation changes, extra records, commits, and publication within separately authorized scope.
- Report changed documents, verification, and remaining uncertainty.

This repository contains the reusable skill only. It does not require a particular application, programming language, documentation directory, or companion skill.
