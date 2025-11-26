```mermaid
classDiagram
class User {
+String name
+String email
+register()
}

class Membership {
+String type
+activate()
}

User "1" *-- "0..*" Membership : has