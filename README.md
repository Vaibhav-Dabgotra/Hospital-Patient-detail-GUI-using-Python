# Hospital-Patient-detail-GUI-using-Python

def main():
    pass

if __name__ == '__main__':
    main()

from tkinter import *
import csv


HEIGHT=700
WIDTH=1200
bg_colour='white'
stus_bar_colour='#d9d9d9'
dr_name1='Pediatricians,\nDr. Satish Mehta \n        (M.S.,ENT )  \nMob.94xxxxxx15'
dr_name2='Geriatric ,\nDr. Deepak Mehta \n        (M.S.,Ortho)\nMob.94xxxxxx29'
dr_name3='Allergist,\nDr. Ashish Arora \n        (MBBS,Specialist)\nMob.78xxxxxx96'
dr_name4='Dermatologist,\nDr. Pratyoosh Anand \n       (Phd.,Python)\nMob.60xxxxxx85'
dr_name5='Infectious disease doctor,\nDr.Vaibhav Dabgotra\n    (MBBS)\nMob.90xxxxxx78'
dr_name6='Ophthalmologists,\nDr.Avnish Pathak\n     (Phd.)\nMob.97xxxxxx87'
dr_name7='Gynecologists,\n Dr.Ansh\n   (Phd.)\n Mob.98xxxxxx23'
dr_name8=' Women Specialist\n Dr.Arya\n (MBBS)\n Mob.87xxxxxx87'
dr_name10='Gastroenterologists\n Dr.Sunil\n (MBBS)\n Mob.878xxxxxx23'
dr_name11='Nephrologits\n Dr.Azhar\n (MBBS)\n Mob.12xxxxxx43'
dr_name12='Cardiologists,\n Dr.Dhoni\n        (Phd.)\n Mob.97xxxxxx65'
dr_name9='Endocrinologists\n Dr.Kalam\n (MBBS)\n Mob. 45xxxxxx89'
dr_name13='Urologist\n Dr.Aftab\n (MBBS)\n Mob.78xxxxxx23'
dr_name14='Pulmonologists\n Dr.Alam\n (MBBS)\n Mob. 45xxxxxx23'
dr_name15='Otolaryngologists\n Dr.Shah\n (MBBS)\n Mob.23xxxxxx12'
dr_name16='Neurologits\n Dr.Khan\n(MBBS)\n Mob.45xxxxxx12'
dr_name17='Psychiatrists\n Dr.Jahangir Khan\n (MBBS)\n Mob.34xxxxxx78'
dr_name18='Onchologists\n Dr.Ahmed\n (MBBS)\n Mob.23xxxxxx43'
dr_name19='Radiologits\n Dr.Singh\n (MBBS)\n Mob. 43xxxxxx23'
dr_name20='General Surgeon\n Dr.Tichkule\n (MBBS)\n Mob.67xxxxxx32'



