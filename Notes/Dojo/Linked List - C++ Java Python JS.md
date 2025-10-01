
# 🚀 C++ Implementation

```cpp
include <iostream>
using namespace std;

class Node {
public:
    int data;
    Node* next;
    Node* prev; // for doubly linked list

    Node(int val) {
        data = val;
        next = prev = nullptr;
    }
};

class LinkedList {
public:
    Node* head;

    LinkedList() { head = nullptr; }

    // Insert at end
    void append(int val) {
        Node* n = new Node(val);
        if (!head) { head = n; return; }
        Node* temp = head;
        while (temp->next) temp = temp->next;
        temp->next = n;
        n->prev = temp;
    }

    // Insert at beginning
    void insertAtBeginning(int val) {
        Node* n = new Node(val);
        if (!head) { head = n; return; }
        n->next = head;
        head->prev = n;
        head = n;
    }

    // Insert at index (doubly linked list)
    void insertAtIndex(int index, int val) {
        if (index == 0) { insertAtBeginning(val); return; }
        Node* temp = head;
        for (int i = 0; i < index - 1 && temp; i++) temp = temp->next;
        if (!temp) return;
        Node* n = new Node(val);
        n->next = temp->next;
        if (temp->next) temp->next->prev = n;
        temp->next = n;
        n->prev = temp;
    }

    // Pop last element
    void pop() {
        if (!head) return;
        if (!head->next) { delete head; head = nullptr; return; }
        Node* temp = head;
        while (temp->next) temp = temp->next;
        temp->prev->next = nullptr;
        delete temp;
    }

    // Reverse linked list
    void reverse() {
        Node* curr = head;
        Node* prevNode = nullptr;
        while (curr) {
            Node* nextNode = curr->next;
            curr->next = prevNode;
            prevNode = curr;
            curr = nextNode;
        }
        head = prevNode;
    }

    // Find middle node
    void findMiddle() {
        Node* slow = head;
        Node* fast = head;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }
        cout << "Middle Node: " << slow->data << endl;
    }

    // Sort linked list (Bubble Sort)
    void sortList() {
        if (!head) return;
        bool swapped;
        do {
            swapped = false;
            Node* temp = head;
            while (temp->next) {
                if (temp->data > temp->next->data) {
                    swap(temp->data, temp->next->data);
                    swapped = true;
                }
                temp = temp->next;
            }
        } while (swapped);
    }

    // Print list
    void print() {
        Node* temp = head;
        while (temp) {
            cout << temp->data << " ";
            temp = temp->next;
        }
        cout << endl;
    }
};

int main() {
    LinkedList ll;
    ll.append(3);
    ll.append(1);
    ll.append(4);
    ll.insertAtBeginning(9);
    ll.insertAtIndex(2, 7);
    ll.print();
    ll.findMiddle();
    ll.sortList();
    ll.print();
    ll.reverse();
    ll.print();
    ll.pop();
    ll.print();
    return 0;
}
```


# 🚀 Java Implementation

```java
class Node {
    int data;
    Node next, prev;
    Node(int d){
	    data = d;
	    next = prev = null;
		}
}

class LinkedList {
    Node head;

    void append(int val) {
        Node n = new Node(val);
        if (head == null) { 
	        head = n; 
	        return; 
	    }
        Node temp = head;
        while (temp.next != null){
			temp = temp.next;
			temp.next = n;
			n.prev = temp;
		}
    }

    void insertAtBeginning(int val) {
        Node n = new Node(val);
        if (head == null) { head = n; return; }
        n.next = head;
        head.prev = n;
        head = n;
    }

    void insertAtIndex(int index, int val) {
        if (index == 0) {
	        insertAtBeginning(val); 
	        return; 
	    }
        Node temp = head;
        for (int i = 0; i < index - 1 && temp != null; i++)temp = temp.next;
        if (temp == null) return;
        Node n = new Node(val);
        n.next = temp.next;
        if (temp.next != null) temp.next.prev = n;
        temp.next = n;
        n.prev = temp;
    }

    void pop() {
        if (head == null) return;
        if (head.next == null) { 
	        head = null; 
	        return;
	    }
        Node temp = head;
        while (temp.next != null) temp = temp.next;
        temp.prev.next = null;
    }

    void reverse() {
        Node curr = head, prev = null;
        while (curr != null) {
            Node next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }
        head = prev;
    }

    void findMiddle() {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }
        System.out.println("Middle Node: " + slow.data);
    }

    void sortList() {
        if (head == null) return;
        boolean swapped;
        do {
            swapped = false;
            Node temp = head;
            while (temp.next != null) {
                if (temp.data > temp.next.data) {
                    int t = temp.data;
                    temp.data = temp.next.data;
                    temp.next.data = t;
                    swapped = true;
                }
                temp = temp.next;
            }
        } while (swapped);
    }

    void print() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
        System.out.println();
    }
}

public class Main {
    public static void main(String[] args) {
        LinkedList ll = new LinkedList();
        ll.append(3);
        ll.append(1);
        ll.append(4);
        ll.insertAtBeginning(9);
        ll.insertAtIndex(2, 7);
        ll.print();
        ll.findMiddle();
        ll.sortList();
        ll.print();
        ll.reverse();
        ll.print();
        ll.pop();
        ll.print();
    }
}

```


