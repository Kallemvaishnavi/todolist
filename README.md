# todolist


def show_todolist(todo_list):
    if len(todo_list) == 0:
        print("Your to-do list is empty!")
    else:
        print("\nTo-Do List:")
        for index, task in enumerate(todo_list, start=1):
            print(f"{index}. {task}")


def add_task(todo_list):
    task = input("Enter the task to add: ")
    todo_list.append(task)
    print(f"Task '{task}' has been added!")


def remove_task(todo_list):
    show_todolist(todo_list)
    try:
        task_num = int(input("Enter the number of the task to remove: "))
        if task_num > 0 and task_num <= len(todo_list):
            removed_task = todo_list.pop(task_num - 1)
            print(f"Task '{removed_task}' has been removed!")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

def todo_app():
    todo_list = []  

    while True:
        print("\nTo-Do List Application")
        print("1. Show To-Do List")
        print("2. Add Task")
        print("3. Remove Task")
        print("4. Exit")
        
        try:
            choice = int(input("Choose an option (1/2/3/4): "))
            if choice == 1:
                show_todolist(todo_list)
            elif choice == 2:
                add_task(todo_list)
            elif choice == 3:
                remove_task(todo_list)
            elif choice == 4:
                print("Exiting the To-Do List application.")
                break
            else:
                print("Invalid option! Please choose 1, 2, 3, or 4.")
        except ValueError:
            print("Please enter a valid number.")


if __name__ == "__main__":
    todo_app()
