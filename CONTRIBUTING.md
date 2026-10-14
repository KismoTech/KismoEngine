# Contributing

KismoEngine is dual-licensed: AGPL-3.0-only, or a commercial licence (see [NOTICE](NOTICE)).

**Inbound terms.** By submitting a contribution you certify that:

1. you have the right to contribute it (the [Developer Certificate of Origin](https://developercertificate.org/)); and
2. you grant Craig Hutchinson (and Craig Hutchinson's successors and assigns) permission to distribute your
   contribution under AGPL-3.0 and under other licence terms, including commercial licences.

Add a sign-off to each commit: `Signed-off-by: Your Name <email@example.com>` (`git commit -s`).

- **Product-neutral:** no game rules or product policy in engine APIs.
- **Determinism:** changes to the loop, world or replay keep full-state replay parity, with tests.
- **Dependencies:** only add third-party code whose licence is compatible with AGPL-3.0 *and* with
  commercial distribution (permissive licences such as MIT, BSD, zlib or Apache-2.0). Record them in NOTICE.

Commercial licence questions: open a "Commercial License Request" issue; don't use email.
