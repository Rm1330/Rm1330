import os

def list_files(directory):
    print(f"Files in {directory}:")
    for filename in os.listdir(directory):
        print(filename)

def create_directory(directory):
    try:
        os.mkdir(directory)
        print(f"Directory '{directory}' created successfully.")
    except FileExistsError:
        print(f"Directory '{directory}' already exists.")

def main():
    current_directory = os.getcwd()

    while True:
        print("\n1. List Files")
        print("2. Create Directory")
        print("3. Exit")

        choice = input("Enter your choice (1/2/3): ")

        if choice == '1':
            list_files(current_directory)
        elif choice == '2':
            new_directory = input("Enter the name of the new directory: ")
            create_directory(new_directory)
        elif choice == '3':
            print("Exiting file manager.")
            break
        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    main()

