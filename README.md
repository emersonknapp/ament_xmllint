# `ament_xmllint` fork & split for `pre-commit`

## Contents

This repository contains only:

- <https://github.com/ament/ament_lint/tree/rolling/ament_xmllint> directory pulled to the top level
- [.pre-commit-hooks.yaml](.pre-commit-hooks.yaml) - to expose this linter as a [pre-commit](https://pre-commit.com) hook

## Modifications to base package

None, currently.

## Usage

Add to your `.pre-commit-config.yaml`

```yaml
- repo: https://github.com/emersonknapp/ament_xmllint
  rev: v0.1
  hooks:
    - id: ament_xmllint
```

## Justification

This is a useful standalone linter because it allows for automatic detection and validation against XSD schemata via the `<?xml-model?>` prolog element.

The base [`check-xml`](https://github.com/pre-commit/pre-commit-hooks/blob/main/pre_commit_hooks/check_xml.py) hook does not perform any schema validation, only verifying that files are syntactically correct XML.
