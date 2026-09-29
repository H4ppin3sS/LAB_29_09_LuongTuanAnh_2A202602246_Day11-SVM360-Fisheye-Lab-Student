# L / R / M

L/R/M là thứ tự box in-scope theo XML của từng frame.

## adasind_128310.jpg
- L3+R5: LR_noM (mid)
- L2+R3+M3: LRM (mid)
- L4+R2+M1: LRM (edge)
- L1+R1+M2: LRM (center)
- R4+M6: RM_noL (center)
- M4: M_only (center)
## adasind_140160.jpg
- L2+R3: LR_noM (center)
- L1+R2+M4: LRM (mid)
- L3+R1+M2: LRM (edge)
- M1: M_only (edge)
- M3: M_only (center)
- M5: M_only (center)
- M6: M_only (mid)
## adasind_230910.jpg
- L5+R6+M6: LRM (edge)
- L6+R1+M1: LRM (mid)
- L7+R4+M7: LRM (center)
- L8+R9+M5: LRM (center)
- L2+R2+M4: LRM (mid)
- L10+R3+M3: LRM (center)
- L1+R8: LR_noM (mid)
- L3+R12+M10: LRM (mid)
- L4: L_only (center)
- L9: L_only (mid)
- L11+M9: LM_noR (mid)
- L12: L_only (mid)
- R5: R_only (mid)
- R7: R_only (mid)
- R10: R_only (center)
- R11: R_only (center)
- M8: M_only (mid)

## Zone × cell
| zone | LRM | LR_noM | LM_noR | L_only | RM_noL | R_only | M_only |
|---|---|---|---|---|---|---|---|
| center | 4 | 1 | 0 | 1 | 1 | 2 | 3 |
| mid | 5 | 2 | 1 | 2 | 0 | 2 | 2 |
| edge | 3 | 0 | 0 | 0 | 0 | 0 | 1 |
