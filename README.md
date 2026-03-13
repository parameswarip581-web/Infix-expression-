# Infix-expression-
Practice program 
class Stack:
    def __init__(self):
        self.items = []
def push(self, item):   
self.items.append(item)
    def pop(self):
        if self.items:
            return self.items.pop()
        return None
    def peek(self):
        if self.items:
            return self.items[-1]
        return None
    def is_empty(self):
        return len(self.items) == 0
def evaluate(expression):
    values = Stack()
    ops = Stack()
    i = 0
    while i < len(expression):
        if expression[i] == ' ':
            i += 1
            continue
if expression[i].isdigit():
            val = 0
            while i < len(expression) and expression[i].isdigit():
                val = val * 10 + int(expression[i])
                i += 1
            values.push(val)
        else:
            while not ops.is_empty():
                op = ops.pop()
                val2 = values.pop()
                val1 = values.pop()
                if op == '+':                   
values.push(val1 + val2)
                elif op == '-':                   
values.push(val1 - val2)          
ops.push(expression[i])
            i += 1
    while not ops.is_empty():
        op = ops.pop()
        val2 = values.pop()
        val1 = values.pop()
        if op == '+':
            values.push(val1 + val2)
        elif op == '-':
            values.push(val1 - val2)
    return values.pop()
expr = "10 + 5 - 3"
print "Expression:", expr
print "Result:", evaluate(expr)
OUTPUT:
Expression: 10 + 5 - 3
Result: 12
