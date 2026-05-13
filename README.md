# amalgame-random

Pure-Amalgame random facade for [Amalgame](https://github.com/amalgame-lang/Amalgame).
**PCG-32** deterministic stream + crypto-grade entropy.

Originally bundled in amc's `src/stdlib/random.am`; extracted into
this external package as part of the framework split (post-v0.7.5).

## Install

```bash
amc package add random                  # via the curated index
amc package add github.com/amalgame-lang/amalgame-random@v0.1.0
```

Requires **amc 0.7.6+** for the facade pre-compile pipeline
(PR #377).

## Surface

```amalgame
import Amalgame.Random

class Program {
    public static void Main() {
        // ── Seeded PCG-32 stream ─────────────────────
        let rng = new Random(42)
        Console.WriteLine(String_FromInt(rng.NextInt()))
        Console.WriteLine(String_FromInt(rng.IntRange(0, 100)))
        Console.WriteLine(if (rng.Bool()) { "true" } else { "false" })

        // ── Crypto-grade entropy ─────────────────────
        let bytes: List<int> = Random.SystemBytes(16)
        let rng2 = Random.FromSystem()
    }
}
```

See `facade.am` for the full API — `new Random(seed)`,
`Random.FromSystem`, `Random.SystemBytes`, `.NextUInt32` /
`.NextInt` / `.IntRange` / `.Float` / `.Bool` / `.Bytes`.

## Tests

```bash
./tests/run_tests.sh /path/to/amc
```

## License

Apache-2.0 — see `LICENSE`. No vendored third-party code.
