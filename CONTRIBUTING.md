# Contributing

Thanks for helping improve the STM32F411 IMU Development Board.

## Hardware changes

Before submitting a change:

1. Open the Altium project from `hardware/altium/`.
2. Review the schematic and PCB together.
3. Run ERC/DRC and resolve or document relevant warnings.
4. Update the BOM if component selections change.
5. Regenerate manufacturing outputs when the PCB changes.
6. Include clear revision notes in the pull request.

## Commit messages

Prefer concise, descriptive commits such as:

- `feat: add SWD protection`
- `fix: correct IMU decoupling footprint`
- `docs: update assembly notes`

## Pull requests

Include:

- What changed
- Why it changed
- Validation performed
- Any manufacturing implications
