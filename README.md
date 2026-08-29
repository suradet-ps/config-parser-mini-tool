# Config Parser Mini Tool

```
 ██████╗ ██████╗ ███╗   ██╗███████╗██╗ ██████╗
██╔════╝██╔═══██╗████╗  ██║██╔════╝██║██╔════╝
██║     ██║   ██║██╔██╗ ██║█████╗  ██║██║  ███╗
██║     ██║   ██║██║╚██╗██║██╔══╝  ██║██║   ██║
╚██████╗╚██████╔╝██║ ╚████║██║     ██║╚██████╔╝
 ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝╚═╝╚═╝ ╚═════╝
```

---

## ◆ PULSE

Rust's rules are best learned in a problem small enough to see all of
them at once. This is that problem: a configuration parser that
simulates reading `host=127.0.0.1` style key-value lines - and in
doing so walks the language's core ideas one by one: `const` for the
defaults, immutability by default, `mut` for the counters, variable
shadowing to turn a string port into a number, and error handling
where the parsing can fail. An educational tool with a real shape.

| Const ▣ | Shadowing ▣ | Parsing ▣ | Errors ▣ |
|---|---|---|---|

*The lesson - read, parse, transform, fail gracefully - is sealed.*

> Built with Rust (edition 2024) - one file, one scenario, six
> language concepts demonstrated in the open.
>
> **suradet-ps**, artifact keeper

---

## ◆ IGNITION

One toolchain, two commands.

```
⟫ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
⟫ git clone https://github.com/suradet-ps/config-parser-mini-tool.git
⟫ cd config-parser-mini-tool
⟫ cargo build
⟫ cargo run
```

The output walks the parse: the initial defaults, the values found in
the input, and the final configuration.

---

## ◆ ANATOMY

One `main.rs`, six concepts, no distractions.

- **Defaults** - `const DEFAULT_PORT` and friends hold the
  system-wide values - the immutable baseline every parse starts
  from.
- **Stands** - immutability by default: variables that do not change
  are written without `mut`, and the compiler says so if someone
  forgets.
- **Counts** - `mut` appears only where state genuinely evolves -
  counters and values that move through the parse.
- **Shadows** - variable shadowing transforms a string port into a
  `u16` in the same scope - the old name reborn with a new type, a
  concept shown rather than lectured.
- **Parses** - key-value pairs are extracted from raw text with
  Rust's string methods - `lines()`, splitting, trimming - the daily
  vocabulary of text handling.
- **Fails** - parsing errors are handled, not ignored: the tool
  shows how a type conversion can go wrong and what the program
  does about it.

---

## ◆ RITUALS

**The core ceremony** - the first run:

1. Build with `cargo build`; the compiler is the first reviewer.
2. Run with `cargo run`; the parse walks the input line by line.
3. Read the output: defaults, found values, and the final
   configuration - the transformation visible from end to end.
4. Study the source: every concept in the lesson has a line it can
   be pointed at.

**The ceremony of the small shape** - the tool stays one file and
one scenario on purpose: a larger problem would bury the concepts it
exists to teach. The size is the syllabus.

**The ceremony of the honest failure** - parsing can fail, and the
code says so. Learning that errors are handled, not papered over, is
part of the lesson - the tool refuses to pretend a bad port is a
good one.

---

## ◆ ECHOES

**Where this artifact is heading**

```
const  ▸ immutable system defaults ──────────────────────────────────── ▸ sealed
shadow ▸ string-to-number type transformation ───────────────────────── ▸ sealed
parse  ▸ key-value extraction from raw text ─────────────────────────── ▸ sealed
errors ▸ handled conversion failures ────────────────────────────────── ▸ sealed
```

**Raising the artifact** - the whole lesson lives in `src/main.rs`.
A contribution extends the scenario - TOML or JSON support would
teach more - via the fork-and-PR path. Open an issue first to discuss
a change.

**Status** - the tool is complete as an educational example and open
to extension.

---

```
  ─────────────────────────────────────────
   A language is learned one concept
   at a time, in code that runs.
  ─────────────────────────────────────────
```

Open source under the [MIT License](LICENSE).