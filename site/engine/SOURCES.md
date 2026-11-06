# Stockfish browser Demo source materials

The unmodified browser engine binaries come from `stockfish@19.0.1` (locked in package-lock.json), Lite single-thread flavor, under GPL-3.0. Published Demo artifacts include the following source materials next to the engine download:

- `stockfish-19.0.1-source.tar.gz`: upstream tag `v19.0.1`, dereferenced commit `0d5dd7944f88c817c07a26bc4fb1905d5f9c46d6`. Source URL: https://codeload.github.com/nmrugg/stockfish.js/tar.gz/0d5dd7944f88c817c07a26bc4fb1905d5f9c46d6
- Source archive SHA-256: `e5289a920554bf0069a6601c228e81d957c00522bb31c4343588dc5d7d251879`.
- `nn-61e7af4bb97d.nnue`: Lite network named by that source's `src/evaluate.h`. URL: https://tests.stockfishchess.org/api/nn/nn-61e7af4bb97d.nnue
- Network SHA-256: `61e7af4bb97d51eeeb25d322916f86513b5cd3a827ce189c98c6e31946f99e5b`.
- `COPYING.txt`: GPL-3.0 license; `README.md`: upstream package documentation.

The archive contains the C++ source, Emscripten integration, build.js and scripts. Upstream documents Emscripten 6.0.9; after extracting the archive and putting the included network into `src/`, the Lite single-thread build entry is `node build.js --single-threaded --lite -f`. See the included upstream README and `node build.js --help` for platform toolchain and build options. This project copies published binaries, and does not claim to have independently reproduced their build bit for bit.

The Demo uses UCI messages through a separate Worker. It does not change the engine source or its license.
