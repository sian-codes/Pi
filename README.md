# Pi 🥧

Pi is a security-first, local-first personal and family data platform.

The project explores how individuals can maintain control over sensitive personal information while still allowing trusted devices and people to interact securely.

## Project Status

🚧 **Foundation / Experimental**

Pi is currently under active development and must not be used to store real sensitive data.

## Principles

- Security by design
- Local-first storage
- Privacy by default
- Least privilege
- Explicit trust
- Data minimisation
- Encrypted sensitive data
- Resilience and recovery

## Development

Pi currently uses:

- Android as the first client platform
- a Samsung Android device as the first physical Pi Slice
- Android emulation for development and testing

Further architecture is intentionally being designed before implementation.

## Documentation

Engineering documentation lives under [`docs/`](docs/).

The living project document is:

[`docs/pi-project.md`](docs/pi-project.md)

Architecture decisions are recorded under:

[`docs/adr/`](docs/adr/)

## Security

Pi is being developed under the assumption that devices, networks and individual components may eventually be compromised.

Security-sensitive architecture will be threat-modelled before Pi handles real personal data.

**Do not commit credentials, cryptographic keys, secrets or real personal data to this repository.**
