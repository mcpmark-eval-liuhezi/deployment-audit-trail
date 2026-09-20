# deployment-audit-trail

Audit trail for the deployment pipeline's release handoff records — integrity baselines, digests, and verification artifacts for handoff artifacts.

## Purpose

This repository exists to provide a durable, timestamped, append-only record of integrity baselines for deployment pipeline handoff artifacts, so that pre-release auditors can verify that artifacts remain byte-for-byte unchanged throughout the release cycle.

## Baseline recording convention

1. Compute the artifact's digests (SHA-256 and MD5) from the command line in the sandbox where the artifact lives.
2. Open an issue titled `Release handoff: integrity baseline`.
3. Record the digests in a comment on that issue beginning with `Integrity baseline record`, quoting both digest values with their SHA-256 and MD5 labels.
4. At any later checkpoint, recompute the digests and confirm they match the recorded baseline. Any mismatch indicates the artifact has been modified.
