# PECmd command reference

Use an authorized, preserved evidence copy. Set the paths for your own workstation and obtain the tools from [Eric Zimmerman's official page](https://ericzimmerman.github.io/).

## Export a directory

```powershell
$pecmdPath = 'C:\DFIR_Tools\ZimmermanTools\net6\PECmd.exe'
$evidencePath = 'C:\Cases\Prefetch'
$analysisPath = 'C:\Cases\Analysis'
& $pecmdPath -q -d $evidencePath --csv $analysisPath --csvf prefetch.csv
```

Inspect `prefetch.csv` and `prefetch_Timeline.csv` in Timeline Explorer. Verify the timezone and tool version used before combining results with other evidence.

## Inspect one file

```powershell
& $pecmdPath -k burpsuite -f 'C:\Cases\Prefetch\7ZG.EXE-D9AA3A0B.pf'
```

This filename is from the simulated training scenario. Choose a file that actually exists in your own evidence set. Keyword hits are investigative leads; review the surrounding paths and execution context before assigning meaning.
