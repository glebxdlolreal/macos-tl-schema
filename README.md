# macos-tl-schema

TL schemas of **Telegram for macOS**, extracted from official beta builds.

- `main_api.tl` — main application API, read directly from the `TLS1` blob
  inside the `Telegram.app/Contents/MacOS/Telegram` binary, so it always
  matches the exact TL layer the app ships with.
- `e2e.tl` — end-to-end (secret chats) schema, assembled from the Swift
  `SecretApi<N>` modules compiled into the binary (current e2e layer =
  highest `<N>`); every constructor id is verified against the machine code.

## Format

- `---types---` / `---functions---` sections, TGScheme-compatible syntax
- footer: `// LAYER <n>`

Feedback: [@glebxdlolreal](https://t.me/glebxdlolreal)
