#Logging in

![Login Window](../neuromoreStudio/Images/Basics/Login.png)

When starting neuromore Studio the first time, it will ask you for your user account and your password. Please enter either your e-mail address or your user account name and your password into the given fields and press 'Sign In'.

In case you want neuromore Studio to remember your login information for the next time, enable the 'Remember Me' checkbox before signing in. Your login information will be stored using AES256 encryption on your local disk.

You can sign out via the 'Help' menu entry 'Sign Out'. This will also destroy the encrypted login information on your local disk. Next time you start neuromore Studio you will be prompted to enter your login information again.

#Browsing examples

A good starting point are our example classifiers in the 'Back-End File System' window located on the right side. It is a hierarchical view with folders and files like in Windows Explorer or OSX Finder. Just click an item and it will open the classifier and show its graph.

![Create Personal Copy](../neuromoreStudio/Images/Classifier/CreatePersonalCopy.png)

The example classifiers are read-only files and you won't be able to change its graph. In case you want to modify an example and play around with it, right click the classifier item and select 'Create Copy In Personal Folder'. A new file will appear in your personal folder which is named the same way as your user id.

![Classifier Tools](../neuromoreStudio/Images/UI/Tool.png)

Use the tool icon in the classifier window to start editing the classifier. New nodes can be created via drag & drop from the 'Available Nodes'. Selecting a node will show up its attributes.