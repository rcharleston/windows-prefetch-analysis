# Investigation: suspicious execution through Prefetch

## Scope

This is a simulated incident involving a fictional Initech workstation. The available artifact is Windows Prefetch. Original filesystem timestamps were not available in the exercise; the investigation relies on embedded execution data and referenced paths. The original article contains the detailed screenshots.

## Method

1. Parse the collected `.pf` directory with PECmd to produce the detailed CSV and timeline CSV.
2. Open both exports in Timeline Explorer, sort execution observations, and find the known suspicious filename.
3. Anchor the investigation on `BURPSUITE-PRO-CRACKED.EXE` at `2024-03-12 18:36:11`.
4. Tag nearby executions, then inspect individual files with PECmd's keyword filter.
5. Pivot on unusual executable paths, shared directories, and referenced files. Record observations separately from interpretations.
6. Return to the complete timeline to check scope, competing explanations, and gaps.

## Evidence and interpretation

| Observation in the published analysis | Working interpretation | Evidence needed to strengthen it |
|---|---|---|
| 7ZG referenced the similarly named cracked-software archive | Possible extraction before execution | Archive metadata, download history, and filesystem evidence |
| `B.EXE` referenced browser-related paths and `1.TXT` | Possible browser-data collection | File contents, binary analysis, and process telemetry |
| `C.EXE` referenced `WCEAUX.DLL` and `2.TXT` | Possible credential-access activity | Binary identity, memory/process evidence, and output contents |
| PowerShell referenced business documents and a backup/logs path | Possible collection or staging | Script-block logs, command lines, and file operations |
| Rclone referenced the staging directory, configuration, and `LSASS.DMP` | Possible exfiltration preparation | Rclone configuration, network logs, and destination evidence |
| A later `SD.EXE` run referenced many of the same staged files | Possible cleanup | Binary identity, command line, and filesystem changes |

## Timeline discipline

The accompanying CSV is a **selected observation list**, not a full forensic timeline. It distinguishes a single recorded run from a last-run value. Timestamps are preserved as displayed in the published lab; the source does not establish their time zone. Do not silently convert them to UTC.

Prefetch can support execution and file-reference analysis. It does not independently identify a human actor, reveal every command-line argument, establish parent/child process relationships, or prove data transfer. Legitimate tools can also appear in ordinary administration.

## Conclusion

The investigation produced a scoped set of suspicious executions and useful pivots for a broader incident investigation. The strongest next step would be correlation with event logs, process telemetry, browser history, filesystem artifacts, and network records. The value is in explaining what the artifact supports—and where the evidence stops.

## Source

[Roman Charleston — Prefetch Analysis Home Lab](https://medium.com/@romancharleston/prefetch-analysis-home-lab-4c9e376c9e01)
