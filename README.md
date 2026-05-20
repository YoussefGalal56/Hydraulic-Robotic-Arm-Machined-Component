## Project — Hydraulic Robotic Arm & Machined Component

![CATIA](https://img.shields.io/badge/CATIA%20V5-3D%20Design-005BAC?style=flat-square)
![Inventor](https://img.shields.io/badge/Inventor%20CAM-CNC%20Simulation-E8590A?style=flat-square)
![Laser](https://img.shields.io/badge/Laser%20Cutting-Cardboard-black?style=flat-square)
![Lathe](https://img.shields.io/badge/Centre%20Lathe-Steel%20Rod-grey?style=flat-square)

**Module:** Integrated Manufacturing &nbsp;|&nbsp; **Supervised by:** Dr. Hesham Mohammed · Eng. Khaled &nbsp;|&nbsp; **Team:** Section 5, Group 2

---

### Overview

A two-part project combining physical design and manufacture:

- **Part I** — Designed a hydraulic robotic arm in CATIA V5, laser-cut from cardboard, actuated by an 8-syringe hydraulic circuit. The arm picks and places marshmallows within a 200–300 mm reach range.
- **Part II** — Machined a low-carbon steel rod to spec using a centre lathe, drilling machine, and milling machine; then recreated the part in Inventor CAM and generated G-code for CNC production.

---

### Part I — Hydraulic Robotic Arm

**Design & Fabrication**

- 3D modelled and assembled in **CATIA V5**; full orthographic and assembly drawings produced
- Structural parts laser-cut from cardboard (`150W / 40% power · 20 mm/s · 4 mm width`)
- Toothpick-and-support pivot joints connect humerus (200×40 mm) and ulna (250×40 mm) arm segments
- Gripper assembly (triangle + finger + supports) glued to arm end; actuated by dedicated syringe pair
- Bolt sub-component: ground to 22 mm length → diameter reduced on lathe → threaded in machine vice

**Hydraulic System**

- 8 × 10 ml syringes paired across 4 axes (base rotation, shoulder, elbow, gripper)
- Tubes filled with water; air purged before assembly to ensure consistent motion
- Syringes mounted with zip ties or glue per the assembly drawing

**Constraints Met**

| Constraint | Target | Result |
|------------|--------|--------|
| Base footprint | ≤ 250 × 250 mm | ✅ |
| Arm reach | 200 – 300 mm | ✅ |
| Self-supporting | No external aid | ✅ |
| Task | Transfer 3 marshmallows | ✅ |

---

### Part II — Steel Rod Machining

**Manual Machining Sequence**

| Step | Operation | Machine |
|------|-----------|---------|
| 1 | Cut stock to length | Circular saw + vice |
| 2 | Diameter reduction | Centre lathe (3-jaw chuck) |
| 3 | Turn nubs on both ends | Centre lathe + tailstock |
| 4 | Chamfer nub edges | Centre lathe |
| 5 | Drill 3 top-face holes | Drill press + vice |
| 6 | Face-mill flat on nubs | Milling machine + vice |
| 7 | Thread nubs + M10 centre | Tap wrench + die stock |

**Key Dimensions**

```
Stock:        Ø23 mm × 161 mm  (low-carbon steel)
Final length: 130 mm
Groove:       3 mm wide
Holes:        M10 centre · Ø6 mm (×2)
Chamfer:      45°
Spindle:      630 RPM  |  Feed: 0.15 mm/rev
```

---

### CAM (Inventor) — Setup Summary

Two setups were used; 30 mm extra stock held in 3-jaw chuck was removed by grooving at the start of Setup 2.

**Setup 1 operations (in order):**
`Face2` → `Drill4 (rapid out)` → `Profile Roughing1` → `Profile Finishing1` → `Single Groove1` → `Face1` → `Thread1` → `Drill6 (rapid out)` → `Drill1` → `Drill2` → `Drill3 (tap)`

**Setup 2 operations:**
`Groove2` → `Face2` → `Profile Roughing1` → `Profile Finishing1` → `Single Groove1` → `Face1` → `Thread1`

> Setup sheet and full G-code are included in the [lab report](./Project_01/Lab_Report_Section5_Group2.pdf).

---

### Time Evaluation

**Calculated roughing time** (L / f × N):

```
L = 130 + 3 (approach) + 2 (over-travel) = 135 mm
f = 0.15 mm/rev  |  N = 630 rpm
Time = 135 / (0.15 × 630) = 1.43 min / pass
```

| Measure | Time |
|---------|------|
| CAM estimated cycle time | 18 min 27 s |
| Actual workshop time | ~4 hours |

**Gap explained by:** workpiece zeroing touches, frequent measurement verification, tool-change overhead (not modelled in CAM), equipment downtime, and operator learning curve.

---

### Reflection

> *"In the future I would like to design the arm links in a truss shape to reduce material volume and improve the smoothness of hydraulic motion."*

---
---
