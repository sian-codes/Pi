# Pi — Project Documentation

> A security-first, local-first personal and family data hub.

**Status:** Foundation  
**Started:** 26 September 2026

---

## 1. Project Vision

Pi is a private data platform designed to give an individual control over their own sensitive information.

Each user has their own **Pi Slice**, with data stored and processed through infrastructure designed around privacy, security and explicit consent.

Pi should eventually support areas such as:

- secure document storage
- financial information and planning
- private messaging
- reminders and records
- encrypted backups
- controlled sharing between trusted family members

Pi must never rely on obscurity for security.

---

## 2. Core Principles

### Security First

Security is an architectural requirement, not a feature added later.

### Local First

Sensitive information should remain under the user's control wherever practical.

### Least Privilege

Components receive only the access required to perform their role.

### Data Minimisation

Do not collect, transmit or retain information without a defined reason.

### Encryption

Sensitive information must not be stored in plaintext.

### Assume Compromise

Architecture should consider what happens if a device, service, account or network is compromised.

### Explicit Trust

Devices and users must not automatically become trusted simply because they are connected to the same network.

### Recovery

Loss of a device must not mean loss of the user's data, but recovery mechanisms must not undermine security.

---

## 3. Pi Vocabulary

### Pi

The overall ecosystem.

### Pi Node

A device providing Pi services and access to encrypted storage.

### Pi Slice

An individual's private part of the Pi ecosystem.

### Pi Client

An application used to interact with Pi.

### Pi-Slice-01

The first physical Pi development device.

Current hardware:

- Samsung Galaxy Z Flip
- factory-reset specifically for Pi development
- no personal data restored
- no Google account
- no Samsung account
- protected by device PIN
- USB debugging enabled for development
- authorised development Mac via ADB

---

## 4. Development Environment

```text
Development Mac
       |
       +---- Samsung Emulator
       |       disposable development environment
       |
       +---- Pi-Slice-01
               physical Android test device
```

## 5. Architecture

Architecture is currently being designed.

### System Context

TBD

### Components

TBD

### Trust Boundaries

TBD

### Data Flow

TBD

---

## 6. Security

Security documentation will be developed before Pi handles real sensitive data.

### Assets

TBD

### Threat Model

TBD

### Authentication

TBD

### Authorisation

TBD

### Encryption

TBD

### Key Management

TBD

### Network Security

TBD

### Backup and Recovery

TBD

### Compromised Device Behaviour

TBD

### Incident / Failsafe Behaviour

TBD

---

## 7. Engineering Governance

`main` represents the latest trusted version of Pi.

Direct development on `main` is prohibited now that the project foundation has been established.

Changes must:

1. Be developed on a separate branch.
2. Have defined acceptance criteria.
3. Be submitted through a Pull Request.
4. Pass required automated checks.
5. Include appropriate tests.
6. Consider security impact.
7. Update documentation where necessary.
8. Receive a complete self-review before merge.

### Security-Sensitive Changes

Changes involving:

- authentication
- authorisation
- encryption
- cryptographic keys
- sensitive storage
- backups
- network security
- recovery mechanisms

require additional review.

Security-sensitive changes should not be implemented and merged during the same development/review session.

### Repository Protection

The `main` branch is protected by a GitHub branch ruleset.

Current protections:

- changes to `main` require a Pull Request
- direct development on `main` is prohibited
- force pushes to `main` are blocked
- deletion of `main` is restricted
- linear Git history is required
- Pull Requests are squash merged

### Continuous Integration

Pull Requests targeting `main` trigger the `Pi Security` GitHub Actions workflow.

The workflow currently contains two independent jobs.

#### Repository Security

Checks that:

- private key and certificate file types have not been committed
- database files have not been committed
- reserved sensitive-data directories have not been committed
- required project documentation remains present

#### Secret Scanning

Gitleaks scans the repository and Git history for accidentally committed credentials, tokens and other potential secrets.

CI uses read-only repository permissions unless additional permissions are explicitly required.

Android build, lint and test checks will be introduced when the Android application project exists.

Passing CI does not by itself mean a change is safe.

Automated checks support — but do not replace — security review and developer understanding.

---

## 8. Architecture Decisions

Important architectural decisions will be recorded as Architecture Decision Records (ADRs) under:

`docs/adr/`

An ADR should explain:

- context
- decision
- reasoning
- security impact
- alternatives considered

---

## 9. Development Log

### 2026-09-26 — Project Foundation

- Pi project started.
- Samsung Flip factory reset.
- Device configured without restoring personal data.
- Optional telemetry minimised during setup.
- Pi-Slice-01 protected with a dedicated device PIN.
- Developer Options enabled.
- USB debugging enabled.
- Development Mac authorised for ADB.
- Samsung Android emulator configured.
- Local Git repository created.
- Default branch established as `main`.
- Initial project structure created.
- Git exclusions established before first commit.
- Private GitHub repository created.
- Personal GitHub SSH identity separated from work GitHub identity.

### 2026-09-26 — PI-002 Repository Security Foundation

- Protected the `main` branch.
- Required Pull Requests before changes can enter `main`.
- Blocked force pushes and restricted branch deletion.
- Required linear history and squash merging.
- Created the `Pi Security` GitHub Actions workflow.
- Added repository checks for prohibited sensitive files and directories.
- Added required-documentation validation.
- Added Gitleaks secret scanning.
- Restricted CI repository access to read-only permissions.
- Deferred Android build/test CI until the Android project exists.

---

## 10. Roadmap

### Foundation

- [x] Prepare Pi-Slice-01
- [x] Configure physical Android development access
- [x] Configure Samsung emulator
- [x] Create local repository
- [x] Establish initial project structure
- [x] Establish Git exclusions
- [x] Create project README
- [x] Establish private remote repository
- [x] Establish Pull Request template
- [x] Configure branch protection
- [x] Configure CI
- [x] Configure security checks
- [ ] Create initial threat model
- [ ] Create system architecture diagrams

### Android Foundation

- [ ] Create Android project
- [ ] Establish application architecture
- [ ] Add Android build CI
- [ ] Add lint CI
- [ ] Add unit-test CI
- [ ] Add instrumented-test strategy
- [ ] Design Pi shell
- [ ] Prototype Pi shell on emulator
- [ ] Validate Pi shell on Pi-Slice-01
- [ ] Investigate cover-screen behaviour

### Security Foundation

- [ ] Define protected assets
- [ ] Define threat actors
- [ ] Define trust boundaries
- [ ] Define authentication architecture
- [ ] Define authorisation architecture
- [ ] Define encryption architecture
- [ ] Define cryptographic key management
- [ ] Define backup and recovery model
- [ ] Define compromised-device behaviour
- [ ] Define incident/failsafe behaviour

### Prototype

- [ ] Prototype Pi Node
- [ ] Prototype authentication
- [ ] Prototype encrypted test storage
- [ ] Prototype secure client-to-node communication

---

## 11. Current Security Rule

> **No real sensitive data will be stored in Pi until its security architecture has been designed, reviewed and tested.**

Development must use synthetic or disposable test data.

Credentials, cryptographic keys, secrets and real personal data must never be committed to the Pi repository.