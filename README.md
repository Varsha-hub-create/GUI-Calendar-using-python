# GUI-Calendar-using-python

from tkinter import *
import calendar

def Calendar_See():
    try:
        get_year = int(year_entry.get())
        window = Toplevel(root)
        window.config(background="light pink")
        window.title(f"Calendar for {get_year}")
        window.geometry('920x860')

        window_content = calendar.calendar(get_year)
        year_cal = Label(window, text=window_content, font=("Courier", 10, "bold"), justify=LEFT, bg="light pink")
        year_cal.pack(padx=20, pady=20)

        close_button = Button(window, text="Close", command=window.destroy, bg="black", fg="white", font=("Arial", 12, "bold"))
        close_button.pack(pady=10)
    except ValueError:
        error_label.config(text="Please enter a valid year!")

if __name__ == '__main__':
    root = Tk()
    root.config(background="light blue")
    root.title("GUI Calendar")
    root.geometry("300x200")

    name = Label(root, text="Calendar", bg="pink", font=("Arial", 15, "bold"))
    name.grid(row=0, column=0, columnspan=2, pady=10)

    year = Label(root, text="Enter the year:", bg="pink", font=("Arial", 12, "bold"))
    year.grid(row=1, column=0, padx=10)

    year_entry = Entry(root, font=("Arial", 15, "bold"))
    year_entry.grid(row=1, column=1, padx=10)

    show_button = Button(root, text="Show Calendar", fg="red", bg="black", font=("Arial", 10, "bold"), command=Calendar_See)
    show_button.grid(row=2, column=0, columnspan=2, pady=10)

    error_label = Label(root, text="", bg="light blue", fg="red", font=("Arial", 10, "bold"))
    error_label.grid(row=3, column=0, columnspan=2)

    root.mainloop()

