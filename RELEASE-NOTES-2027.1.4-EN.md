# StageMon 2027.1.4 — Windows

This maintenance moves the Windows candidate to .NET 10. Project formats, levels, mutes, routing, snapshots, StageFlow LIVE contracts and licence rights are preserved. The expired-trial reminder remains five seconds. Audio and remote control still require deliberate activation.

The delivered executable is the verified 2027.1.4 candidate compiled from `e7eb8431b1e06bedb4c489cc23968e20516f6687`, reused byte for byte. The standard installer was produced by the official recipe at packaging commit `3af79540c06f3089c6c06a499cde1e57af6b5703`. No 1.3 executable was renamed.

Retained candidate evidence records 348 test executions across five runs, ten Chromium scenario groups and six CLI checks: suite header 596, shutdown 1, connections 218, remote interop 68, local interop 26 and shared round trip 18. These checks were not repeated for packaging alone. New checks verify packaging source, all eleven candidate files, the payload prepared for Inno Setup, version, approved guides, manifests and SHA-256 digests.

Published on explicit human instruction on 11 October 2026 with native qualification pending. OS-window rendering and keyboard navigation were not qualified; automated captures were inconclusive and their cause was not established. Full DPI coverage, physical audio, live networks and phones remain unqualified. Actual standard installer execution, upgrade, shortcuts and rollback were not exercised for this delivery. Software tests do not replace these checks. This publication performs no installation on the personal PC.

macOS remains available as **2027.1.3** in its existing release. This 1.4 release publishes Windows only and claims no new 1.4 DMG. Complete NuGet advisory auditing remains to be confirmed.

Commercial terms are unchanged. Read `QUALIFICATION-2027.1.4.md`, `release-manifest.json` and `SHA256SUMS.txt`.
