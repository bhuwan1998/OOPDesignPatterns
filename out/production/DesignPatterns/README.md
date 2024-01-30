# Design Patterns

## Structural Patterns





<hr/>

## Behaviour Patterns

### Memento Pattern

Memento - Implementation and Testing below showcasing the restore/undo functionality

```var editor = new Editor(); // to create a state and add it to history
var history = new History(); // state history - with a stack

editor.setContent("a"); // make new content
history.push(editor.createState()); // add it to history

editor.setContent("b");
history.push(editor.createState());

editor.setContent("c"); // at the moment
history.push(editor.createState());

editor.setContent("d"); // at the moment
history.push(editor.createState());

editor.restore(history.pop()); // restore - still encapsulated
System.out.println(editor.getContent());

editor.restore(history.pop());
System.out.println(editor.getContent());

editor.restore(history.pop());
System.out.println(editor.getContent());

editor.restore(history.pop());
System.out.println(editor.getContent());
```

### State Pattern

State Design Pattern - Using the Tool interface, different tool types implementing the interface
are created when set a new tool on the canvas. The mouseup and mousedown functions
don't need to setup separately in a switch case or an if and else case

#### Example 1 - Canvas


```var canvas = new Canvas();
canvas.setCurrentTool(new SelectionTool()); // an object that implements the interface (Selection or Brush)
canvas.mouseDown();
canvas.mouseUp();

canvas.setCurrentTool(new BrushTool());
canvas.mouseUp();
canvas.mouseDown();

canvas.setCurrentTool(new EraserTool());
canvas.mouseDown();
canvas.mouseUp();
```

#### Example 2 

![img.png](img.png)

Showcasing how the state pattern can be applied to a TCP Connection class to have 3 different behaviours such 
established, listen and closed using an abstract class here. 

## Creational Patterns 

### Builder Pattern 

The builder pattern abstracts creation of new objects without having to fill in all the fields of an object. Here for 
example the car has multiple fields but I can use the CarBuilder class to build a Car object with any field I like. Using 
the multiple construct methods. This gives me the flexibility to create Car objects however I want to create them. Whether 
its just the car model or just with the colour and car brand.

```
Car car = new CarBuilder().id(10).color("Blue").build();
System.out.println(car.toString());

CarBuilder builder = new CarBuilder();
builder.brand("Mazda").engine("V8").color("Black");

Car secondCar = builder.build();
System.out.println(secondCar.toString());
```

### Prototype Pattern 

Specify the kinds of objects to create using a prototypical instance, and create new objects by copying the prototype. 
Basically the point is to copy an existing object rather than create a new instance from scratch, something that may 
include costly operations. The existing object acts as a prototype and contains the state of the object. The newly 
copied object may change same properties only if required. This approach saves costly resources and time, especially when
object creation is a heavy process. 

**When to use the Prototype Design Pattern**

When a system should be independent of how its product are created, composed and represented 
When the classes to instantiate are specified at run-time   

### Factory Pattern
<hr/>

### Abstract Factory Pattern

<hr/>

