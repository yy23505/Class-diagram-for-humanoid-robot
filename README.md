# Class-diagram-for-humanoid-robot
@startuml
class Robot {
    - position: (int, int)
    - battery_level: int
    + move(direction: String): void
    + charge(): void
    + pick_up(object: (int, int)): void
    + place(object: (int, int)): void
}

class Environment {
    - obstacles: List<(int, int)>
    - objects: List<(int, int)>
    + add_obstacle(obstacle: (int, int)): void
    + remove_obstacle(obstacle: (int, int)): void
    + get_objects(): List<(int, int)>
}

class Human {
    - name: String
    - commands: List<String>
    + send_command(command: String): void
    + receive_feedback(feedback: String): void
}

Robot --> Environment : interacts with
Human --> Robot : sends commands
@enduml
