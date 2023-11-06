## Alternative Parts

Some components can be swapped for more cheaper or more available parts,
without impacting the functionality of the epdiy controlling board.
If you find other alternatives that may be useful to others, please submit a pull request!

| Part name      | Replacement Name   | Default LCSC ID   | Replacement ID  | Comments                                                  |
| -------------  | ----------------   | ----------------- | --------------- | ---------                                                 |
| TPS651851RSLR  | TPS65185RSLR       | C139292           | C702311         | Only if your panel size <= 9"                             |
| XF2M-3315-1A** | FH12-33S-0.5SH(55) | C231420           | C597986         | Omron connector is better quality than Hirose replacement |
| MBR0540T1G     | B5819W SL          | C8598             | C21353          | Much cheaper diode when ordering from LCSC                |

** IMPORTANT: XF2M-3315-1A replacement C597986 uses a slightly different footprint. It has to be updated in KiCad PCB before sending fabrication files to production.
