## Z80 Coding Style and Conventions

- Whitespace
  - Tabs, not spaces
  - Instructions indented 8 tabstops
  - Space between oprands e.g. ld a, b
- Naming conventions
  - Upper case assembler directives e.g. EQU, ORG, IF, ENDIF
  - Upper case constants e.g. MAGENTA EQU %011
  - Lower case operators (opcode mnemonics) and registers e.g. push hl
  - Function names UpperCamelCase and end with colon e.g. DrawScore:
    - Local helper functions can be lowerCamelCase to make it clear they are not part of the "public" API
  - Function names starting with NB are intended as public NextBASIC API entry points
  - Local labels start with .
  - Data labels (variable names) lowerCamelCase e.g. playerScore: DW 0
    - Addresses that contain addresses (i.e. pointers) should start with a 'p' e.g. pActivePlayer DW $0000
  - Struct names UpperCamelCase e.g. STRUCT InvaderBullet
- Numbers
  - Use $ for hex literals e.g. ld hl,$4000
  - Addresses generally referenced as hex
- Comments
  - Only use semi-colon
  - Full line/standalone comments start with `;;` at same indentation as opcodes
  - Capital register names in comments
  - No vertical space between comment above function and the function. Use single ; on last line if required (for VS Code intellisense)
  - Function comments should mark all input with =, output with <- and modified registers
```
    ;
    ; DE = address of addhend
    ; B <- sum
    ; Modifies: AF, BC, DE, HL
    ; Zero Flag <- reset if changed player, set if did not change player
    ;
    Sum:
    ...
```

## Thanks and attribution

- Coding style structure adapted from [@howprice's z80n invaders](https://github.com/howprice/specnext-invaders/)
