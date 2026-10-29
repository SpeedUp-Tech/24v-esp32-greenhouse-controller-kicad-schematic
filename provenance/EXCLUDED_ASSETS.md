# Source bundle exclusions for v0.2.0

The public package contains the new project settings, seven editable schematic sheets, CSV BOM, and schematic evidence. The following supplied files remain local:

- `Smart_Greenhouse_Controller.kicad_pcb`: embedded footprint geometry has no established upstream redistribution record.
- `symbols/*.kicad_sym`, `libs/ProjectPCB.pretty/*.kicad_mod`, `sym-lib-table`, and `fp-lib-table`: standalone library provenance is unverified.
- `Smart_Greenhouse_Controller.kicad_dru` and `Smart_Greenhouse_Controller.pcb.svg`: PCB-related artifacts outside the approved schematic-only publication scope.
- `DesignDocument.pdf` and `BillOfMaterials.xlsx`: original source report/workbook; not included in the public schematic update. The report's requirement and architecture were checked against the schematic.
- `*.kicad_prl`, `*-backups/`, `.DS_Store`, and `.copperpilot/`: local application state, backups, and internal review material.

No engineering files in the supplied Downloads folder were modified.
