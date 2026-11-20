# third-party-mirror

Verified copies of third party build inputs that CGA products fetch at build
time. Each release here holds the exact bytes of one upstream release, so a
build keeps working when the upstream address goes away, as the ONNX Runtime
GitHub repository did on 2026-11-17.

Nothing here is modified. Every consuming build pins the SHA-256 of each file
and refuses anything else, so a copy served from here is checked the same way
as one served by the original publisher.

## Releases

| Tag | Upstream | Files | Licence |
|---|---|---|---|
| `onnxruntime-1.20.1` | microsoft/onnxruntime v1.20.1, GitHub release assets | `onnxruntime-linux-x64-1.20.1.tgz`, `onnxruntime-win-x64-1.20.1.zip` | MIT |
| `silero-vad-v6.2` | snakers4/silero-vad tag v6.2, `src/silero_vad/data/silero_vad.onnx` | `silero_vad.onnx` | MIT |

SHA-256 of every file is in the release notes and in `SHA256SUMS` beside it.

## Adding a file

1. Obtain the upstream file and record its SHA-256 from at least two
   independent downloads or caches.
2. Create a release tagged `<project>-<version>`, upload the file unchanged,
   and put the hashes in the release notes.
3. Point the consuming build at
   `https://github.com/cga-management/third-party-mirror/releases/download/<tag>/<file>`
   with the upstream address kept as a fallback.
