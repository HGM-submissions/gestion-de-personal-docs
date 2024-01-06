```plantuml
@startuml
class Car {
  + make: string
  + model: string
  + year: int
}
class Engine {
  + start()
  + stop()
}
Car *-- Engine
@enduml
```