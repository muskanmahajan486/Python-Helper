# OOPS in Python

# Class


```python
class Student:
    def __init__(self,n,a):
        self.name = n
        self.age = a
```

# Object


```python
stu_1 = Student("Ram",20)
```


```python
print(stu_1.name,"is",stu_1.age,"years old.")
```

    Ram is 20 years old.
    

# Method


```python
class Email:
    def __init__(self):
        self.isMailSent = False
    def sendEmail(self):
        self.isMailSent = True
```


```python
email = Email()
```


```python
email.isMailSent
```




    False




```python
email.sendEmail()
```


```python
email.isMailSent
```




    True



# Inheritance

* single
* multilevel
* hierarchical
* multiple 
* hybrid

## Single Inheritance
<img src="Img/single.jpg"/>


```python
class Super_Class:    
    def IAmSuperClass(self):
        print("Super class")
class Sub_class(Super_Class):
    def IAmSubClass(self):
        print("Sub Class")
```


```python
super_class = Super_Class()
super_class.IAmSuperClass()
```

    Super class
    


```python
sub_class = Sub_class()
sub_class.IAmSubClass()
sub_class.IAmSuperClass()
```

    Sub Class
    Super class
    

# Multiple Inheritance

<img src="Img/Multiple.jpg"/>


```python
class SuperClass1:
    def IAmSuper1(self):
        print("Super 1")

class SuperClass2:
    def IAmSuper2(self):
        print("Super 2")
        
class SubClass(SuperClass1,SuperClass2):
    def IAmSubClass(self):
        print("Sub Class")
```


```python
super1 = SuperClass1()
super1.IAmSuper1()
```

    Super 1
    


```python
super2 = SuperClass2()
super2.IAmSuper2()
```

    Super 2
    


```python
sub = SubClass()
sub.IAmSubClass()
sub.IAmSuper1()
sub.IAmSuper2()
```

    Sub Class
    Super 1
    Super 2
    

# Multilevel Inheritance

<img src="Img/Multilevel.jpg"/>


```python
class SuperClass:
    def IAmSuper(self):
        print("Super")
        
class Sub1(SuperClass):
    def IAmSub1(self):
        print("Sub 1")
        
class Sub2(Sub1):
    def IAmSub2(self):
        print("Sub 2")
```


```python
superClass = SuperClass()
superClass.IAmSuper()
```

    Super
    


```python
sub1 = Sub1()
sub1.IAmSub1()
sub1.IAmSuper()
```

    Sub 1
    Super
    


```python
sub2 = Sub2()
sub2.IAmSub2()
sub2.IAmSub1()
sub2.IAmSuper()
```

    Sub 2
    Sub 1
    Super
    

# Hierarchical Inheritance

<img src="Img/hierarchical.jpg" />


```python
class SuperClass:
    def IAmSuper(self):
        print("Super")
        
class Sub1(SuperClass):
    def IAmSub1(self):
        print("Sub 1")
        
class Sub2(SuperClass):
    def IAmSub2(self):
        print("Sub 2")
        
class Sub3(SuperClass):
    def IAmSub3(self):
        print("Sub 3")
```


```python
superClass = SuperClass()
superClass.IAmSuper()
```

    Super
    


```python
sub1 = Sub1()
sub1.IAmSub1()
sub1.IAmSuper()
```

    Sub 1
    Super
    


```python
sub2 = Sub2()
sub2.IAmSub2()
sub2.IAmSuper()
```

    Sub 2
    Super
    


```python
sub3 = Sub3()
sub3.IAmSub3()
sub3.IAmSuper()
```

    Sub 3
    Super
    

# Hybrid Inheritance

<img src="Img/Hybrid.jpg"/>


```python
class SuperClass:
    def IAmSuper(self):
        print("Super")
        
class Sub1(SuperClass):
    def IAmSub1(self):
        print("Sub 1")
        
class Sub2(SuperClass):
    def IAmSub2(self):
        print("Sub 2")
        
class Sub3(Sub1, Sub2):
    def IAmSub3(self):
        print("Sub 3")
```


```python
superClass = SuperClass()
superClass.IAmSuper()
```

    Super
    


```python
sub1 = Sub1()
sub1.IAmSub1()
sub1.IAmSuper()
```

    Sub 1
    Super
    


```python
sub2 = Sub2()
sub2.IAmSub2()
sub2.IAmSuper()
```

    Sub 2
    Super
    


```python
sub3 = Sub3()
sub3.IAmSub1()
sub3.IAmSub2()
sub3.IAmSub3()
sub3.IAmSuper()
```

    Sub 1
    Sub 2
    Sub 3
    Super
    

# Abstraction


```python
from abc import ABC, abstractmethod 
  
class Shapes(ABC):
    @abstractmethod
    def no_of_sides(self):
        pass
    
class Square(Shapes):
    def no_of_sides(self):
        print("4 Sides")
        
class Rectangle(Shapes):
    def display(self):
        print("Hi")
        
class Triangle(Shapes):
    def no_of_sides(self):
        print("3 Sides")
```


```python
square = Square()
square.no_of_sides()
```

    4 Sides
    


```python
rectangle = Rectangle()
rectangle.display()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-32-beab8ec7dd23> in <module>
    ----> 1 rectangle = Rectangle()
          2 rectangle.display()
    

    TypeError: Can't instantiate abstract class Rectangle with abstract methods no_of_sides



```python
triangle = Triangle()
triangle.no_of_sides()
```

    3 Sides
    

# Encapsulation

<img src="Img/Encapsulation.png"/>


```python
class Base:
    def __init__(self):
        self.public = 1
        self._protected = 2
        self.__private = 3
    def display(self):
        print("Protected =",self._protected)
        print("Private =",self.__private)
        
class Derived(Base):
    def __init__(self):
        Base.__init__(self)
        print("Public :",self.public)
        print("Protected :",self._protected)
        print("Private :",self.__private)
```


```python
base = Base()
print("Public =",base.public)
print("Protected =",base._protected)
print("Private =",base.__private)
```

    Public = 1
    Protected = 2
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-35-17f8942db81e> in <module>
          2 print("Public =",base.public)
          3 print("Protected =",base._protected)
    ----> 4 print("Private =",base.__private)
    

    AttributeError: 'Base' object has no attribute '__private'



```python
base.display()
```

    Protected = 2
    Private = 3
    


```python
derived = Derived()
```

    Public : 1
    Protected : 2
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-37-8b1f9d30210c> in <module>
    ----> 1 derived = Derived()
    

    <ipython-input-34-50fa178bca4a> in __init__(self)
         13         print("Public :",self.public)
         14         print("Protected :",self._protected)
    ---> 15         print("Private :",self.__private)
    

    AttributeError: 'Derived' object has no attribute '_Derived__private'

