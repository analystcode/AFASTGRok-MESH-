# Security & Privacy — Zero-Trust by Design

No node can ever view another user’s video. Period.

### Core Principles
| Principle               | Implementation                                      |
|-------------------------|-----------------------------------------------------|
| End-to-End Encryption   | XChaCha20-Poly1305 with per-user per-chunk keys     |
| Zero-Knowledge Storage  | Keys derived client-side via HKDF (prompt + user ID)|
| Immutability            | Content-addressed CIDs (IPFS-style)                 |
| Forward Secrecy         | Chunks become permanently inaccessible after 90 days|
| Proofs                  | Verifiable Delay Functions (VDF) for storage proofs |

### Threat Model & Mitigations

| Threat                  | Mitigation                                      | Confidence |
|-------------------------|-------------------------------------------------|----------------|
| Malicious node          | E2EE + VDF proofs                               | 99.99 %       |
| Sybil attack            | Hardware-bound attestation + stake slashing     | 99.9 %        |
| ISP snooping            | Encrypted chunks only — ISP sees hashes only    | 100 %         |
| Key compromise          | Ephemeral keys + perfect forward secrecy        | Full PFS      |

All code will be audited by **Trail of Bits** and **OtterSec** before mainnet.

[Full security deep-dive (PDF pages 22–23)](FASTGRok_MESH_Whitepaper_v1.1.pdf){ .md-button }
