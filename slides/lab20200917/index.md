---
marp: true
title: Computer Programming 1 Lab - Lecture 1
date: 2020-09-17
paginate: true 
---

# Computer Programming 1 Lab
## 2020-09-17
---

# Rules - Assignments 
  - DO NOT CHEAT!
  - Both cheater and his partner will be punished.
  - Lock your assignment directory!
  - Discuss, BUT not copy.
  - Exercise will be announced in EVERY TA’s class.


--- 
# Rules - Mailing Convention 
  - Asking questions of TAs via e-mail
  - The subject of mail shall begin with **<span style="color:red;">[109cp1]</span>** and make it clear.
  - `Hi, my code doesn’t work` -----> (X) wrong subject.
  - `[109cp1] help!!` -----> (X) help what?
  - `[109cp1] for-loop did’t stop!` -----> (O) nice and clear !!
  - Include your signature
    - Remember to append your **studentID** and your **name** to the mail.

--- 
# Rules - Asking a Question in a Smart Way
### Before You Ask
- Try to find an answer by searching the archives of the FB Group or class resources.
- Try to find an answer by searching the Web.
- Try to find an answer by asking a skilled friend.
### When You Ask
- Use meaningful, specific subject headers
- Be explicit about your question
  - Have you tried any test? What problem you think you are facing?
  - **DON'T JUST PASTE YOUR CODE SNIPPETS.**
---
# Outline
- Basic Unix Command
- Basic Vim
- Lock directory
- Assignment
---
# Basic UNIX Command

0. Download [pietty](http://ntu.csie.org/~piaip/pietty/) **(Windows Only)**
1. Connect to `ghost.cs.nccu.edu.tw`
   **Windows**: Use Telnet first time, and use SSH afterwards.
   `telnet s109XX@ghost.cs.nccu.edu.tw`
   **MacOS**:
   `ssh s109XX@ghost.cs.nccu.edu.tw`
   > s109XX is your ID, the "XX" is the latest two digits of your StudentID
2. Enter your password 
   > It is normal for the password you entered not displaying on your window

---
# Basic UNIX Command

3. Change your password
  $ passwd
4. Activate your mail service
  $ elm
  then press 'y' three times and 'q' to finish
5. Setting your enviorment
  ```bash
  cp ~g10611/.profile . 
  cp ~g10611/.vimrc .  
  cp ~g10611/.bashrc .  
  exit
  ```
6. Connenct to `s109XX@ghost.cs.nccu.edu.tw` again **(Use SSH this time)**

---
# Basic UNIX Command
~   => your home directory 
~x => x’s home directory 
.    =>  current directory
..   =>  parent directory

**Absolute path**: Start with "/"

- /usr/share/bin
- /home1/student/stud107/s107xx

**Relative path**: Path relate to current directory.

- If current dir is /usr
  test/bin =>   /usr/test/bin
  li/public =>  /usr/li/public

---

# Basic UNIX Command

- `ls` list files in current directory.

```bash
ls
ls -l  # list files details in current directory.
ls -a  # list all files (include hidden files).
ls -la # Both of listing all files with details
```

---
# Basic UNIX Command

## How to create/delete/copy files or directories?

```bash
mkdir test 
# Create a directory named "test" in current directory
cp fileX dirY/dirZ
# Copy fileX from current directory to ./dirY/dirZ
cp fileX dirY/fileZ
# Copy fileX from current directory to dirY and rename to fileZ.
cp -r dirX dirY
# Copy dirX from current directory to dirY.
# If dirY doesn't exist, dirY is a copy of dirX.
# If dirY is a directory then there will be a copy of dirX under dirY.
```

---

# Basic UNIX Command

## How to create/delete/copy files or directories?

```bash
mv fileA dirB
# Move fileA to dirB.
mv dirA dirB
# If dirB exist, then move dirA under dirB.
# If dirB does not exist, dirA is rename to dirB.
rm fileA
# Remove file fileA (Only for file)
rm -r dirA
# Remove directory dirA and all its contents
```

---

# Basic UNIX Command - Your Round
1. Please create a directory named “1091cp1”
  `mkdir 1091cp1`
2. Enter directory 1091cp1
  `cd 1091cp1`
3. Please create a directory named `abc`
  `mkdir abc`
4. Please rename `abc` to `xyz`
  `mv abc xyz`
5. Copy `xyz` and rename it as `jqk`
  `cp -r xyz cdf`
7. Please delete directory `xyz` and `jqk`
  `rm -r xyz jqk`

---

# Basic UNIX Command - Recap

- Use `mkdir` to create a directory
- Use `mv` to move a directory/file or rename a directory/file
- Use `cp` to copy a file and `cp -r` to copy a directory
- Use `rm` for removing file and `rm -r` for removing directory

---

# Basic UNIX Command - Others

- The path used on cp, mv, rm, mkdir can be absolute path or relative path.
- Use `pwd` to see what the current directory is.
- Use `whoami` to see your account's name.
- Use `logout` to logout the system. (or you can press Ctrl+D either)
- Type `Ctrl+L` to clean your screen
- Remember, whenever you have problems using Unix, try "man" command.

```bash
man ls
man cp
```

> man stands for manual.

---

# Basic VIM

- Vim is a text editor that you can write texts, codes just like `記事本`
- To use it, you just need to type `vim` with a filename folowing it, e.g. `vim test.txt`
<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>
![VIM h:300 center](https://i.imgur.com/C0121Me.png)