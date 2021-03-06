+++
date = "2010-07-23"
title = "TDA Fila com Python"
tags = ["tda", "fila", "python"]
aliases = ["/2010/07/tda-fila-com-python"]
+++

O foco este post é levar você aprender computação com Python.
O TDA Fila é definido pelas seguintes operações:

`__init__`: Inicializar uma nova fila vazia
`insert`: Adicionar um novo item à fila
`remove`: Remover e retornar um item da fila. O item retornado é o que foi adicionado primeiro.
`isEmpty`: Checar se a fila está vazia

Segue abaixo um código para explica melhor a implementação `"TAD Fila"`.

```python
class Queue:
	def __init__(self):
		self.length = 0
		self.head = None

	def isEmpty(self):
		return (self.length == 0)

	def insert(self, cargo):
		node = Node(cargo)
		node.next = None
		if self.head == None:
			# if list is empty the new node goes first
			self.head = node
		else:
			# find the last node in the list
			last = self.head
			while last.next: last = last.next
			# append the new node
			last.next = node
			self.length = self.length + 1

	def remove(self):
		cargo = self.head.cargo
		self.head = self.head.next
		self.length = self.length - 1
		return cargo
```

Existem duas invariantes para um objeto Fila bem formado: o atributo length deve ser o número de nós na fila.

```python
from queue import Queue
start = new Queue()
start.insert(50)
start.insert(99)
start.insert(10)
while not start.isEmpty(): print start.remove()
```

> 50
> 99
> 10
