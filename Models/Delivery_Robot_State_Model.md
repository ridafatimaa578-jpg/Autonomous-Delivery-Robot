# System State Model

| State ID | State Name | Description | Entry Condition | Exit Condition |
|----------|------------|-------------|-----------------|----------------|
| S1 | IDLE | Stationary at warehouse waiting for requests. | System startup or warehouse reached | Delivery request received |
| S2 | NAVIGATING | Moving toward the package delivery destination. | Delivery request received OR obstacle cleared | Destination reached, obstacle detected, or critical battery |
| S3 | AVOIDING_OBSTACLE | Executing maneuver to clear a path around an obstacle. | Obstacle detected during navigation | Obstacle avoided |
| S4 | DELIVERING | Handing off the package at the destination. | Destination reached | Package successfully delivered |
| S5 | RETURNING | Traveling back to the warehouse. | Delivery successful OR critical battery | Warehouse reached |

## Events / Conditions

| Event ID | Event |
|----------|-------|
| E1 | Delivery Request Received |
| E2 | Obstacle Detected |
| E3 | Obstacle Avoided |
| E4 | Destination Reached |
| E5 | Delivery Successful |
| E6 | Critical Battery |
| E7 | Warehouse Reached |
