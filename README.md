<p align="center">
  <img src="public/logo.webp" alt="Cerberus" width="200" />
</p>

<h1 align="center">Cerberus</h1>
<p align="center"><strong>Local-First Password Manager</strong></p>
<p align="center">
  A secure, open-source password manager available as a desktop app and a web app.<br/>
  Your credentials stay on your device. No cloud required. No trust needed.
</p>

---

## Why Cerberus?

Most password managers store your credentials on their servers. Even with end-to-end encryption, you're trusting a third party with your most sensitive data. Cerberus flips this model — available as both a native desktop app and a web app, with the same local-first approach either way:

- **Local-first**: Whether you use the desktop app or the web app, your vault lives on your device. Nothing leaves unless you explicitly want it to.
- **Zero-knowledge**: The master password never touches a server. Verification happens locally.
- **Open source**: Every line of code is auditable. No proprietary lock-in.

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Rust |
| Encryption | AES-256-GCM |
| Key Derivation | PBKDF2 (high iteration count) |
| Local Storage | SQLite3 |

## Features

- **Encrypted Vault** — All credentials are stored in a locally encrypted database using AES-256-GCM. Without the master password, the data is unreadable.
- **Active Memory Defense** — Sensitive strings are zeroed out in RAM immediately after use. No plaintext lingers.
- **Auto-Lock** — After 5 minutes of inactivity, the vault purges decrypted data from memory and locks itself.
- **Secure Clipboard** — Copied passwords are automatically cleared from the clipboard after 30 seconds.
- **Password Generator** — Built-in entropy generator for creating strong, random passwords.

## Getting Started

### Prerequisites

- Rust toolchain (stable)
- SQLite3

### Build & Run

```bash
git clone https://github.com/yourusername/cerberus.git
cd cerberus
cargo build --release
./target/release/cerberus
```

## How It Works

1. **Set a Master Password** — On first launch, you pick a master password. There's no "forgot password" option — that's by design.
2. **Add Credentials** — Store services, usernames, and passwords through the dashboard.
3. **Generate Passwords** — Use the built-in generator for high-entropy, 20+ character passwords.
4. **Stay Locked** — The vault auto-locks after 5 minutes of idle time, clearing all decrypted data from memory.

## Contributing

This is a personal project, but feedback on the cryptographic implementation or memory safety is always welcome. If you spot a vulnerability, please open an issue.

## License

This project is licensed under the **BSD 3-Clause License**. See the [LICENSE](LICENSE) file for details.
