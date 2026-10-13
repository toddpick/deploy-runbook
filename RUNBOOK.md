# Runbook: defusing a stuck release

You can't see the deploy panel. The Panel team can. Ask them what you need, one thing at a time, and tell them exactly what to do. Clear the modules in order. Read each rule in full before acting: the panel gives one try per module.

## Module 1: Feature-flag wires

Find out how many wires there are, then:

- **3 wires:** if none is red, cut the second wire. Otherwise cut the last wire.
- **4 wires:** if more than one wire is red **and** the last digit of the panel's serial number is odd, cut the **last red** wire. Otherwise, if the last wire is white, cut the first wire. Otherwise cut the second wire.
- **5 or more wires:** cut the third wire.

## Module 2: Status button

Find out the status light and the button label, then:

- **Solid green light:** press and release right away.
- **Blinking amber light and the label says HOLD:** press and hold. Ask what color the strip lights up, then release when the countdown timer shows:
  - white: a **1** in any position
  - blue: a **4** in any position
  - yellow: a **5** in any position
  - any other color: a **1** in any position
- **Anything else:** press and release right away.

## Module 3: Release code

Enter 3 characters on the keypad:

1. The first letter of the panel's region, in capitals.
2. The number of red wires module 1 had (before any were cut).
3. The release-candidate number (the number after "rc" in the release tag) plus the number of rollback attempts so far.

When all three modules are cleared, the deploy is defused.
