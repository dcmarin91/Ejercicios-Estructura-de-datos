# Ejercicios Estrcuras de datos

## Ejercicio 1 Metodo Reverse

```
function LinkedList() {
  this.size = 0;
  this.head = null;
  this.tail = null;
}

function Node(val) {
  this.val = val;
  this.next = null;
}

LinkedList.prototype.add = function(val) {
  let nodo = new Node(val);
  if (!this.head) {
    this.head = nodo;
    this.tail = nodo;
    this.size++;
  } else {
    this.tail.next = nodo;
    this.tail = nodo;
    this.size++;
  }
  return nodo;
}

LinkedList.prototype.reverse = function() {
  var curr = this.head;
  var next = null;
  var prev = null;

  while(curr) {
    next = curr.next;

    curr.next = prev;

    prev = curr;

    curr = next;
  }
  this.head = prev;
}

var myLL = new LinkedList();
myLL.add(10);
myLL.add(30);
myLL.add(50);
myLL.reverse();
console.log(myLL);
```
