# whisper-rs-sys 0.15.0, patched for rust-hub

This repository holds whisper-rs-sys 0.15.0 exactly as published on crates.io
(the first commit, SHA-256 of the `.crate`
`6986c0fe081241d391f09b9a071fbcbb59720c3563628c3c829057cf69f2a56f`), plus the
fixes below, each its own commit. rust-hub pins it by revision through
`[patch.crates-io]` until a whisper-rs release bundles a whisper.cpp that has
them; then the patch and this repository go.

1. `whisper.cpp/src/whisper.cpp`, `median_filter`: narrow DTW's median filter
   instead of asserting on a window with fewer audio tokens than the filter is
   wide. Upstream as ggml-org/whisper.cpp pull request 4096, merge commit
   `a46fadb36a9bbaf40021c5135fb3ee34cca6a42b`, applied unchanged.
