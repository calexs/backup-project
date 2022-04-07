# How to backup a repository with Git

# First of all: create an account on GitHub or GitLab

- You can simply create the account by accessing `GitHub` ([github.com](https://github.com)) or `GitLab` ([gitlab.com](http://gitlab.com)).
    - Either platform is free to use.
- After creating your account you need to generate your personal Key.
    - Go to your account settings:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled.png)
        
    
    - After you will go to the `archives` section and click on `Developer Settings`:
        
        Tip: it’s the last item of the column.
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%201.png)
        
    
    - Then click on the third option `Personal access tokens`:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%202.png)
        
    
    - You should now, see a list with all your personal access tokens from `GitHub` (In case you create an account on it):
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%203.png)
        
    
    - After this, generate a new token with `Generate new token` button
        - It’s needed to authenticate your account password, and then you should proceed to this page.
            
            ![Untitled](How%20to%20bac%20612bd/Untitled%204.png)
            
        - **Make sure to select the `repo` checkbox, to guarantee full control of the backup repository.**
    
    - When you’re done, you can generate the token:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%205.png)
        
    
    - This is your token, you can copy and save it
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%206.png)
        

# Second part: Initialize a new repository

- Now there is an important thing, you need to initialize a repository in both the Git platform (GitHub or GitLab as you may choose) and your local folder, that you pretend to backup the files.
    - So, for creating a new repository on GitHub, go to `your repositories` and select `new`:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled.png)
        
    - And on this page:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%207.png)
        
    - Then you will go to this page:
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%208.png)
        
    - Fill in the `Repository name` and you can also add a `Description`, but it’s optional
        
        ![Untitled](How%20to%20bac%20612bd/Untitled%209.png)
        
    - Depending on the case, you can check these boxes underneath the repository privacy, and initialize with some “pre-files”, like a `README`, a `.gitignore`, or a `LICENSE` file when it’s necessary. In a backup situation, you won’t need any “pre-file”, because it may cause conflict between local and remote archives.
    - Privacy also depends on the purpose of your project, but just in case, select `Private`.
    
- For the following step, you must get your repository code, so:
    
    ![Untitled](How%20to%20bac%20612bd/Untitled%2010.png)
    
    - Click on `Code` and select the `HTTPS` clone option. This will be your `remote` link.

- And for initializing in your local folder, that needs backup, you need access to a terminal to run the following commands:
    
    ```bash
    # Go into the folder
    cd (folder_name)
    
    # Initilize your repository
    git init
    
    # This specifies the name of the branch to "main"
    git branch -M main
    
    # Add the remote that will receive the backup
    git remote add origin (your_repository_link)
    
    # Since you want to backup, you can add all files as a single commit 
    git add .
    
    # Commit message example
    git commit -m "Just creating a backup"
    
    # Now go on and add your files to the remote
    git push -u origin main
    ```
    

- When you run the last command, the environment will ask for your `user_name`:
    
    ![Screenshot from 2022-04-07 11-46-22.png](How%20to%20bac%20612bd/Screenshot_from_2022-04-07_11-46-22.png)
    
    and then your `personal access token` to authenticate the session:
    
    ![Screenshot from 2022-04-07 11-46-39.png](How%20to%20bac%20612bd/Screenshot_from_2022-04-07_11-46-39.png)
    

- After these commands, you can see all the files of your project right in the Git platform that you chose.
    - For example:
        
        Access *[https://github.com/user_name/repository_name](https://github.com/user_name/repository_name)*
        
---
## Contributors
<p align="center">
    <a href="https://github.com/calexs/backup-project/graphs/contributors">
      <img src="https://contrib.rocks/image?repo=calexs/backup-project" />
    </a>
    <br>
    <a href="https://github.com/calexs">calexs</a>
</p>

## LICENSE
This project is licensed under the [GNU General Public License v3.0](LICENSE).
