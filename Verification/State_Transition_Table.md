# State Transition Table

| Transition ID | From State | Event | To State | Req |
|---------------|------------|-------|----------|-----|
| T1 | IDLE | Delivery Request Received | NAVIGATING | R2 |
| T2 | NAVIGATING | Obstacle Detected | AVOIDING_OBSTACLE | R4 |
| T3 | AVOIDING_OBSTACLE | Obstacle Avoided | NAVIGATING | R5 |
| T4 | NAVIGATING | Destination Reached | DELIVERING | R6 |
| T5 | DELIVERING | Delivery Successful | RETURNING | R7 |
| T6 | NAVIGATING | Critical Battery | RETURNING | R8 |
| T7 | RETURNING | Warehouse Reached | IDLE | R1 |

---

# Verification Analysis

### Check 1 — Invalid Transition (IDLE -> DELIVERING)
- **Status:** Invalid
- **Violation:** Violates **Requirement R9**.
- **Finding:** The robot cannot directly deliver packages without receiving a request and navigating to the destination first.

### Check 2 — Missing Transition (AVOIDING_OBSTACLE without return)
- **Status:** Critical Defect
- **Finding:** Without the return transition (`AVOIDING_OBSTACLE` -> `NAVIGATING`), the robot remains stuck in the obstacle-avoidance state and cannot resume or finish its journey.

### Check 3 — Obstacle During Delivery (AVOIDING_OBSTACLE -> DELIVERING)
- **Status:** Invalid
- **Violation:** Violates **Requirement R10**.
- **Finding:** The robot must transition back to `NAVIGATING` to verify path clearance before reaching the destination and beginning delivery.
