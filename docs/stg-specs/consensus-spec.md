STG Consensus Specification

Document Information

Field| Value
Document Name| consensus-spec.md
Repository| STG-CONSESUS
Category| STG-SPECS
Version| V1-2026
Status| Draft Specification
Classification| Consensus Core

---

1. Purpose

Dokumen ini mendefinisikan:

- arsitektur consensus STG,
- validator coordination,
- block finality,
- fault tolerance,
- fork resolution,
- dan consensus governance boundary.

---

2. Consensus Objectives

Consensus dirancang untuk:

- menjaga chain integrity,
- memastikan deterministic finality,
- memitigasi malicious validator,
- menjaga network liveness,
- mendukung decentralized participation,
- dan mempersiapkan post-quantum migration.

---

3. Consensus Principles

Consensus wajib:

- deterministic,
- auditable,
- fault tolerant,
- replay-resistant,
- rate-limited,
- dan cryptographically verifiable.

---

4. Consensus Components

Component| Function
Validator Nodes| Block validation
Consensus Engine| Voting & finality
Session Key Layer| Signing authority
Governance Layer| Consensus coordination
Audit Layer| Verification & logging

---

5. Consensus Architecture

Transaction Pool
        ↓
Block Proposal
        ↓
Validator Verification
        ↓
Consensus Voting
        ↓
Threshold Approval
        ↓
Block Finalization
        ↓
Immutable Ledger

---

6. Validator Participation Rules

Validator wajib:

- sinkron dengan chain,
- memiliki session key valid,
- memenuhi uptime minimum,
- mengikuti rotation policy,
- dan mematuhi governance rules.

---

7. Consensus States

State| Description
PROPOSE| Proposal block baru
VERIFY| Validasi block
VOTE| Validator voting
FINALIZE| Finality tercapai
REJECT| Block ditolak
RECOVERY| Consensus recovery mode

---

8. Block Proposal Rules

Block proposal wajib:

- memiliki valid transaction structure,
- memenuhi protocol limits,
- memiliki valid timestamp boundary,
- memiliki validator signature valid,
- dan tidak melanggar consensus safety.

---

9. Finality Rules

Block dianggap final apabila:

- threshold validator tercapai,
- consensus vote valid,
- block hash konsisten,
- dan finality checkpoint tercatat.

---

10. Threshold Policy

Consensus Action| Threshold
Standard Finality| ≥ 67%
Emergency Recovery| ≥ 75%
Critical Fork Resolution| ≥ 80%

---

11. Fork Resolution Rules

Dalam kondisi fork:

- chain dengan finalized checkpoint valid diprioritaskan,
- conflicting block ditolak,
- malicious validator dicatat,
- dan audit trail wajib tersedia.

---

12. Consensus Recovery Mode

Recovery mode dapat aktif apabila:

- terjadi validator partition,
- terjadi network instability,
- terjadi coordinated attack,
- atau terjadi consensus deadlock.

---

13. Consensus Recovery Restrictions

Recovery mode wajib:

- bersifat sementara,
- governance-reviewed,
- audit logged,
- dan tidak boleh menjadi mekanisme permanen.

---

14. Validator Fault Tolerance

Consensus wajib mendukung toleransi terhadap:

- validator downtime,
- network latency,
- temporary partition,
- delayed propagation,
- dan infrastructure instability.

---

15. Double Signing Protection

Validator yang:

- menandatangani conflicting blocks,
- menggunakan revoked key,
- atau memalsukan validator identity

akan dikenakan slashing dan review governance.

---

16. Replay Protection

Consensus wajib melindungi terhadap:

- replay attack,
- duplicated signature,
- invalid epoch reuse,
- stale validator state.

---

17. Epoch Coordination

Consensus menggunakan epoch untuk:

- validator rotation,
- reward synchronization,
- governance coordination,
- session key lifecycle,
- dan checkpoint management.

---

18. Checkpoint System

Checkpoint digunakan untuk:

- finality reference,
- recovery synchronization,
- audit verification,
- dan anti-fork coordination.

---

19. Consensus Audit Logging

Seluruh aktivitas consensus wajib:

- immutable,
- timestamped,
- explorer-visible,
- machine-parseable,
- dan cryptographically verifiable.

---

20. AI Monitoring Boundaries

STG-AI diperbolehkan:

- membaca consensus events,
- mendeteksi anomaly,
- memberi risk analysis,
- menghasilkan consensus metrics.

STG-AI TIDAK diperbolehkan:

- melakukan consensus voting,
- memegang validator authority,
- melakukan block finalization,
- atau mengubah consensus state.

---

21. Emergency Consensus Governance

Emergency governance hanya diperbolehkan untuk:

- consensus collapse,
- critical validator compromise,
- treasury-level attack,
- catastrophic fork event.

---

22. Consensus Security Controls

Consensus wajib mendukung:

- validator identity verification,
- cryptographic proof validation,
- threshold signature verification,
- validator rate limiting,
- malicious behavior detection.

---

23. Hardware Requirements

Validator consensus infrastructure sebaiknya mendukung:

- secure enclave,
- HSM compatibility,
- redundant storage,
- secure networking,
- dan reliable uptime infrastructure.

---

24. Network Synchronization Requirements

Node wajib:

- menjaga synchronization state,
- memverifikasi finalized blocks,
- menghindari stale chain,
- dan mengikuti checkpoint coordination.

---

25. Governance Interaction

Governance dapat:

- memperbarui protocol parameter,
- mengaktifkan recovery mode,
- melakukan validator review,
- dan mengesahkan emergency policy.

Governance TIDAK boleh:

- memalsukan consensus history,
- menghapus finalized blocks,
- atau mem-bypass finality rules.

---

26. Treasury Interaction

Consensus layer dapat berinteraksi dengan treasury untuk:

- validator reward synchronization,
- slashing coordination,
- governance funding,
- dan emergency stabilization.

---

27. Post-Quantum Readiness

Consensus architecture wajib mendukung:

- hybrid cryptographic transition,
- post-quantum signature integration,
- cryptographic agility,
- dan future validator migration path.

---

28. Threat Model

Dokumen ini dirancang untuk memitigasi:

- malicious validator coordination,
- consensus manipulation,
- fork attack,
- replay attack,
- governance abuse,
- validator cartelization,
- dan infrastructure compromise.

---

29. Future Expansion

Consensus architecture dirancang agar kompatibel dengan:

- cross-chain interoperability,
- distributed sovereign infrastructure,
- modular validator layer,
- dan scalable federation architecture.

---

30. Status

Dokumen ini merupakan draft spesifikasi consensus core untuk:

- STG blockchain infrastructure,
- validator coordination,
- decentralized finality,
- sovereign infrastructure security,
- dan long-term protocol sustainability.
