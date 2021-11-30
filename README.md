+from tkinter import *

root = Tk()
root.title("Body Mass Index")
root.geometry("550x380+0+0")

frame1 = Frame(root, pady=10, bd=16)
frame1.grid()

weight = StringVar()
height = StringVar()
result = StringVar()

frame2 = Frame(frame1, width=550, height=190, pady=10, bd=16, relief="sunken")
frame2.grid(row=0, column=0)

frame3 = Frame(frame1, width=550, height=190, pady=10, bd=16, relief="sunken")
frame3.grid(row=1, column=0)
frame4 = Frame(frame1, width=550, height=190, pady=10, bd=16, relief="sunken")
frame4.grid(row=0, column=1)

lblweight = Label(frame2, text='Enter your weight', bd=12)
lblweight.grid(row=0, column=0)

lblweight = Entry(frame2, textvariable=weight, bd=12)
lblweight.grid(row=0, column=1)

lblkg = Label(frame2, text='kg', bd=12)
lblkg.grid(row=0, column=2)

lblheight = Label(frame2, text='Enter your height', bd=12)
lblheight.grid(row=1, column=0)

lblheight = Entry(frame2, textvariable=height, bd=12)
lblheight.grid(row=1, column=1)


lblcm = Label(frame2, text='cm', bd=12)
lblcm.grid(row=1, column=2)

lblresult = Label(frame2, text='Show Result(BMI)', bd=12)
lblresult.grid(row=2, column=0)

lblresult = Entry(frame2, textvariable=result, bd=12)
lblresult.grid(row=2, column=1)

lbltext = Label(frame4, text='underweight=<18.5', bd=12)
lbltext.grid(row=3, column=0)

lbltext = Label(frame4, text='normal range = 18.5-24.9', bd=12)
lbltext.grid(row=4, column=0)

lbltext = Label(frame4, text='overweight=25-29.9', bd=12)
lbltext.grid(row=5, column=0)

lbltext = Label(frame4, text='obesity = BMI of 30 or greater', bd=12)
lbltext.grid(row=6, column=0)


def add():
    f = float(lblweight.get())
    s = float(lblheight.get()) / 100  # cm convert into meater
    a = f / (s * s)
    b = round(a, 2)
    result.set(b)


def Rest():
    weight.set("")
    height.set("")
    result.set("")


def Exit():
    root.destroy()


btnTotal = Button(frame3, text='Total', bd=12, pady=12, width=8, command=add)
btnTotal.grid(row=0, column=0)

btnReset = Button(frame3, text='Reset', bd=12, pady=12, width=8, command=Rest)
btnReset.grid(row=0, column=1)

btnExit = Button(frame3, text='Exit', bd=12, pady=12, width=8, command=Exit)
btnExit.grid(row=0, column=2)

root.mainloop()
