# TIC TAC TOE
Tic-Tac-Toe Game in Python

To build tic-tac-toe game using python we require tkinter module and basic concept of python

Tkinter modules is a standard graphical user interface used to render graphics.

Tkinter.messagebox used to display message box
## Project File Structure
These are the step to build Tic-Tac-Toe game using python :
+ Import modules
+ Initialize window
+ Function to check result
+ Function to check the winner
+ Define labels and buttons

### 1. Import modules
      from tkinter import *
      import tkinter.messagebox as msg
      
### 2. Initialize window
     root = Tk()
     root.title('TIC_TAC_TOE')

     digits = [1,2,3,4,5,6,7,8,9]
     mark = ''
     count = 0
     panels = ["panel"] * 10
     
### 3. Function to check results
     # function check results
     def win(panels, sign):
         return ((panels[1] == panels[2] == panels[3] == sign)
                 or (panels[1] == panels[4] == panels[7] == sign)
                 or (panels[1] == panels[5] == panels[9] == sign)
                 or (panels[2] == panels[5] == panels[8] == sign)
                 or (panels[3] == panels[5] == panels[7] == sign)
                 or (panels[3] == panels[6] == panels[9] == sign)
                 or (panels[4] == panels[5] == panels[6] == sign)
                 or (panels[7] == panels[8] == panels[9] == sign))
                 
### 4. Function to check winer
     def checker(digit):
         global count, mark, digits
###### TH1         
         if digit == 1 and digit in digits:
             digits.remove(digit)
             if count % 2 == 0:
                 mark = 'X'
                 panels[digit] = mark
             elif count % 2 != 0:
                 mark = 'O'
                 panels[digit] = mark
             button1.config(text=mark)
            count = count + 1
            sign = mark
            
            if (win(panels, sign) and sign == 'X'):
                msg.showinfo("Result", "Player1 wins")
                root.destroy()
            elif (win(panels, sign) and sign == 'O'):
                msg.showinfo("Result", "Player2 wins")
                root.destroy()
 ##### TH2               
        if digit == 2 and digit in digits:
            digits.remove(digit)
            if count % 2 == 0:
                mark = 'X'
                panels[digit] = mark
            elif count % 2 != 0:
                mark = 'O'
                panels[digit] = mark
            button2.config(text=mark)
            count = count + 1
            sign = mark
            if (win(panels, sign) and sign == 'X'):
                 msg.showinfo("Result", "Player1 wins")
                 root.destroy()
            elif (win(panels, sign) and sign == 'O'):
                msg.showinfo("Result", "Player2 wins")
                root.destroy() 
                
##### TH3, TH4, TH5, ... TH9. 

### 5. Labels and Buttons
#### Labels
     Label(root, text="player1 : X", font="times 15").grid(row=0, column=1)
     Label(root, text="player2 : O", font="times 15").grid(row=0, column=2)
#### Buttons
     button1 = Button(root, width=15, height=7, font=('Times 16 bold'), command=lambda:checker(1))
     button1.grid(row=1, column=1)

     button2 = Button(root, width=15, height=7, font=('Times 16 bold'), command=lambda:checker(2))
     button2.grid(row=1, column=2)

     button3 = Button(root, width=15, height=7, font=('Times 16 bold'), command=lambda: checker(3))
     button3.grid(row=1, column=3)
##### ......

### finish
    root.mainloop()
## Output
![xo](https://user-images.githubusercontent.com/87347502/134285440-1dce2ecc-ce26-4411-b611-87e02a437047.png)
# Thank you!
