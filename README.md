
from tkinter import *

class GUI :
    def __init__ (self,parent):
        self.parent=parent
        self.processes=""
        self.initUI()
        self.operations = ["+","-","×","÷"]
    
    def initUI(self):
        
        self.display = Label(height=2, width=28, bg="white",fg="blue",font=("digital",15,"bold"), anchor=CENTER)
        self.display.place(x=5,y=7)
        
        self.button_delete = Button(text="Backspace\n⇽",font=("times new roman",10,"bold"), bg="white",width=2, bd=4,padx=27,pady=7,activebackground="white",command=self.delete)
        self.button_delete.place(x=5,y=63)
        
        self.button_ce = Button(text="Ce",font=("times new roman",12,"bold"), bg="white",width=2, bd=4,padx=24,pady=11,activebackground="white",command=self.clear)
        self.button_ce.place(x=83,y=63)
        
        self.button_c = Button(text="C",font=("times new roman",12,"bold"), bg="white",width=4, bd=4,padx=17,pady=11,activebackground="white",command=self.clear)
        self.button_c.place(x=159,y=63)
        
        self.button_seven = Button(text="7\nseven",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=8,activebackground="white",command=self.seven)
        self.button_seven.place(x=5,y=120)

        self.button_eight = Button(text="8\neight",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=8,activebackground="white",command=self.eight)
        self.button_eight.place(x=82,y=120)

        self.button_nine = Button(text="9\nnine",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=27,pady=8,activebackground="white",command=self.nine)
        self.button_nine.place(x=159,y=120)

        self.button_four = Button(text="4\nfour",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=8,activebackground="white",command=self.four)
        self.button_four.place(x=5,y=180)
        
        self.button_five = Button(text="5\nfive",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=8,activebackground="white",command=self.five)
        self.button_five.place(x=82,y=180)

        self.button_six = Button(text="6\nsix",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=27,pady=8,activebackground="white",command=self.six)
        self.button_six.place(x=159,y=180)
        
        self.button_one = Button(text="1\none",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=7,activebackground="white",command=self.one)
        self.button_one.place(x=5,y=240)
        
        self.button_two = Button(text="2\ntwo",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=26,pady=7,activebackground="white",command=self.two)
        self.button_two.place(x=82,y=240)

        self.button_three = Button(text="3\nthree",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=27,pady=7,activebackground="white",command=self.three)
        self.button_three.place(x=159,y=240)

        self.button_zero = Button(text="0\nzero",font=("times new roman",10,"bold"),bg="white", width=6, bd=5,padx=50,pady=8,activebackground="white",command=self.zero)
        self.button_zero.place(x=5,y=298)
        
        self.button_coma = Button(text=".",font=("times new roman",10,"bold"), bg="white",width=2, bd=5,padx=27,pady=15,activebackground="white",command=self.coma)
        self.button_coma.place(x=159,y=299)

        self.button_divide = Button(text="/",font=("times new roman",15,"bold"), bg="white",width=4, bd=5,padx=24,pady=7,activebackground="white",command=self.divide)
        self.button_divide.place(x=239,y=63)

        self.button_multiply = Button(text="+",font=("times new roman",15,"bold"), bg="white",width=4, bd=5,padx=24,pady=8,activebackground="white",command=self.plus)        
        self.button_multiply.place(x=239,y=120)
        
        self.button_minus = Button(text="-",font=("times new roman",15,"bold"), bg="white",width=4, bd=5,padx=24,pady=8,activebackground="white",command=self.minus)
        self.button_minus.place(x=239,y=180)

        self.button_plus = Button(text="×",font=("times new roman",15,"bold"), bg="white",width=4, bd=5,padx=24,pady=8,activebackground="white",command=self.multiply)
        self.button_plus.place(x=239,y=240)

        self.button_equal = Button(text="=",font=("times new roman",15,"bold"), bg="white",width=4, bd=5,padx=24,pady=8,activebackground="white",command=self.equal)
        self.button_equal.place(x=239,y=299)
        
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
        try :
            self.pro.pop(-1)
        except Exception :
            self.display.config(text="Math error")
        self.processes ="".join(self.pro)
        self.display.config(text=self.processes)
    def change(self):
        # try:
        self.changed = int(self.processes) * (-1)
        self.processes = str(self.changed)
        self.display.config(text=self.processes)
        # except Exception :
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
    
    root=Tk()
    root.title("Simple Calculator")
    root.maxsize(width=351, height=362)
    root.minsize(width=351, height=362)
    calc = GUI(root)
    root.config(bg="sky blue")
    root.mainloop()
    
main()