# 🚀 Python Implementation

```python
class Node:
    def init(self, data):
        self.data = data
        self.next = None
        self.prev = None

class LinkedList:
    def init(self):
        self.head = None

    def append(self, val):
        n = Node(val)
        if not self.head:
            self.head = n
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = n
        n.prev = temp

    def insert_at_beginning(self, val):
        n = Node(val)
        if not self.head:
            self.head = n
            return
        n.next = self.head
        self.head.prev = n
        self.head = n

    def insert_at_index(self, index, val):
        if index == 0:
            self.insert_at_beginning(val)
            return
        temp = self.head
        for _ in range(index - 1):
            if not temp:
                return
            temp = temp.next
        if not temp:
            return
        n = Node(val)
        n.next = temp.next
        if temp.next:
            temp.next.prev = n
        temp.next = n
        n.prev = temp

    def pop(self):
        if not self.head:
            return
        if not self.head.next:
            self.head = None
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.prev.next = None

    def reverse(self):
        prev = None
        curr = self.head
        while curr:
            next_node = curr.next
            curr.next = prev
            prev = curr
            curr = next_node
        self.head = prev

    def find_middle(self):
        slow = self.head
        fast = self.head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        print("Middle Node:", slow.data)

    def sort_list(self):
        if not self.head:
            return
        swapped = True
        while swapped:
            swapped = False
            temp = self.head
            while temp and temp.next:
                if temp.data > temp.next.data:
                    temp.data, temp.next.data = temp.next.data, temp.data
                    swapped = True
                temp = temp.next

    def print_list(self):
        temp = self.head
        while temp:
            print(temp.data, end=" ")
            temp = temp.next
        print()

Example usage
ll = LinkedList()
ll.append(3)
ll.append(1)
ll.append(4)
ll.insert_at_beginning(9)
ll.insert_at_index(2, 7)
ll.print_list()
ll.find_middle()
ll.sort_list()
ll.print_list()
ll.reverse()
ll.print_list()
ll.pop()
ll.print_list()
```


# 🚀 JavaScript Implementation

```js
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
    this.prev = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  append(val) {
    let n = new Node(val);
    if (!this.head) {
      this.head = n;
      return;
    }
    let temp = this.head;
    while (temp.next) temp = temp.next;
    temp.next = n;
    n.prev = temp;
  }

  insertAtBeginning(val) {
    let n = new Node(val);
    if (!this.head) {
      this.head = n;
      return;
    }
    n.next = this.head;
    this.head.prev = n;
    this.head = n;
  }

  insertAtIndex(index, val) {
    if (index === 0) {
      this.insertAtBeginning(val);
      return;
    }
    let temp = this.head;
    for (let i = 0; i < index - 1 && temp; i++) temp = temp.next;
    if (!temp) return;
    let n = new Node(val);
    n.next = temp.next;
    if (temp.next) temp.next.prev = n;
    temp.next = n;
    n.prev = temp;
  }

  pop() {
    if (!this.head) return;
    if (!this.head.next) {
      this.head = null;
      return;
    }
    let temp = this.head;
    while (temp.next) temp = temp.next;
    temp.prev.next = null;
  }

  reverse() {
    let prev = null;
    let curr = this.head;
    while (curr) {
      let nextNode = curr.next;
      curr.next = prev;
      prev = curr;
      curr = nextNode;
    }
    this.head = prev;
  }

  findMiddle() {
    let slow = this.head, fast = this.head;
    while (fast && fast.next) {
      slow = slow.next;
      fast = fast.next.next;
    }
    console.log("Middle Node:", slow.data);
  }

  sortList() {
    if (!this.head) return;
    let swapped;
    do {
      swapped = false;
      let temp = this.head;
      while (temp && temp.next) {
        if (temp.data > temp.next.data) {
          [temp.data, temp.next.data] = [temp.next.data, temp.data];
          swapped = true;
        }
        temp = temp.next;
      }
    } while (swapped);
  }

  print() {
    let temp = this.head;
    let out = "";
    while (temp) {
      out += temp.data + " ";
      temp = temp.next;
    }
    console.log(out);
  }
}

// Example usage
let ll = new LinkedList();
ll.append(3);
ll.append(1);
ll.append(4);
ll.insertAtBeginning(9);
ll.insertAtIndex(2, 7);
ll.print();
ll.findMiddle();
ll.sortList();
ll.print();
ll.reverse();
ll.print();
ll.pop();
ll.print();

```
