# MergeAndBranchLab
for CS 170/270
By Brenna Baker

	This lab will give you some practice in collaborating with other people on the same files. We are all going to work off the same repository for this lab, so the more people that participate in lab, the more helpful it will be to see the power of git. 

Ask Brenna to to add you as a collaborator (either ask me in person during lab, or if you want to do this lab at home, email me your github username) 

Navigate to the MergeAndBranchLab repository, which should now be available as one of your repositories. 

Click the clip board icon next to the https address of the repository. This copies the https address into your clipboard.

In Terminal, navigate to your Desktop ($ cd ~/Desktop) and then run the following command and paste in the https address from your clipboard. 
$git clone ‘pasted https address’

This should create a folder on your desktop called MergeAndBranchLab. 
What you have just done is cloned the repository. When you clone a repository, it means that any changes you make are meant to be shared with the other people who have cloned the repository. 
		This is different than forking. Forking means you want a copy of the repository to work on, but you don’t necessarily want or expect other people with access to that repository to see or use your changes.

Inside of MergeAndBranchLab is a file called SoftwareEngineeringLab.rb. Open the file and add a line below the existing line such as puts "My name is ‘Insert Name’ and I added this line to this file”

Now also create a second ruby file in your favorite text editor and add something to it. Mine is called BrennasFile.rb	

In command line, cd into MergeAndBranchLab. 
	Add the files to staging using the command  
	
$git add . 

The “.” means add all the files inside the MergeAndBranchLab directory for staging. 

Now commit your files using your name in your commit message
$git commit -m “YourName's commit”
You’ll get a little message that tells you that you are working on the master branch, 	how many files you changed, and a little information about what types of changes were 		made. 




Finally, push your changes to master so everyone can see them. Run the following command and complete the prompts for your Github username and password: 
$ git push origin master

Refresh Github and you’ll see the changes you made along with your commit message!

Merge Conflicts

Merge conflicts occur when the code in two branches is combined (merged) but they have conflicting code. You may encounter conflicts often if you are working on the same files as many other people. In this portion of the lab, we will learn how to solve merge conflicts. 

Go back to your Github repository page and create a new branch by clicking on the branch button. Name your new branch after yourself.
Branches are useful when many people will be working on the same file. It allows you to track which changes you are making in comparison to another person’s changes. 

If you two make changes that contradict one another, such as I say var = 4 while you say var = 15, then you can see before pushing to the master copy that you two have different ideas about how to write the code. Then, you can resolve the conflict and agree that really var1 should be equal to 3. 

Open MergeTest.rb inside of MergeAndBranchLab and change the line to read puts "I am practicing with branches”


 Now run 

$git add MergeTest.rb 

to add just the changed file. Recall that last time we used “add .”  to add all files. Also commit the file, but don’t push just yet!

Now let’s try making a change to a file. First switch from the Master Branch to your branch using 
$ git checkout -b YOURBRANCHNAME

Go back to your local copy of the files and open the MergeTest.rb file. Replace the line with puts “I am in YOURNAME branch”	
	Add that file and commit. 

 Now switch back to the master branch with $ git checkout master. 

 One more time, open the MergeTest.rb file and now change the line to “I am in the master branch”

Add, commit, and finally, run
$ git merge YOURBRANCHNAME

You will get an error that looks like this telling you there is a merge conflict:





Open up MergeTest.rb and you will find that some text has been added:



 <<<<<<<<     and >>>>>>>  surround areas with conflicts. 

The ====== shows you the different conflicting versions. Above the line, you see the code as it is in your master branch, and below the line you see the code as it is in your personal branch.

At this point, we must resolve the conflict.  This involves deleting all the extra symbols that have been added to your file and also choosing which of these lines we want our code to actually contain. When resolving conflicts, git will allow you could keep one, combine them, or replace them both with an entirely new line. I’d like you to restore the branch to its original state by replacing everything with 

puts “Hello” 

 Add your file, commit, and run the merge command again to reset the master copy. 