class BookingSystem:

    def __init__(self, master):


        #menu function
        def menu_bar(lop):
            m_bar = Menu(lop)
            lop.config(menu= m_bar)

            submenu = Menu(m_bar)
            m_bar.add_cascade(label='Menu', menu=submenu)
            submenu.add_command(label='Refresh', command= '')
            submenu.add_command(label='Exit', command='')

            helpmenu = Menu(m_bar)
            m_bar.add_cascade(label='Help', menu=helpmenu)

        #stoe vale in excel sheet
        def store(e1, e2, e3, e4, e5, dr_n):
            list = [e1, e2, e3, e4, e5, dr_n]
            with open('hospital.csv', 'a') as f:
                w=csv.writer(f, dialect='excel')
                w.writerow(list)


        #second screen
        def stem(e1, e2, e3, e4, e5, dr_n):
            store(e1, e2, e3, e4, e5, dr_n)

            root_1 = Tk()

            canvas = Canvas(root_1 ,height=HEIGHT, width=WIDTH)
            canvas.pack()
            topframe = Frame(root_1, bg = bg_colour)
            topframe.place(relwidth = 1, relheight = 0.25)
            middleframe = Frame(root_1, bg = bg_colour)
            middleframe.place(rely = 0.25, relwidth = 1, relheight = 0.75)

            #second screen top frame
            heading = Label(topframe, text="AIIMS  Appointment  Booking", font=('arial 30 bold '),fg='black', bg=bg_colour)
            heading.place(relx = 0.1, relwidth = 0.6, relheight = 0.3)
            #photo = PhotoImage(file = 'hospital.png', width = 250)
            #photo_show = Label(topframe, image = photo)
            #photo_show.place(relx = 0.8, relwidth = 0.2, relheight = 0.7)
            dr = Label(topframe, text='%s' %(dr_n), font=('arial 14'), fg = 'steelblue', bg = bg_colour)
            dr.place(relx = 0.05, rely= 0.4)
            timing = Label(topframe, text='Timing:- Morning(10 a.m. to 1 p.m.)', font='arial 12', fg = 'steelblue', bg = bg_colour)
            timing.place(relx=0.68, rely=0.7, relwidth=0.3, relheight= 0.25)
            separator = Label(topframe, bg='#3399ff')
            separator.place(rely=0.99, relwidth=1, relheight=0.01)

            #second screen middle frame
            name = Label(middleframe, text="Patient Name : %s" %(e1), font=('arial 18 bold'), fg='black', bg=bg_colour)
            name.grid(row=0, column=0, sticky=W, pady=10,padx=20)
            age = Label(middleframe, text="Patient's Age : %s" %(e2), font=('arial 18 bold'), fg='black', bg=bg_colour)
            age.grid(row=1, column=0, sticky=W, pady=5, padx=20)
            disease = Label(middleframe, text="Disease : %s" %(e3), font=('arial 18 bold'), fg='black', bg=bg_colour)
            disease.grid(row=2,column=0, sticky=W, pady=5, padx=20)
            location=Label(middleframe, text="Address : %s" %(e4), font=('arial 18 bold'), fg='black', bg=bg_colour)
            location.grid(row=3,column=0, sticky=W,pady=5,padx=20)
            phone=Label(middleframe, text="Phone no. : %s" %(e5), font=('arial 18 bold'), fg='black', bg=bg_colour)
            phone.grid(row=4,column=0, sticky=W,pady=5,padx=20)

            #second screen no frame
            message = Label(root_1, text='Your appointment has been booked \n\n  Your appointment number:', font= 'arial 14')
            message.place(relx=0.2, rely=0.6, relwidth=0.6, relheight=0.2)

            ok = Button(root_1, text='OK', width=8, height=1, font = 'arial 12', fg = 'black', command=quit)
            ok.place(relx=0.69, rely=0.85)

            hd_copy = Button(root_1, text='Print', width=10, height=1, font = 'arial 12', fg = 'black', command=quit)
            hd_copy.place(relx=0.50, rely=0.85)

            #status bar 2
            self.status= Label(root_1, text="Task Completed                                                |       Modified       |   Insert   |  ",
              bg=stus_bar_colour, font= 'arial 10', anchor=W)
            self.status.place(rely=0.96 , relwidth = 1, relheight=0.04)

            root_1.mainloop()


        def root(dr_n):
            root_0 = Tk()

            #menu function call
            menu_bar(root_0)

            #first screen (canvas = size of screen)
            canvas = Canvas(root_0, height=HEIGHT, width=WIDTH)
            canvas.pack()

            #frames
            topframe = Frame(root_0, bg = bg_colour)
            topframe.place(relwidth=1, relheight=0.25)
            middleframe = Frame(root_0, bg = bg_colour)
            middleframe.place(rely=0.25, relwidth=1, relheight=0.50)
            lowerframe = Frame(root_0, bg = bg_colour)
            lowerframe.place(rely=0.75, relwidth=1, relheight=0.25)


            #first frame
            heading = Label(topframe, text="AIIMS  Appointment  Booking", font=('arial 30 bold '),fg='black', bg=bg_colour)
            heading.place(relx = 0.1, relwidth = 0.6, relheight = 0.3)
            #photo = PhotoImage(file = 'hospital.png', width = 250)
            #photo_show = Label(topframe, image = photo)
            #photo_show.place(relx = 0.8, relwidth = 0.2, relheight = 0.7)
            dr = Label(topframe, text='%s' %(dr_n), font=('arial 14'), fg = 'steelblue', bg = bg_colour)
            dr.place(relx = 0.05, rely= 0.4)
            timing = Label(topframe, text='Timing:- Morning(10 a.m. to 1 p.m.)', font='arial 12', fg = 'steelblue', bg = bg_colour)
            timing.place(relx=0.68, rely=0.7, relwidth=0.3, relheight= 0.25)

            separator = Label(topframe, bg='#3399ff')
            separator.place(rely=0.99, relwidth=2, relheight=1)

            #second frame
            name = Label(middleframe, text="Patient Name", font=('arial 18 bold'), fg='black', bg=bg_colour)
            name.grid(row=0, column=0, pady=10,padx=20)
            age = Label(middleframe, text="Patient's Age", font=('arial 18 bold'), fg='black', bg=bg_colour)
            age.grid(row=1, column=0, pady=5, padx=20)
            disease = Label(middleframe, text="Disease", font=('arial 18 bold'), fg='black', bg=bg_colour)
            disease.grid(row=2,column=0, sticky=E, pady=5, padx=20)
            location=Label(middleframe, text="Address", font=('arial 18 bold'), fg='black', bg=bg_colour)
            location.grid(row=3,column=0, sticky=E,pady=5,padx=20)
            phone=Label(middleframe, text="Phone no.", font=('arial 18 bold'), fg='black', bg=bg_colour)
            phone.grid(row=4,column=0, sticky=E,pady=5,padx=20)

            #Entry in second frame
            entry_1 = Entry(middleframe, width=60)
            entry_1.grid(row=0, column=1, ipady=6)
            entry_2 = Entry(middleframe, width=60)
            entry_2.grid(row=1, column=1, ipady=6)
            entry_3 = Entry(middleframe, width=60)
            entry_3.grid(row=2, column=1, ipady=6)
            entry_4 = Entry(middleframe, width=60)
            entry_4.grid(row=3, column=1, ipady=6)
            entry_5 = Entry(middleframe, width=60)
            entry_5.grid(row=4, column=1, ipady=6)


            #third frame
            submit = Button(lowerframe, text="Add Appointment", width=20, height=2, font = 'arial 12', fg = 'white', bg='steelblue',
              command=lambda:stem(entry_1.get(), entry_2.get(), entry_3.get(), entry_4.get(), entry_5.get(), dr_n))
            submit.place(relx=0.25, rely=0.3)
            back = Button(lowerframe, text="Exit", width=10, height=2, font = 'arial 12', fg = 'white', bg='steelblue')
            back.place(relx=0.55, rely=0.3)

            #status bar
            status= Label(lowerframe, text="Appointment Booking System                                                |       Modified       |   Insert   |  ",
              bg=stus_bar_colour, font= 'arial 10', anchor=W)
            status.place(rely=0.88 , relwidth = 1, relheight=0.12)

            root_0.mainloop()


        menu_bar(seed)

        #first screen (canvas = size of screen)
        self.canvas = Canvas(height=HEIGHT, width=WIDTH)
        self.canvas.pack()

        self.topframe_1 = Frame( bg = '#99cf45')
        self.topframe_1.place(relwidth=1, relheight=0.15)
        self.middleframe_1 = Frame(bg = '#ff9933')
        self.middleframe_1.place(rely=0.15, relwidth= 1, relheight= 0.85)

        self.heading = Label(self.topframe_1, text = 'Hi there...!, Hope you are not well...',anchor=W, fg= 'white', bg= '#006699', font= 'arial 24 ')
        self.heading.place(relx=0,rely=0.05, relwidth= 1, relheight= 1)

        self.photo = PhotoImage(file = 'img-1.png')
        self.photo_show = Label(self.topframe_1, image = self.photo)
        self.photo_show.place(relx = 0.8,rely=0.05, relwidth = 0.20, relheight = 1)

        but_colr='#006699'
        but_fclr='#e6ffff'
        self.butt_0 = Button(self.middleframe_1, text ='%s' %(dr_name1), command=lambda:root(dr_name1), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_0.grid(row=0, column=0, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_1 = Button(self.middleframe_1, text ='%s' %(dr_name2), command=lambda:root(dr_name2), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_1.grid(row=0, column=1, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_2 = Button(self.middleframe_1, text ='%s' %(dr_name3), command=lambda:root(dr_name3), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_2.grid(row=0, column=2, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_3 = Button(self.middleframe_1, text ='%s' %(dr_name4), command=lambda:root(dr_name4), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_3.grid(row=0, column=3, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_4 = Button(self.middleframe_1, text='%s' %(dr_name5), command=lambda:root(dr_name5), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_4.grid(row=0, column=4, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_5 = Button(self.middleframe_1, text='%s' %(dr_name6), command=lambda:root(dr_name6), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_5.grid(row=1, column=0, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_6= Button(self.middleframe_1, text='%s' %(dr_name7), command=lambda:root(dr_name7), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_6.grid(row=1, column=1, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_7=Button(self.middleframe_1, text='%s' %(dr_name8), command=lambda:root(dr_name8), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_7.grid(row=1, column=2, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_8=Button(self.middleframe_1, text='%s' %(dr_name9), command=lambda:root(dr_name9), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_8.grid(row=1, column=3, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_9=Button(self.middleframe_1, text='%s' %(dr_name10), command=lambda:root(dr_name10), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_9.grid(row=1, column=4, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_10=Button(self.middleframe_1, text='%s' %(dr_name11), command=lambda:root(dr_name11), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_10.grid(row=2, column=0,padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_11=Button(self.middleframe_1, text='%s'%(dr_name12), command=lambda:root(dr_name12), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_11.grid(row=2, column=1, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_12=Button(self.middleframe_1, text='%s'%(dr_name13), command=lambda:root(dr_name13), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_12.grid(row=2, column=2, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_13=Button(self.middleframe_1, text='%s'%(dr_name14), command=lambda:root(dr_name14), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_13.grid(row=2, column=3, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_14=Button(self.middleframe_1, text='%s'%(dr_name15), command=lambda:root(dr_name15), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_14.grid(row=2, column=4, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_15=Button(self.middleframe_1, text='%s'%(dr_name16), command=lambda:root(dr_name16), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_15.grid(row=3, column=0, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_16=Button(self.middleframe_1, text='%s'%(dr_name17), command=lambda:root(dr_name17), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_16.grid(row=3, column=1, padx=50, pady=40, ipady=6, ipadx=6)
        self.butt_17=Button(self.middleframe_1, text='%s'%(dr_name18), command=lambda:root(dr_name18), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_17.grid(row=3, column=2, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_18=Button(self.middleframe_1, text='%s'%(dr_name19), command=lambda:root(dr_name19), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_18.grid(row=3, column=3, padx=50, pady=30, ipady=6, ipadx=6)
        self.butt_19=Button(self.middleframe_1, text='%s'%(dr_name20), command=lambda:root(dr_name20), font = 'arial 14', bg=but_colr, fg=but_fclr)
        self.butt_19.grid(row=3, column=4, padx=50, pady=30, ipady=6, ipadx=6)



        #status bar
        self.status= Label(self.middleframe_1, text="  AIIMS Appointment Booking                                             |       33:58      |   Insert   |  ",
              bg=stus_bar_colour, font= 'arial 10', anchor=W)
        self.status.place(rely=0.97 , relwidth = 1, relheight=0.03)




seed = Tk()
b = BookingSystem(seed)
seed.mainloop()
