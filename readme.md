from tkinter import *

root = Tk()
root.title("Converting Celsius to Fahrenheit")
width = 700
height = 200
screen_width = root.winfo_screenwidth()
screen_height = root.winfo_screenheight()
x = (screen_width / 2) - (width / 2)
y = (screen_height / 2) - (height / 2)
root.geometry("%dx%d+%d+%d" % (width, height, x, y))
root.resizable(0, 0)
root.config(bg="white")


def CelciusToFahren():
    FAHRENHEIT.set("")
    if CELCIUS.get() != "":
        FAHRENHEIT.set((float(CELCIUS.get()) * (9 / 5)) + 32)


def FahrenToCelcius():
    CELCIUS1.set("")
    if FAHRENHEIT1.get() != "":
        CELCIUS1.set((float(FAHRENHEIT1.get()) - 32) * (5 / 9))


CELCIUS = StringVar()
CELCIUS1 = StringVar()
FAHRENHEIT = StringVar()
FAHRENHEIT1 = StringVar()

Top = Frame(root, width=700, bd=1, relief=SOLID)
Top.pack(side=TOP)
BottomTitle = Frame(root, width=700, bd=1, relief=SOLID)
BottomTitle.pack(side=TOP, pady=10)
BottomForm = Frame(root, width=700, bg="white")
BottomForm.pack(side=TOP)
BottomLeft = Frame(BottomForm, width=250, bd=1, relief=SOLID)
BottomLeft.pack(side=LEFT)
BottomRight = Frame(BottomForm, width=250, bd=1, relief=SOLID)
BottomRight.pack(side=RIGHT, padx=10)

lbl_title = Label(Top, text="Converting Celsius to Fahrenheit", width=700, font=('arial', 18))
lbl_title.pack(fill=X)
lbl3 = Label(BottomLeft, text="Celcius To Fahrenheit", font=('arial', 12))
lbl3.grid(row=0, columnspan=5, column=0)
lbl4 = Label(BottomRight, text="Fahrenheit To Celcius", font=('arial', 12))
lbl4.grid(row=0, columnspan=5, column=0)
lbl_celcius = Label(BottomLeft, text="Celcius", font=(12))
lbl_celcius.grid(row=1, padx=5, pady=10)
lbl_celcius1 = Label(BottomRight, text="Celcius", font=(12))
lbl_celcius1.grid(row=1, column=3)
lbl_to2 = Label(BottomLeft, text="-")
lbl_to2.grid(row=1, column=2)
lbl_to3 = Label(BottomRight, text="-")
lbl_to3.grid(row=1, column=2)
lbl_fahrenheit = Label(BottomLeft, text="Fahrenheit", font=(12))
lbl_fahrenheit.grid(row=1, column=3)
lbl_fahrenheit1 = Label(BottomRight, text="Fahrenheit", font=(12))
lbl_fahrenheit1.grid(row=1, padx=5, pady=10)

celcius1 = Entry(BottomLeft, textvariable=CELCIUS, width=12)
celcius1.grid(row=1, column=1)
celcius2 = Entry(BottomRight, textvariable=CELCIUS1, width=12, state=DISABLED)
celcius2.grid(row=1, column=4, padx=5)
fahrenheit1 = Entry(BottomLeft, textvariable=FAHRENHEIT, width=12, state=DISABLED)
fahrenheit1.grid(row=1, column=4, padx=5)
fahrenheit2 = Entry(BottomRight, textvariable=FAHRENHEIT1, width=12)
fahrenheit2.grid(row=1, column=1)

btn3 = Button(BottomLeft, text="Convert", width=20, bg="white", command=CelciusToFahren)
btn3.grid(row=2, columnspan=5, column=0, pady=10)
btn4 = Button(BottomRight, text="Convert", width=20, bg="white", command=FahrenToCelcius)
btn4.grid(row=2, columnspan=5, column=0, pady=10)

if _name_ == '_main_':
    root.mainloop()
