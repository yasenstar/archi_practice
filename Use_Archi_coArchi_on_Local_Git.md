# Using Archi Tool (with coArchi plug-in) in a Local Git Server

Normally through coArchi workspace, we add or retrieve a Archi model from remote Git repository (github, Azure DevOps, etc.), you might ask why we need to do this via local Git server?

Simple answers, not only for fun, but also sometimes we just want to create private model for private using, utilizing any remote Git server involving _cloud_ into your route, Privacy people may not like that.

It may not exactly running like remote repository, but below steps I've referred from variable nice articles (thanks [godo.dev](https://www.godo.dev/), [Sergey Polezhaev](https://medium.com/@piteryo7/how-to-set-up-git-server-on-local-network-windows-tutorial-7ec5cd2df3b1)), below are the steps I've practiced and for your reference.

## Create a Local Git Server

If you have one another server running in your local network, that would be great, assume that is one Linux server with a host name as `localserver`, you can remotely connect that via ssh:

```
$ ssh [username]@localserver
```

Here, I'd like to go with even simpler way, no need other server, I'm using Windows 11 with Git 2.37.0, let's start to create Git server on the PC and connect that.

1. Come to one folder you like in Windows Explore, my sample is just `c:\temp`, where you want to initialize the Git server, Give it a name without spaces. I just create one `newgit` subfolder but you can just use the whatever folder your like.

    ![c-temp-folder](img/c-temp-folder.png)

2. Under `newgit`, right click the empty area and choose `Git Bash Here` to open git bash in this folder

    ![git-bash](img/git-bash-in-menu.png)

3. In Git Bash terminal, type

    ```
    git init testmodel.git --bare
    ```

    Note: you can try to name the folder without `.git` at the end, however, in some cases it leads to troubles.

    Now, you have your local Git Server, congratulation, and remember your Git server path, e.g. my sample is `c:\temp\newgit\testmodel.git`, you need this for Archi below.

## Configure User Name and Password

To connect Git from coArchi, you need fill in three information:

- URL
- User Name
- Password

    ![Archi New Model Repository Pop Up](img/Archi_New_Model_Repo_Empty.png)

You already have URL (saying the local Path on-hand from above step), you need to make other two.

Still in Git Bash, type

```
$ git config user.name "Your Name"
$ git config user.email "Your Email"
$ git config user.password "Password"
```

Note: here I don't have `--global` option as I just want those information are applying to this repository, not impact my others.

