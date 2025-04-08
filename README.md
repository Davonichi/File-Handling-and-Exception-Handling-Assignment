# File-Handling-and-Exception-Handling-Assignment
Description
File Read & Write Challenge 🖋️: Create a program that reads a file and writes a modified version to a new file.
Error Handling Lab 🧪: Ask the user for a filename and handle errors if it doesn’t exist or can’t be read.

# Step 1: Open the original file and read its content
with open("original.txt", "r") as original_file:
    content = original_file.read()

# Step 2: Modify the content (example: make it uppercase)
modified_content = content.upper()

# Step 3: Write the modified content to a new file
with open("modified.txt", "w") as modified_file:
    modified_file.write(modified_content)

print("File has been read, modified, and saved as 'modified.txt'.")


# Ask the user to enter a filename
filename = input("Enter the filename to read: ")

try:
    with open(filename, "r") as file:
        content = file.read()
        print("\nFile content:\n")
        print(content)

except FileNotFoundError:
    print("❌ Error: The file does not exist.")
except PermissionError:
    print("❌ Error: You do not have permission to read this file.")
except Exception as e:
    print(f"❌ An unexpected error occurred: {e}")
    
