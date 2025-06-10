# todo_list.py
A simple command-line To-Do List app made with Python. You can add, view, and delete tasks easily.
tasks = []

def show_menu():
    print("\n📝 To-Do List Menu:")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Delete Task")
    print("4. Exit")

while True:
    show_menu()
    choice = input("Enter your choice (1-4): ")

    if choice == '1':
        task = input("Enter a task: ")
        tasks.append(task)
        print("✅ Task added.")
    elif choice == '2':
        if not tasks:
            print("📭 No tasks found.")
        else:
            print("\nYour Tasks:")
            for idx, task in enumerate(tasks, start=1):
                print(f"{idx}. {task}")
    elif choice == '3':
        if not tasks:
            print("❌ No tasks to delete.")
        else:
            for idx, task in enumerate(tasks, start=1):
                print(f"{idx}. {task}")
            try:
                task_num = int(input("Enter task number to delete: "))
                if 1 <= task_num <= len(tasks):
                    removed = tasks.pop(task_num - 1)
                    print(f"🗑️ Task '{removed}' deleted.")
                else:
                    print("❗ Invalid task number.")
            except ValueError:
                print("❗ Please enter a valid number.")
    elif choice == '4':
        print("👋 Exiting the to-do list. Bye!")
        break
    else:
        print("❗ Invalid choice. Please enter a number from 1 to 4.")
