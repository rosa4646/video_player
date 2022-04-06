import tkinter as tk
from tkinter import *
import tkvideo
from tkvideo import *
import os

#creates the master window
root = Tk()
w = Label(root, text="video player :)")
root.geometry("500x500")

var = tk.StringVar()

#creates the listbox of videos
listbox = tk.Listbox(root)
mp4_list = os.listdir(r"D:\videos")
for file in mp4_list:
    listbox.insert(END, file)
listbox.pack()

#function for extracting the video name and playing it
def submit():
    global video_name
    global path
    video_name = var.get()
    var.set("")
    print(video_name)
    path = "D:\\videos\\" + video_name  
    print(path)
    video_player = tkvideo(path, 
            w,
            loop = 1,
            size = (200, 200)
    )
    video_player.play()

#entry box code
entry = tk.Entry(root, textvariable=var)
entry.pack()
btn = tk.Button(root, text="Play", 
                    command=submit)

#detects if the window is in focus, destroys the window if it isnt
focus = 0

def focus_in(event):
    global focus
    focus += 1

def focus_out(event):
    global focus
    focus -= 1
    if focus == 0:
        root.destroy()
        w.destroy()
        listbox.destroy()

root.bind("<FocusIn>", focus_in)
root.bind("<FocusOut>", focus_out)

btn.pack()
w.pack()
root.mainloop()
entry.pack()
