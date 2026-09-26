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
