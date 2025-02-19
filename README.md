# A02
How to use Git, GitHub, and VSCode. 

<h4>Step 1: Download Git</h4>
<ol>
    <li>Check if Git is installed by typing <code>git --version</code> in your terminal.</li>
    <li>Download Git <a href="https://git-scm.com/downloads">here</a> for your OS.</li>
    <ul>
        <li>For Windows, I recommend downloading <a href="https://gitforwindows.org/">Git Bash</a>.</li>
</ol>

<h4>Step 2: Set up GitHub and create a repository</h4>
<ol>
    <li>Log into <a href="https://github.com/">GitHub</a>. If you haven't already, make an account.</li>
    <li>Click the plus button on the top right and click "New repository". Give it a name.</li>
    <li>Change the repository to "Private". Compared to public repositories, which are accessible to everyone on the Internet, private repositories are only accessible to you and other people you give access to.</li>
    <li>Check "Add a README file". This will create the repository with a README file in it, which is a file where you can detail any important information about your project.</li> 
    <li>Now, click "Create Repository".</li>
    <li>Congratulations! You have successfully created your first repository!</li> 
</ol>

<h4>Step 3: Create an SSH key and connect to GitHub</h4>
<ol>
    <li>An SSH key allows you to connect your local machine to your GitHub account so that you do not need to sign in every single time. To create one, type <code>ssh-keygen -t ed25519 -C "example@email.com"</code> into your terminal. Replace "example@email.com with the email you use to log into GitHub.</li>
    <li>Your terminal should then prompt you with a file to save your key in. Type <code>/c/Users/"your name"/.ssh/"key name"</code>; replace "your name" with your user name and "key name" with whatever you want to name your key. You should see a randomly generated picture if the command worked.</li>
    <li>Now, find your public key. Enter <code>ls ~/.ssh</code>. Your terminal should return all of your keys.</li>
    <li>Enter <code>cat ~/.ssh/"key name".pub</code>. This should return a public key that starts with "ssh" and ends in your email address. Copy this.</li>
    <li>Go back to GitHub. Click on your profile picture in the top right corner, go to "Settings", and click on "SSH and GPG keys". Click "Add SSH key". Your title should be named appropriately and allow you to identify which machine the key is connected to. Paste the key you copied and click "Add SSH key".</li>
    <li>Now that you connected your SSH key, you need to add it to the SSH agent, which is a program that holds and manages your SSH keys. To start, enter <code>eval "$(ssh-agent -s)"</code> into your terminal.</li>
    <li>To add the private key that you made, enter <code>ssh-add ~/.ssh/"key name"</code> into your terminal. Remember, replace "key name" with the name of the key. 
    </li>
</ol>

<h4>Step 4: Clone a directory from GitHub</h4>
<ol>
    <li>You created your first repository on GitHub, but now you need to clone it to your local machine so you can edit files. In your terminal, navigate to whichever folder you want to clone your repository to using <code>cd</code>.</li>
    <li>Go back to your repository on GitHub. Click the green "Code" button on the top right and click "SSH". Copy the link.</li>
    <li>Enter <code>git clone "SSH URL"</code> and replace "SSH URL" with the one you copied.</li>
    <li>To check if the repo was successfully cloned, navigate into it using <code>cd "repo name"</code>.</li>
</ol>

<h4>Step 5: Set an SSH key for a repository</h4>
<ol>
    <li>Now that you have your repository and your SSH key, you need to link your SSH key to the repository. Navigate into your repository folder using <code>cd</code>.</li>
    <li>Enter your .git/config folder using <code>nano .git/config</code>.</li>
    <li>Add "sshCommand" under [core] and set it equal to "ssh -i ~/.ssh/"key name".</li>
</ol>

<h4>Step 6: Use VSCode with Git and GitHub</h4>
<ol> 
    <li>To practice using VSCode with Git and GitHub, we will practice editing the README.md file that you created with the repository. First, make sure that you have the GitHub extension installed on VSCode.</li>
    <li>In your file explorer, find your repository. Open your README.md file in VSCode.</li>
    <li>Enter a new line into the README file. Then save the file.</li>
    <li>On the left side of your screen, navigate to the "Source Control" tab.</li>
    <li>Under "Changes", stage the change that you just made by clicking the plus button. You should see that the change was moved to the "Staged Changes" tab. Staging a change means to add it to the list of changes that you want to commit. If you do not stage a change, it will not be committed.</li>
    <li>Enter a descriptive commit message and then press the blue Commit button.</li>
    <li>Press "Sync changes" to push the commit to your remote repository. Note that this will also pull any changes from your remote repository.</li>
</ol>



    


<br>
# Definitions
<ul>
    <li><strong>Branch:</strong> a version of the main repository isolated from the live version, where you can edit files without worrying about other branches.</li>
    <li><strong>Clone:</strong> copy a remote repository from GitHub locally onto a machine. After cloning, it is possible to edit files in the repository locally and sync changes onto the remote repository.</li>
    <li><strong>Commit:</strong> save edits made to files to whichever branch you are working on. Commits also save commit messages, which records what edits were made.</li>
    <li><strong>Fetch:</strong> downloads data from a remote repository without changing local files.</li>
    <li><strong>GIT:</strong> a version control system which captures edits made to files as "snapshots", hence allowing you to track changes.</li>
    <li><strong>Github:</strong> stores Git repositories on the cloud and allows you to access/manage them online.</li>
    <li><strong>Merge:</strong> combine data from two different branches into one.</li>
    <li><strong>Merge Conflict:</strong> happens when branches with incompatible commits are merged. A merge conflict is resolved by selecting which changes should be kept in the final merge.</li>
    <li><strong>Push:</strong> updates a remote repository with edits from the local branch you are currently working on.</li>
    <li><strong>Pull:</strong> updates the local branch that you are currently working on with changes on the remote repository.</li>
    <li><strong>Remote:</strong> a repository stored on the cloud, which is the repository that changes are pushed onto. Could also refer to a Git command which lets you view and manage tracked repositories.</li>
    <li><strong>Repository:</strong> where team members can store files and code. Also tracks changes to these files and code, so edits made by each team member can be tracked and managed. Can be made public through GitHub to allow for public access.</li>
</ul>

# Resources
<ul>
    <li><a href = "https://www.w3schools.com/git/git_branch.asp?remote=github">W3Schools: Git</a></li>
    <li><a href = "https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository">GitHub Docs: Cloning a repository</a></li>
    <li><a href = "https://www.youtube.com/watch?v=uEEcw1s_wWk">YouTube: "Git Fetch | What is Git Fetch and How to Use it | Learn Git"</a></li>
    <li><a href = "https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F">Git: Getting Started - What is Git?</a></li> 
    <li><a href = "https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts">GitHub Docs: About merge conflicts</a></li> 
    <li><a href = "https://github.com/git-guides/git-pull">Git Guides: Git Pull</a></li> 
    <li><a href = "https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories">GitHub Docs: About Repositories</a></li> 
    <li><a href = "https://code.visualstudio.com/docs/sourcecontrol/intro-to-git">Intro to Git</a></li> 
    <li><a href="https://lessons.ethereallab.app/general/Github#/">GitHub Version Control slides</a></li>



</ul>