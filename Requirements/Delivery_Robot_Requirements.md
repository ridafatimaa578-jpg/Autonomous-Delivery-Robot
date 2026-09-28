# Functional & Behavioral Requirements

| Req ID | Description | Priority |
|--------|-------------|----------|
| R1 | The robot shall remain in an idle state waiting for a delivery request when powered on or upon completing a task. | High |
| R2 | Upon receiving a valid delivery request, the robot shall transition from idle to navigating toward the destination. | High |
| R3 | While navigating, the robot shall continuously scan its environment for obstacles. | Medium |
| R4 | Upon detecting an obstacle during navigation, the robot shall pause navigation and enter obstacle-avoidance mode. | High |
| R5 | Upon successfully clearing an obstacle, the robot shall resume navigation toward the destination. | High |
| R6 | Upon reaching the destination, the robot shall initiate and process package delivery. | High |
| R7 | Upon completing package delivery, the robot shall begin navigating back to the warehouse. | High |
| R8 | If a critical battery level is detected during navigation, the robot shall abort its current task and return to the warehouse. | High |
| R9 | The robot shall not transition directly from an idle state to the delivery state without receiving a request and navigating to the destination first. | High |
| R10 | The robot shall not transition directly from the obstacle-avoidance state to the delivery state; it shall return to navigation to verify path clearance first. | High |
