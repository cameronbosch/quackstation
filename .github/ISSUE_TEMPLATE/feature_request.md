---
name: Feature request
about: Request a feature to be added or improved in QuackStation
title: "[FEATURE]"
labels: ''
assignees: ''

---

name: Feature request
description: Request a feature to be added or improved in QuackStation
body:

- type: markdown
  attributes:
    value: |
      **Please read before creating a new feature request:**
      1. Make sure there is not already an issue for this feature request by [searching in **both** open and closed issues](https://github.com/cameronbosch/quackstation/issues?q=is%3Aissue+sort%3Aupdated-desc+).
      2. Please open **one issue per requested feature**. Do not cram several unrelated feature requests in a single issue, as this makes it harder for contributors to track what's being worked on.
      3. Please post your bug report in English, as this is the only language spoken by the developers. The Matrix room has many helpful people if you need help translating.
      4. Issues about the libretro core will be marked as "completed" and "won't fix". We do not control that fork and it has nothing to do with us.

- type: textarea
  attributes:
    label: Problem statement
    description: |
      Is your feature request related to a problem? Please describe.
    placeholder: Example - "I'm always frustrated when […]"
  validations:
    required: true

- type: textarea
  attributes:
    label: Proposed solution
    description: |
      A clear and concise description of what you want to happen.
  validations:
    required: true

- type: textarea
  attributes:
    label: Alternatives considered
    description: |
      Describe alternatives you've considered.
  validations:
    required: true

- type: textarea
  attributes:
    label: Additional context
    description: |
      Add any other context about the problem or proposed feature here.
