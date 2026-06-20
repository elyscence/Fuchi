# Fuchi

A bare-metal x86_64 kernel written in Rust. No standard library, no OS underneath.

The name comes from Japanese 淵 — a deep pool where you can't see the bottom.

## What it is

Fuchi boots on x86_64 hardware and QEMU, writes directly to VGA memory, and runs without any runtime or OS support. Built to understand what actually happens before `main()`.

Inspired by [Asahi Linux](https://asahilinux.org) and [Zinnia](https://github.com/zinnia-os/zinnia).

## Running

```bash
rustup override set nightly
rustup component add rust-src llvm-tools-preview
cargo install bootimage

cargo bootimage
qemu-system-x86_64 -drive format=raw,file=target/x86_64-fuchi-os/debug/bootimage-fuchi.bin
```

## Roadmap

- [x] Freestanding Rust binary
- [x] Custom x86_64 target spec
- [x] VGA text buffer output
- [ ] Hardware interrupts
- [ ] Memory paging
- [ ] Heap allocator
- [ ] UEFI bootloader
