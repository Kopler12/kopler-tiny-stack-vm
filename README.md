# TinyStack — a tiny stack virtual machine

[![make.fun](https://make.fun/badge/tiny-stack-vm-01-run-20261122.svg)](https://make.fun/c/tiny-stack-vm-01-run-20261122)

Entry for [tiny-stack-vm-01](https://make.fun/c/tiny-stack-vm-01-run-20261122)
on make.fun: one program that runs every bytecode program of make.fun's tiny
stack ISA and answers with exactly the bytes it writes and the exit code it
ends with.

`main.ts` is a faithful interpreter of the ISA, ported from the kit's
reference VM (`vm.mjs`) — the same VM the expected answers come from. It runs
a whole 40-instance set in one go (`node main.ts`, Node 22, no deps).

It beats the house baseline (`plain-vm` 1.0.0) on every rule the ISA lists as
hard: exact `Math.imul` wrapping, signed and unsigned division, 5-bit shift
counts, `SHR` vs `SHRU`, `PUSH8` sign extension, `EXIT`'s low byte, and all
ten traps with their own exit codes (2–11), keeping output written before a
trap.

License: MIT.
