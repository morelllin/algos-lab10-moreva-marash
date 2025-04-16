# Лабораторная работа №10

## Задание

Разработать графический интерфейс для списка задач (TODO-листа) с возможностью добавления, удаления и выбора задач.

1. Создать окно приложения с заголовком "Мой TODO-лист" и фиксированным размером.

2. Добавить Listbox для отображения списка задач.

3. Добавить поле ввода (Entry) для ввода новой задачи.

4. Добавить кнопки:

    "Добавить" — добавляет задачу в список.
    "Удалить" — удаляет выбранную задачу.
    "Очистить всё" — полностью очищает список.

<img src="./.repo/todo.png" />

import tkinter as tk
root = tk.Tk() 
root.geometry("700x400")
root.configure(bg='#8A2BE2')
root.title("ПАША ТЕХНИК УМЕР") 
def delete_selected():
    selected = listbox.curselection()
    if selected:
        listbox.delete(selected[0])
def delete_all():
        listbox.delete(0, tk.END)
def add():
    if textbox.get():
        listbox.insert(0, textbox.get())

label = tk.Label(root, text="100 дел которые надо сделать до конца жизни", font=("Arial", 18), bg="#D8BFD8") 
label.pack(padx=20, pady=20,)
textbox = tk.Entry(root, font=("Arial", 16), bg="#D8BFD8")
textbox.pack()         
select_button = tk.Button(root, text="Добавить", command=add, bg="#483D8B")
select_button.pack()
listbox = tk.Listbox(root, width=50, height=10, bg="#D8BFD8" )
listbox.pack(pady=10)
listbox.insert(tk.END, "встать с кровати")
listbox.insert(tk.END, "почистить зубы")
listbox.insert(tk.END, "выучить питон с нуля за 8 часов")
listbox.insert(tk.END, "не покупать маленькой пиво")
listbox.insert(tk.END, "cходить на любимую алгоритмизацию")
delete_button = tk.Button(root, text="Удалить", command=delete_selected, bg="#483D8B")
delete_button.pack()
deleteall_button = tk.Button(root, text="Удалить всё", command=delete_all, bg="#483D8B")
deleteall_button.pack()

root.mainloop()
