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

## Ejericio 2 Metodo Middle

```
LinkedList.prototype.mitad = function() {
  let cont = 0;
  let nodo = this.head;
  let middle = Math.floor(this.size/2-1);
  while (nodo) {
    if (cont === middle) {
      if(this.size%2===0){
        return nodo;
      }
      return nodo.next
    }
    cont++;
    nodo = nodo.next;
  }
  return console.log("El arreglo es de tamano 1")
}
```
## Ejercicio 3 Metodo isBalanced
