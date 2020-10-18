# Calculator

from  tkinter import *


class GUI:
    def __init__(self,parent):
        self.parent = parent
        self.processes = ""
        self.operations = ["+","-","×","÷"]
        self.initUI()
        

    def initUI(self):
        self.display = Label(height=3, width=42, bg="white",fg="red",font=("digital",10,"bold"), anchor=CENTER)
        self.display.place(x=5, y=7)
        self.ce_button = Button(text="CE",fg="red", width=16,height=2, bd=4, command=self.clear)
        self.ce_button.place(x=5, y=60)
        self.c_button = Button(text="C",fg="red", width=7, bd=4, height=2, command=self.clear)
        self.c_button.place(x=130, y=60)
        self.delete_button = Button(text="Backspace ⇽",fg="green", width=14, bd=4, height=2, command=self.delete)
        self.delete_button.place(x=194, y=60)
        self.seven_button = Button(text="7", width=7, bd=4, height=2, command=self.seven)
        self.seven_button.place(x=5, y=105)
        self.eight_button = Button(text="8", width=7, bd=4, height=2, command=self.eight)
        self.eight_button.place(x=68, y=105)
        self.nine_button = Button(text="9", width=7, bd=4, height=2, command=self.nine)
        self.nine_button.place(x=130, y=105)
        self.plus_button = Button(text="+", width=14,fg="red", bd=4, height=2, command=self.plus)
        self.plus_button.place(x=194, y=105)
        self.four_button = Button(text="4", width=7, bd=4, height=2, command=self.four)
        self.four_button.place(x=5, y=150)
        self.five_button = Button(text="5", width=7, bd=4, height=2, command=self.five)
        self.five_button.place(x=68, y=150)
        self.six_button = Button(text="6", width=7, bd=4, height=2, command=self.six)
        self.six_button.place(x=130, y=150)
        self.minus_button = Button(text="-", width=14,fg="red", bd=4, height=2, command=self.minus)
        self.minus_button.place(x=194, y=150)
        self.one_button = Button(text="1", width=7, bd=4, height=2, command=self.one)
        self.one_button.place(x=5, y=195)
        self.two_button = Button(text="2", width=7, bd=4, height=2, command=self.two)
        self.two_button.place(x=68, y=195)
        self.three_button = Button(text="3", width=7, bd=4, height=2, command=self.three)
        self.three_button.place(x=130, y=195)
        self.multiply_button = Button(text="×",fg="red", width=14, bd=4, height=2, command=self.multiply)
        self.multiply_button.place(x=194, y=195)
        self.coma_button = Button(text=".", width=7,fg="red", bd=4, height=2, command=self.coma)
        self.coma_button.place(x=5, y=240)
        self.zero_button = Button(text="0", width=7, bd=4, height=2, command=self.zero)
        self.zero_button.place(x=68, y=240)
        self.divide_button = Button(text="÷", width=7,fg="red", bd=4, height=2, command=self.divide)
        self.divide_button.place(x=130, y=240)
        self.equal_button = Button(text="=", width=14,fg="red", bd=4, height=2, command=self.equal)
        self.equal_button.place(x=194, y=240)
        
    def zero(self):
        self.processes += "0"
        self.display.config(text=self.processes)
    def one(self):
        self.processes += "1"
        self.display.config(text=self.processes)
    def two(self):
        self.processes += "2"
        self.display.config(text=self.processes)
    def three(self):
        self.processes += "3"
        self.display.config(text=self.processes)
    def four(self):
        self.processes += "4"
        self.display.config(text=self.processes)
    def five(self):
        self.processes += "5"
        self.display.config(text=self.processes)
    def six(self):
        self.processes += "6"
        self.display.config(text=self.processes)
    def seven(self):
        self.processes += "7"
        self.display.config(text=self.processes)
    def eight(self):
        self.processes += "8"
        self.display.config(text=self.processes)
    def nine(self):
        self.processes += "9"
        self.display.config(text=self.processes)
    def plus(self):
        self.processes += "+"
        self.display.config(text=self.processes)
    def minus(self):
        self.processes += "-"
        self.display.config(text=self.processes)
    def clear(self):
        self.processes = ""
        self.display.config(text=0)
    def ce(self):
        pass
    def divide(self):
        self.processes += "/"
        self.display.config(text=self.processes)
    def multiply(self):
        self.processes += "×"
        self.display.config(text=self.processes)
    def coma(self):
        self.processes += "."
        self.display.config(text=self.processes)
    def delete(self):
        self.pro = list(self.processes)
        self.pro.pop(-1)
        self.processes ="".join(self.pro)
        self.display.config(text=self.processes)
    def change(self):
        try:
            self.changed = int(self.processes) * (-1)
            self.processes = str(self.changed)
            self.display.config(text=self.processes)
        except Exception :
            self.display.config(text="Syntax error")
            self.processes=""
            
    def equal(self,*x):
        self.pro = list(self.processes)
        for i in range(len(self.pro)):
            if self.pro[i] == "×":
               self.pro[i] = "*"
        self.processes="".join(self.pro)
        self.processes = str(eval((self.processes)))
        if "." in self.processes :
            self.pro = self.processes.split(".")
            if self.pro[1] == "0" :
                self.processes = self.pro[0]
        self.display.config(text=self.processes) 
    
               
def main():

    root = Tk()
    root.title("Calculator")
    root.geometry("310x290")
    calculator = GUI(root)
    root.mainloop()
main()
