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

