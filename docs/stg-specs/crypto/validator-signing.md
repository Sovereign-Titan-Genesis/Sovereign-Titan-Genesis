STG Validator Signing Specification

Document Information

Field| Value
Document Name| validator-signing.md
Repository| STG-CONSESUS
Category| STG-SPECS / CRYPTO
Version| V1-2026
Status| Draft Specification
Classification| Consensus Security

---

1. Purpose

Dokumen ini mendefinisikan:

- aturan perilaku validator,
- mekanisme signing consensus,
- adaptive slashing model,
- dan deterministic penalty enforcement
  untuk ekosistem STG.

---

2. Design Objectives

Tujuan utama:

- menjaga consensus integrity,
- mencegah malicious signing,
- menjaga validator fairness,
- meminimalkan false positive slashing,
- menjaga network liveness,
- dan mendukung decentralized validator participation.

---

3. Validator Responsibilities

Validator wajib:

- menjaga availability node,
- menandatangani block valid,
- menjaga session key security,
- mematuhi rotation policy,
- menjaga synchronization state,
- dan mengikuti governance protocol.

---

4. Validator Signing Rules

Validator TIDAK BOLEH:

- melakukan double-signing,
- menandatangani conflicting blocks,
- menandatangani invalid state transition,
- menggunakan revoked session key,
- mengabaikan mandatory rotation,
- memalsukan validator identity.

---

5. Consensus Signing Model

Signing Flow

Block Proposal
        ↓
Validator Verification
        ↓
Session Key Signing
        ↓
Signature Broadcast
        ↓
Consensus Aggregation
        ↓
Finalization

---

6. Validator State Classification

State| Description
ACTIVE| Validator sehat dan sinkron
DEGRADED| Validator mengalami latency tinggi
UNSYNCHRONIZED| Validator tertinggal chain
PENALIZED| Validator sedang terkena penalti
SUSPENDED| Validator kehilangan hak signing sementara
EJECTED| Validator dikeluarkan dari consensus

---

7. Adaptive Penalty Curve

Penalty Philosophy

Sistem penalti bersifat progresif dan adaptif.

Tujuan:

- membedakan gangguan teknis dengan tindakan jahat,
- mencegah cartel abuse,
- menjaga validator kecil tetap bisa berpartisipasi.

---

8. Penalty Levels

Violation| Initial Action| Escalation
Minor downtime| Warning| Small slash
Repeated downtime| Small slash| Suspension
Missed rotation| Temporary restriction| Slash
Invalid signing| Medium slash| Suspension
Double signing| Severe slash| Ejection
Fraud proof confirmed| Maximum slash| Permanent ejection

---

9. Slashing Principles

Slashing wajib:

- deterministic,
- publicly auditable,
- replay-resistant,
- machine-verifiable,
- proportional terhadap severity.

---

10. Network Health Awareness

Sistem wajib memeriksa:

- network latency,
- partition condition,
- synchronization anomalies,
- global validator health,
- propagation delay,

sebelum penalti berat diterapkan.

---

11. False Positive Protection

Validator TIDAK boleh dihukum berat apabila:

- terjadi network partition,
- RPC infrastructure failure,
- global synchronization delay,
- atau consensus instability global.

---

12. Double Signing Detection

Detection Conditions

Validator dianggap double-sign apabila:

- menggunakan validator identity sama,
- menandatangani dua conflicting blocks,
- pada consensus slot identik.

---

13. Double Signing Enforcement

Conflict Detected
        ↓
Signature Verification
        ↓
Evidence Validation
        ↓
Penalty Proposal
        ↓
Governance Confirmation
        ↓
Slashing Execution

---

14. Slashing Escalation Model

Offense Count| Penalty
First| Warning
Second| Small slash
Third| Medium slash
Fourth| Suspension
Fifth| Ejection review

---

15. Validator Suspension Rules

Validator dapat disuspend apabila:

- gagal melakukan rotation,
- mengalami desynchronization berat,
- menunjukkan abnormal signing pattern,
- atau gagal memenuhi minimum uptime governance.

---

16. Ejection Rules

Validator dapat dikeluarkan apabila:

- melakukan malicious consensus manipulation,
- melakukan repeated double signing,
- melakukan governance attack,
- atau terbukti melakukan coordinated fraud.

---

17. Audit Logging

Seluruh aktivitas validator wajib:

- dicatat immutable,
- dapat diverifikasi explorer,
- kompatibel dengan indexer,
- dan tersedia untuk auditor governance.

---

18. AI Monitoring Boundaries

STG-AI hanya diperbolehkan:

- membaca event logs,
- mendeteksi anomaly,
- menghasilkan risk score,
- memberikan recommendation.

STG-AI TIDAK BOLEH:

- melakukan slashing otomatis,
- memegang signing authority,
- melakukan consensus override,
- atau mengganti validator state secara langsung.

---

19. Emergency Governance

Emergency governance hanya dapat dilakukan melalui:

- multi-signature quorum,
- governance council,
- audit-logged execution,
- dan transparent emergency procedure.

---

20. Treasury Interaction

Validator reward dapat berasal dari:

- block reward,
- treasury allocation,
- staking incentive,
- governance incentive.

Seluruh distribusi wajib:

- transparent,
- auditable,
- dan consensus-approved.

---

21. Hardware Security Requirements

Validator wajib mendukung:

- secure key storage,
- hardware wallet compatibility,
- HSM integration,
- offline recovery support,
- dan secure enclave capability.

---

22. Future Post-Quantum Migration

Validator architecture wajib mendukung:

- hybrid signature transition,
- PQC compatibility layer,
- dual-sign verification,
- dan cryptographic agility.

---

23. Threat Model

Dokumen ini dirancang untuk memitigasi:

- validator cartelization,
- malicious signing,
- replay attack,
- rogue validator coordination,
- governance abuse,
- false slashing,
- dan compromised validator infrastructure.

---

24. Status

Dokumen ini merupakan draft spesifikasi consensus validator behavior untuk:

- STG consensus layer,
- validator lifecycle governance,
- dan sovereign infrastructure hardening.
