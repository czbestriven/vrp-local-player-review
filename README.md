# VRP Local Player Connector — Independent Review Kit

This repository provides a Windows x64 synthetic-media environment for reviewing the VRP local-player extension. It is separate from the normal end-user installation flow.

## Download and run

- [Review release](https://github.com/czbestriven/vrp-local-player-review/releases/tag/review-1.1.2-20261107-r1)
- [Windows x64 kit, approximately 127 MiB](https://github.com/czbestriven/vrp-local-player-review/releases/download/review-1.1.2-20261107-r1/VRP-Review-Windows-x64.zip)
- [Archive checksum](https://github.com/czbestriven/vrp-local-player-review/releases/download/review-1.1.2-20261107-r1/VRP-Review-Windows-x64.zip.sha256)
- [English instructions](INSTALL-en.txt) / [中文步骤](INSTALL-zh-CN.txt)

Extract the entire ZIP, then run `Start-Review.cmd`. The service listens only at `http://127.0.0.1:18765`. Use a separate Windows test account or VM, Microsoft Edge, and the real PotPlayer executable. Follow the instructions to bind the actual extension identity and confirm local media access. The kit includes its .NET runtime and a synthetic eight-second clip.

The extension and native helper use their normal request validation and playback protocol. There is no reviewer-specific code path. The service is explicitly a single-sample fixture, not a full VRP/PostgreSQL backend. The executable and helper installer are unsigned review candidates.

## Preflight scope

The publisher reported Windows Edge 157 detection, visible PotPlayer playback, expected invalid-request/expired-ticket/unauthorized-folder errors, player continuation after Edge closed, native-host unavailability after uninstall, and the listener stopping with its console. See [the scoped result](PREFLIGHT-SUMMARY.json).

This release updates guides and metadata after that report. Executables, extension files and sample bytes are unchanged from the preflight kit. Original source files/component descriptors inside the archive preserve build-time snapshots. This report is not store approval, a complete filesystem/registry cleanup audit, NAS acceptance or production deployment acceptance.

## Identity

Kit SHA-256: `a8f61efc68e02841b3319c7619081f4ed652677d927ab9199ba0a2a21c43fc7c`

Extension submission ZIP SHA-256: `6795cc701abc5ca0a3f4cffdca19ff1a7628c046d126bf4a306c66b7f543bfc3`.

The matching extension allows the existing configured private deployment origin and the exact loopback review pair. The native helper still requires explicit local identity, site, HTTP and media-root permissions. An unpacked extension ID must not be substituted for the store-assigned ID.

[Privacy statement](https://czbestriven.github.io/vrp-local-player-privacy/) · Support: 449541117@qq.com
