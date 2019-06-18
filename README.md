# tkvalidate
Validation functions that only allow integers or floats for tkinter Entry widgets

The validate functions are called with an entry widget as an argument. The following code will validate an entry so only
integers in the range -5 to 5 may be input. 

    import tkinter as tk

    root = tk.Tk()
    widget = tk.Entry(root, justify=tk.CENTER)
    widget.pack(padx=10, pady=10)
    int_validate(widget, from_=-5, to=5)
    root.mainloop()

This works on any subclass of Entry. For a ttk.Spinbox it can take the limits directly from the spinbox. The following
code accomplishes the same as the previous but with a spinbox.

    import tkinter as tk
    from tkinter import ttk

    root = tk.Tk()
    widget = ttk.Spinbox(root, justify=tk.CENTER, from_=-5, to=5)
    widget.pack(padx=10, pady=10)
    int_validate(widget)
    root.mainloop()

For validating floating points instead of integers, simply use float_validate instead