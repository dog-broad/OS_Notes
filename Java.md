# Distinguish Multithreading and Multitasking.

Multi-tasking and multi-threading are two techniques used in operating systems. Multi-tasking allows the CPU to execute multiple independent processes or tasks concurrently, sharing the same processor and resources. On the other hand, multi-threading involves dividing a single process into multiple threads that can execute concurrently, sharing the same memory space and resources of the parent process.

| S.NO | Multitasking                                                 | Multithreading                                                      |
|------|-------------------------------------------------------------|---------------------------------------------------------------------|
| 1.   | Users can perform many tasks by CPU.                        | Many threads are created from a process, increasing computer power. |
| 2.   | Involves often CPU switching between tasks.                 | Involves often CPU switching between threads.                       |
| 3.   | Processes share separate memory.                            | Processes are allocated the same memory.                            |
| 4.   | Involves multiprocessing.                                   | Does not involve multiprocessing.                                   |
| 5.   | CPU executes many tasks at a time.                          | CPU executes many threads from a process at a time.                 |
| 6.   | Each process has separate resources.                        | Each process shares the same resources.                             |
| 7.   | Slower compared to multithreading.                          | Faster than multitasking.                                           |
| 8.   | Termination of a process takes more time.                   | Termination of a thread takes less time.                            |
| 9.   | Isolation and memory protection exist.                      | Isolation and memory protection do not exist.                       |
| 10.  | Helps in developing efficient programs.                     | Helps in developing efficient operating systems.                    |
| 11.  | Involves running multiple independent processes or tasks.   | Involves dividing a single process into multiple threads.           |
| 12.  | Multiple processes or tasks run simultaneously.             | Multiple threads within a single process run concurrently.          |
| 13.  | Each process has its memory space and resources.            | Threads share the memory space and resources of the parent process. |
| 14.  | Used to manage multiple processes and improve efficiency.   | Used to manage multiple processes and improve efficiency.           |
| 15.  | Examples: running multiple applications, servers on a network. | Examples: splitting a video encoding task, responsive UI in an app. |

# How do you handle the mouse events using java AWT. Explain.

In Java AWT (Abstract Window Toolkit), mouse events can be handled using two interfaces:

**1. MouseListener:** This interface is used to handle basic mouse events like mouse clicks, mouse enters (when the mouse cursor enters a component's area), mouse exits (when the mouse cursor exits a component's area), and mouse button releases.

**2. MouseMotionListener:** This interface is used to handle mouse motion events, such as mouse dragging (when the mouse is moved with a button pressed) and mouse movement (when the mouse is moved without any button pressed).

To use these interfaces, you need to implement their methods and attach the listener to the component you want to monitor for mouse events.

Here's a minimal example program that demonstrates how to handle mouse events using Java AWT:

```java
import java.awt.*;
import java.awt.event.*;

public class MouseEventsExample extends Frame implements MouseListener, MouseMotionListener {

    public MouseEventsExample() {
        addMouseListener(this);
        addMouseMotionListener(this);
        setSize(300, 200);
        setTitle("Mouse Events Example");
        setVisible(true);
    }

    public void mouseClicked(MouseEvent e) {
        System.out.println("Mouse Clicked at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mouseEntered(MouseEvent e) {
        System.out.println("Mouse Entered at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mouseExited(MouseEvent e) {
        System.out.println("Mouse Exited at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mousePressed(MouseEvent e) {
        System.out.println("Mouse Pressed at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mouseReleased(MouseEvent e) {
        System.out.println("Mouse Released at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mouseDragged(MouseEvent e) {
        System.out.println("Mouse Dragged at (" + e.getX() + ", " + e.getY() + ")");
    }

    public void mouseMoved(MouseEvent e) {
        System.out.println("Mouse Moved at (" + e.getX() + ", " + e.getY() + ")");
    }

    public static void main(String[] args) {
        new MouseEventsExample();
    }
}
```

In this example, we create a simple Java AWT Frame and implement both MouseListener and MouseMotionListener interfaces. We override their respective methods to print messages when various mouse events occur. The `main` method creates an instance of our custom class `MouseEventsExample`, and the program displays the frame. When you run the program and interact with the window using the mouse, you will see the corresponding messages in the console.

