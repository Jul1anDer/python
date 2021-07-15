<h1 align="center">Task-2</h1>

<h3 align="left">Calculator</h3>
<p align="left">Create a window program in which to implement the basic functions of the calculator. (+, -, \, *). 
Implement additional functions in the program. (cos, sin, tan, ctg, log, ln,%)</p>

<p align="left">The appearance of the program on the operating system macos.</p>
<kbd>
    <img src="../Images/Task-2_1.png" width="700px" alt="Task-1">
</kbd>

<br>
<br>

<p align="left">1. Testing addition, subtraction, multiplication, division.</p>
<p align="left">1.1 Start</p>

<kbd>
  <br>
  <p align="center" width="100%">
    <img width="47%" src="../Images/Task-2_2.png" alt="Task-2">
    <img width="47%" src="../Images/Task-2_3.png" alt="Task-2">
  </p>
</kbd>

<br>
<br>

<p align="left">1.2 Complete example:</p>
<kbd>
    <img width="700px" src="../Images/Task-2_4.png" alt="Task-2">
</kbd>

<br>
<br>

<p>Result:</p>
<kbd>
    <img width="700px" src="../Images/Task-2_5.png" alt="Task-2">
</kbd>

<br>
<br>

<p align="left">2. An example of testing trigonometric functions:</p>
<p align="left">Take Sin 56° = -0.521551002086912</p>

<kbd>
    <img width="700px" src="../Images/Task-2_6.png" alt="Task-2">
</kbd>

<br>
<br>

<p>Result:</p>
<kbd>
    <img width="700px" src="../Images/Task-2_7.png" alt="Task-2">
</kbd>

<br>
<br>

<p align="left">3. Converting a number to binary:</p>
<p align="left">For example 5 = 00000101</p>

<kbd>
  <br>
  <p align="center" width="100%">
    <img width="47%" src="../Images/Task-2_8.png" alt="Task-2">
    <img width="47%" src="../Images/Task-2_9.png" alt="Task-2">
  </p>
</kbd>

### Example

```python
from tkinter import *
import math

win = Tk()
win.geometry("533x430")
win.resizable(0, 0)
win.title("Calculator")

def btn_click(item):
    global expression
    expression = expression + str(item)
    input_text.set(expression)

    def bt_clear(): 
    global expression 
    expression = "" 
    input_text.set("")
  
def bt_equal():
    global expression
    result = str(eval(expression))
    input_text.set(result)
    expression = ""


def func_cos():
    global expression
    input_text.set(math.cos(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_sin():
    global expression
    input_text.set(math.sin(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_tan():
    global expression
    input_text.set(math.tan(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_ctan():
    global expression
    input_text.set(math.ctg(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_log():
    global expression
    input_text.set(math.log(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_ln():
    global expression
    input_text.set(math.ln(int(expression)) if expression.isdecimal() else 'error')
    expression = ""
 
def func_pt():
    global expression
    input_text.set(float(expression)/100 if expression.isdecimal() else 'error')
    expression = ""
 
def to_bin():
    global expression
    input_text.set(bin(int(expression))[2:].zfill(8) if expression.isdecimal() else 'error')
    expression = ""
 
expression = ""
input_text = StringVar()
 
input_frame = Frame(win, width=312, height=50, bd=0, highlightbackground="#fff", highlightcolor="#fff", highlightthickness=1)
input_frame.pack(side=TOP)
 
input_field = Entry(input_frame, font=('calibri', 20, 'bold'), textvariable=input_text, width=50, bg="#fff", bd=0, justify=RIGHT)
input_field.grid(row=0, column=0)
input_field.pack(ipady=20)

btns_frame = Frame(win, width=312, height=272.5, bg="#fff")
btns_frame.pack()
 
clear = Button(btns_frame, text = "C", fg = "black", width = 32, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: bt_clear()).grid(row = 0, column = 0, columnspan = 3, padx = 1, pady = 1)
divide = Button(btns_frame, text = "/", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: btn_click("/")).grid(row = 0, column = 3, padx = 1, pady = 1)
f_cos = Button(btns_frame, text = "cos", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_cos()).grid(row = 0, column = 4, padx = 1, pady = 1)
f_ln = Button(btns_frame, text = "ln", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_ln()).grid(row = 0, column = 5, padx = 1, pady = 1)

seven = Button(btns_frame, text = "7", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(7)).grid(row = 1, column = 0, padx = 1, pady = 1)
eight = Button(btns_frame, text = "8", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(8)).grid(row = 1, column = 1, padx = 1, pady = 1)
nine = Button(btns_frame, text = "9", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(9)).grid(row = 1, column = 2, padx = 1, pady = 1)
multiply = Button(btns_frame, text = "*", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: btn_click("*")).grid(row = 1, column = 3, padx = 1, pady = 1)
f_sin = Button(btns_frame, text = "sin", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_sin()).grid(row = 1, column = 4, padx = 1, pady = 1)
f_pt = Button(btns_frame, text = "%", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_pt()).grid(row = 1, column = 5, padx = 1, pady = 1)
 
four = Button(btns_frame, text = "4", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(4)).grid(row = 2, column = 0, padx = 1, pady = 1)
five = Button(btns_frame, text = "5", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(5)).grid(row = 2, column = 1, padx = 1, pady = 1)
six = Button(btns_frame, text = "6", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(6)).grid(row = 2, column = 2, padx = 1, pady = 1)
minus = Button(btns_frame, text = "-", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: btn_click("-")).grid(row = 2, column = 3, padx = 1, pady = 1)
f_tan = Button(btns_frame, text = "tan", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_tan()).grid(row = 2, column = 4, padx = 1, pady = 1)
f_bin = Button(btns_frame, text = "bin", fg = "gray", width = 7, height = 13, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: to_bin()).grid(row = 2, column = 5, rowspan = 4, padx = 1, pady = 1)
 
one = Button(btns_frame, text = "1", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(1)).grid(row = 3, column = 0, padx = 1, pady = 1)
two = Button(btns_frame, text = "2", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(2)).grid(row = 3, column = 1, padx = 1, pady = 1)
three = Button(btns_frame, text = "3", fg = "black", width = 10, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(3)).grid(row = 3, column = 2, padx = 1, pady = 1)
plus = Button(btns_frame, text = "+", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: btn_click("+")).grid(row = 3, column = 3, padx = 1, pady = 1)
f_ctan = Button(btns_frame, text = "ctan", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_ctan()).grid(row = 3, column = 4, padx = 1, pady = 1)
 
zero = Button(btns_frame, text = "0", fg = "black", width = 21, height = 4, bd = 0, bg = "#fff", cursor = "hand2", command = lambda: btn_click(0)).grid(row = 4, column = 0, columnspan = 2, padx = 1, pady = 1)
point = Button(btns_frame, text = ".", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: btn_click(".")).grid(row = 4, column = 2, padx = 1, pady = 1)
equals = Button(btns_frame, text = "=", fg = "black", width = 10, height = 4, bd = 0, bg = "#eee", cursor = "hand2", command = lambda: bt_equal()).grid(row = 4, column = 3, padx = 1, pady = 1)
f_log = Button(btns_frame, text = "log", fg = "gray", width = 7, height = 4, bd = 0, bg = "#e37b19", cursor = "hand2", command = lambda: func_log()).grid(row = 4, column = 4, padx = 1, pady = 1)
win.mainloop()
```
