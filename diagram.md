```
classDiagram
    direction BT %% TB, BT, RL, LR 모두 가능

    class Person {
        <<abstract>>
        +name : str
        +phoneNumber : str
        +purchasePakringPass()
    }

    class Student {
        +studentNumber : int
        +averageMark : int
        +isEligibleToEnroll(str) bool
        +getSeminarsTaken() : int

    }

    class Professor {
        -salary : int
        #staffNumber : int
        -yearsOfService : int
        +numberOfClasses : int
    }

    class Address {
        +street : str
        +city : str
        +state : str
        +postalCode : int 
        +country : str
        -validate() bool
        +outputAsLabel() str
    }

    Person <|-- Student
    Person <|-- Professor
    Student "0..*" <-- "1..5" Professor : supervise
    Person "0..1" --> "1" Address : lives in
    ```