![Folders](https://github.com/user-attachments/assets/b9eba1f8-c09d-4d9c-8df2-22d1616dfc93)

> Automatically creates a new folder after a new folder is named.

1. A new folder is created without a name.
2. The new folder is automatically named.
3. Another new folder is created without a name.
4. The second new folder is automatically named.
5. Repeat step 1.	
6. Repeat step 2.
7. Repeat step 3.

#

```
import os

def create_new_folder(base_dir):
    # Get a list of all folders in the base directory
    folders = [folder for folder in os.listdir(base_dir) if os.path.isdir(os.path.join(base_dir, folder)]

    # Find the highest numbered folder
    max_num = 0
    for folder in folders:
        try:
            folder_num = int(folder)
            if folder_num > max_num:
                max_num = folder_num
        except ValueError:
            continue

    # Create a new folder with the next number
    new_folder_name = str(max_num + 1)
    new_folder_path = os.path.join(base_dir, new_folder_name)
    os.mkdir(new_folder_path)

    return new_folder_name

if __name__ == "__main__":
    base_directory = "./"  # Change this to the directory where you want to create the folders

    # Create the first folder
    create_new_folder(base_directory)
    print("Created the first folder.")

    # Create the second folder
    create_new_folder(base_directory)
    print("Created the second folder.")
```
Make sure to change the base_directory variable to the directory where you want to create the folders. This script will automatically name new folders with incremental numbers (e.g., 1, 2, 3, etc.) in the specified directory.

#
### Related Links

[Regulated_File_Manager](https://github.com/sourceduty/Regulated_File_Manager)

***
Copyright (C) 2024, Sourceduty - All Rights Reserved.
