---
name: 'release: urbit-os'
about: An issue describing a new urbit-os release
title: 'release: urbit-os-v2.XXX'
labels: ''
assignees: ''

---

# urbit-os-v2.XXX

Date: TODO
Kelvin: 4XX

## Candidates
TODO

## Pulls

* 

## Issues

* 

## Test Plan

### This Release

### Generic
- [ ] Check initial OTA
  - [ ] Boot a live moon without specifying a pill, so that the pill is downloaded automatically.  Immediately afterward, run `|ota %disable` to turn off OTA updates.
  - [ ] Run `|ota ~marnec-dozzod-marzod`, which should have the latest release candidate.
  - [ ] Check that the live moon receives the full OTA over Fine, not over Ames.  If the moon prints `%retry-with-ames-yawn`, then that means the Fine download failed and Ames was used instead.
- [ ] Check `+vats` by running all these commands and ensuring they don't crash:
  - [ ] `+vats %base %kids`
  - [ ] `+vats %base, =verb &`
  - [ ] `+vats %base, =verb |`
  - [ ] `+vats, =filt %suspended`
  - [ ] `+vats, =filt %running`
  - [ ] `+vats, =filt %blocking`
- [ ] Check that `|hi` and `-hi` work.
  - [ ] Run `|hi ~zod` and check that the response comes back quickly.
  - [ ] Run `-hi ~zod` and check that the response comes back quickly.
- [ ] Check that `-keen` works.
  - [ ] Run `-keen ~zod /c/x/143/kids/sys/kelvin`
- [ ] Check that `+agents %base` returns a reasonable-looking list of running agents, including `%hood` and `%dojo`.
- [ ] Check that `|install` works.
  - [ ] Run `|install ~paldev %pals`.
  - [ ] Load the `%pals` app in the browser.  Add someone as a pal.
  - [ ] Run `:pals +dbug` and check that the pal ship is in the state.
- [ ] Check that suspending and resuming agents works.
  - [ ] Run `|suspend %pals`.
  - [ ] Run `|revive %pals`.
  - [ ] Run `:pals +dbug` and check that the pal ship is still in the state.
