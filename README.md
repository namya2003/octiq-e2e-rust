# octiq-e2e-rust

End-to-end fixture for the indexed tier: a real build (`cargo build --all-targets`),
a real suite (`cargo test`, declared by CI), and no `octiq.verify.json`.

Planned sequence:
1. import (green, nothing runs)
2. green pull -> suite baseline `passed`
3. build-only break -> `build_failed` mail
4. fix the build -> verified -> publish
5. test-only break -> `tests_failed` mail
6. fix the tests -> verified -> publish
7. green pull -> clean, episode closed
