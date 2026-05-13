# NOTICE — amalgame-random

## Authorship

Copyright 2026 Bastien Mouget. The Amalgame facade code in this
repository is original work — see `facade.am` and the
`amalgame.toml` manifest.

This package is part of the Amalgame ecosystem
([github.com/amalgame-lang/Amalgame](https://github.com/amalgame-lang/Amalgame)).
It was extracted from amc's bundled `src/stdlib/random.am`
during the framework split (post-v0.7.5).

## License

Licensed under the Apache License, Version 2.0 — see `LICENSE`.

## Third-party content

None. The facade is 100% pure-Amalgame. The PCG-32 algorithm is
public-domain (Melissa O'Neill, 2014); the crypto-grade entropy
helper shells out to OS primitives (`/dev/urandom` on POSIX,
`BCryptGenRandom` on Windows) without vendoring code.
