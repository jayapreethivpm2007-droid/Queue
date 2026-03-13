Queue with User Input Example

class Node:
    def __init__(self,data):
        self.data=data
        self.next=None

class Queue:
    def __init__(self):
        self.front=None
        self.rear=None

    def enqueue(self,data):
        new=Node(data)

        if self.rear==None:
            self.front=self.rear=new
            return

        self.rear.next=new
        self.rear=new

    def dequeue(self):
        if self.front==None:
            print("Queue Empty")
            return

        temp=self.front
        self.front=temp.next
        print("Removed:",temp.data)

    def display(self):
        temp=self.front
        while temp:
            print(temp.data,end=" ")
            temp=temp.next

q=Queue()

n=int(input("Enter number of elements: "))

for i in range(n):
    x=int(input("Enter element: "))
    q.enqueue(x)

print("Queue elements:")
q.display()

q.dequeue()

print("\nAfter deletion:")
q.display()

Output:
Enter number of elements: 3
Enter element: 5
Enter element: 10
Enter element: 15

Queue elements:
5 10 15
Removed: 5

After deletion:
10 15
