# Design Patterns

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
<hr/>

### Factory Pattern
<hr/>

### Abstract Factory Pattern

<hr/>

### State Pattern

State Design Pattern - Using the Tool interface different tool types implementing it
are created when set a new tool on the canvas. The mouseup and mousedown functions
don't need to setup separately in a switch case or an if and else case

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
