#  INHERITENCE

1. once the class is declared as abstract it cannot be initiated.
2. at lewast one abstract method
3. Every inheriting class must override the parent class
4. an abstract class can have non abstract method also  

## Code
```py
# method overrinding is the concept of polymorphism

from abc import ABC , abstractmethod

class Animal(ABC):
    @abstractmethod
    def talk(self):
        print("Hello")
        pass

class Cat(Animal):  #method overrinding 
    def talk(self):
        print("Meow")

class Dog(Animal):   #method oveeriding
    def talk(self):
        print("woof")


# a = Animal() # not possible because animal is an abstract class
# '''TypeError: Can't instantiate abstract class Animal with abstract method talk  '''

c=Cat()
c.talk
d=Dog()
d.talk
```

## Code2
```py
# method overrinding is the concept of polymorphism

from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def talk(self):
        print("Hello")


class Cat(Animal):  #method overrinding
    def talk(self):
        # super.talk()
        print("Meow")

class Dog(Animal):   #method oveeriding
    def talk(self):
        print("woof")


# a = Animal() # not possible because animal is an abstract class
# '''TypeError: Can't instantiate abstract class Animal with abstract method talk  '''

class AnimalTalkShow:
    def dias(self,guest):
        if(isinstance(guest,Animal)):
            guest.talk()
talk_show = AnimalTalkShow()
c=Cat()
talk_show.dias(c)
d=Dog()
talk_show.dias(d)
```