# Setting up SSH  
Create a key: `ssh-keygen -t rsa -b 4096 -C "example@email.com"`  
Activate the key (make sure that you are using **bash**): `eval "$(ssh-agent -s)"`  
Insert this in *~/.ssh/config*:  
```  
Host *
 AddKeysToAgent yes
 IdentityFile ~/.ssh/id_rsa  
```  
Run the key: `ssh-add ~/.ssh/id_rsa`  
Go to GitHub (in the SSH and GPG Keys section) and create a new SSH key using the contents of the *id_rsa.pub* file  
**NOTE:** If you named your file something other than the default (*id_rsa*), then just use the name of your file
Check connection: `ssh -T git@github.com`  
  
# How to Pull Repository (using the Git method):  
`git clone <example_repository_goes_here>`  
  
# How to Push Changes (using the Git method):  
```  
cd <example_repository_goes_here>  
git add .
git commit -m "example comment to describe changes"
git push origin main  
```  
  
**NOTE:** If your branch is not named *main*, then use the name of your branch
**TIP:** Use `git commit -a` to be able to write multi-line comments! Just make sure that you set `git config --global core.editor <your_favourite_editor_goes_here>`
