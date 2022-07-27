# Alarm Clock

## Tools required

<img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue" />
<hr>

## About the project

> The objective of our project is to implement an alarm clock using Python. Python consists of some very innovative libraries such as datetime and tkinter which help us to build the project using the current date and time as well as to provide a user interface to set the alarm according to the requirement in 24-hour format.

<hr>

## Prerequisites

> This project requires good knowledge of Python and GUI (Graphic User Interface). Python when combined with Tkinter provides a fast and easy way to create GUI applications. Tkinter provides a powerful object-oriented interface to the Tk GUI toolkit. All the modules used need not be downloaded beforehand like the other libraries like NumPy, thus this project will be user friendly and accessible in any virtual environment used for python programming.

<hr>

## Project File Structure

`First, let’s check the steps to build an Alarm Clock program in Python`:

- Importing all the libraries and modules required.
- Putting forward a while loop which takes the argument of the time, the user wants to set the alarm on and automatically breaks when the time is up, with sound.
- Create a display window for user input.

Step by Step

1. ### First, we import all the necessary libraries and modules:

```Python
#Importing all the necessary libraries to form the alarm clock:
from tkinter import *
import datetime
import time
import winsound
```

> Explanation

- <b>Tkinter</b> module belongs to a standard library of GUI in Python. It helps us to create a dialog box with any information that we want to provide or get from the users.
- <b>Datetime</b> and time modules in python help us to work with the dates and time of the current day when the user is operating python and to manipulate it too.
- <b>Winsound</b> module provides access to the basic sound playing machinery provided by Windows platforms. This is useful to generate the sound immediately when a function is called.

2. ### Create a while loop:

```Python
def alarm(set_alarm_timer):
    while True:
        time.sleep(1)
        current_time = datetime.datetime.now()
        now = current_time.strftime("%H:%M:%S")
        date = current_time.strftime("%d/%m/%Y")
        print("The Set Date is:",date)
        print(now)
        if now == set_alarm_timer:
            print("Time to Wake up")
        winsound.PlaySound("sound.wav",winsound.SND_ASYNC)
        break
def actual_time():
    set_alarm_timer = f"{hour.get()}:{min.get()}:{sec.get()}"
    alarm(set_alarm_timer)
```

> Explanation

- Define a function named as <b>alarm()</b> which takes the argument of <b>(set_alarm_timer)</b>.It contains a while loop with a Boolean function True which makes the program automatic to work.
- <b>time.sleep(1)</b> halts the execution of the further commands given until we get the time value from the user later in the code and returns the background thread of the clock time going on at a regular interval.
- Get the current time using <b>current_time</b> which takes the argument of <b>datetime.datetime.now()</b>.
- now is used to print the time and date is used to print the current date by <b>string conversion</b> using <b>strftime()</b>.
- Define another function here named <b>actual_time()</b> which takes in the user value for setting the alarm in the string format. The same argument of </b>(set_alarm_timer)</b> as alarm before to execute the while loop which we further use while making GUI.
- If loop suggests that if the user input time </b>set_alarm_timer</b> matches with the while loop ongoing time now, the message is printed as” <b>Time to Wake up</b>”.
- <b>winsound.SND_ASYNC</b> plays the system generated sound as soon the condition satisfies, acting as a reminder for the alarm clock.

3. ### Creating GUI using tkinter:

```Python
clock = Tk()
clock.title("DataFlair Alarm Clock")
clock.geometry("400x200")

time_format=Label(clock, text= "Enter time in 24 hour format!", fg="red",bg="black",font="Arial").place(x=60,y=120)
addTime = Label(clock,text = "Hour  Min   Sec",font=60).place(x = 110)
setYourAlarm = Label(clock,text = "When to wake you up",fg="blue",relief = "solid",font=("Helevetica",7,"bold")).place(x=0, y=29)

# The Variables we require to set the alarm(initialization):
hour = StringVar()
min = StringVar()
sec = StringVar()

#Time required to set the alarm clock:
hourTime= Entry(clock,textvariable = hour,bg = "pink",width = 15).place(x=110,y=30)
minTime= Entry(clock,textvariable = min,bg = "pink",width = 15).place(x=150,y=30)
secTime = Entry(clock,textvariable = sec,bg = "pink",width = 15).place(x=200,y=30)

#To take the time input by user:
submit = Button(clock,text = "Set Alarm",fg="red",width = 10,command = actual_time).place(x =110,y=70)

clock.mainloop()
#Execution of the window.
```

> Explanation

- To Initialize tkinter, we pass a command under the name clock as <b>Tk()</b>.
- The dialog box has the title as DataFlair Alarm Clock with a geometry of (400\*200). We pass on the heading to mention the time format for 24 hours using <b>time_format</b>.
- The second heading is given above the user input boxes for the labeling to be “Hour Min Sec” using <b>addTime</b>.
- Just to make the dialog box look funkier, adding another label as “<b>when to wake you up</b>” using <b>setYourAlarm</b>.
- As we have already converted the current time in the string before (actual time), the variables we initialize for the user input dialog boxes are in <b>StringVar()</b>.
- Finally make the input boxes such as <b>hourTime</b>, </b>minTime</b>, and </b>secTime</b> which takes the entry of the time the user wants to set the alarm on in 24-hour format.
- Submit takes the command of the defined function <b>actual_time</b> and executes the clock as it acts as a set button to start the program.
- <b>Clock.mainloop()</b> is the basic and the last command was given to compile all the previous commands with their basic settings of color, font, width, axis, etc. and displays the window as soon as the program is run.

<hr>

> Yay!! The alarm clock is ready for execution for your next work nap 😉. Save the source code with main.py and run the file: `python3 main.py`
