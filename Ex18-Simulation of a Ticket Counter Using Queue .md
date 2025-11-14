# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)

## DATE:13.11.2025  

### Developed by
**Name:** Shanmuga Vasanth M

**Register Number:** 212223040191  

## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.

## Algorithm
1. Start the program.  
2. Create a `Node` class with `data` and `next` attributes.  
3. Implement a `Queue` class with `enqueue()` and `dequeue()` methods.  
4. Enqueue customers (represented by integers or names).  
5. Dequeue each customer in FIFO order as they are served.  
6. Display the queue before and after serving customers.  
7. Stop the program.  

## Program:
```java

class Node {
    String data;
    Node next;
    Node(String data) {
        this.data = data;
        this.next = null;
    }
}

class Queue {
    Node front, rear;
    
    void enqueue(String data) {
        Node newNode = new Node(data);
        if (rear == null) {
            front = rear = newNode;
            return;
        }
        rear.next = newNode;
        rear = newNode;
    }

    void dequeue() {
        if (front == null) {
            System.out.println("Queue is empty.");
            return;
        }
        System.out.println(front.data + " has been served.");
        front = front.next;
        if (front == null)
            rear = null;
    }

    void display() {
        if (front == null) {
            System.out.println("Queue is empty.");
            return;
        }
        Node temp = front;
        System.out.print("Current Queue: ");
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class TicketCounter {
    public static void main(String[] args) {
        Queue q = new Queue();
        q.enqueue("Alice");
        q.enqueue("Bob");
        q.enqueue("Charlie");
        q.enqueue("Diana");
        q.display();
        q.dequeue();
        q.display();
    }
}
```
## OUTPUT

<img width="950" height="125" alt="512030267-9d85a3e2-357d-4d62-ba4b-0241b85d7cc3" src="https://github.com/user-attachments/assets/d717f433-b7c0-4f66-91b1-8dfcf339e278" />

## RESULT
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
