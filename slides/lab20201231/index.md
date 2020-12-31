---
marp: true
title: Computer Programming 1 Lab - Lecture 14
date: 2020-12-31
paginate: true 
---
<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>
# Computer Programming 1 Lab
## 2020-12-31

---

# Outline
- Command line argument
- Stream
- Redirect
- Pipe
- File


---

# Command line argument
- Pass argument to main function from command line
- `args`: the number of command line argument 
- `argv`: an array of strings in which the actual command-line arguments are stored.
```bash
./a.out data1.in data2.in data3.in
->
args: 4
argv[0] = ./a.out
argv[1] = data1.in  
argv[2] = data2.in 
argv[3] = data3.in  

```
---

# Stream

### A “source” or “sink” of data.

## Common streams:

- FILE I/O
- Socket
- STDIN/STDOUT/STDERR

---
```c
FILE* file_1 = fopen(.......); 
FILE* file_2 = fopen(.......); 

fgets(str, sizeof(str), stdin);
fgets(str, sizeof(str), file_1); 

fputs(str, stdout); 
fputs(str, file_2); 

fprintf(stdout, ......); 
fprintf(stderr, ......); 
```
---

# Redirect

```
myprogram > output.txt 
myprogram 2> err.txt 
myprogram > output.txt 2> err.txt 
```
---
# Pipeline

- |

- Simply, '|' 

- Connecting multiple program procedures' stdout and stdin like a waterfall, like ONE stream. 

---
- Program_A: 
Prints 1 ~ 10 ascendingly 
- Program_B: 
Reads a number and multiply it by 2 

Than prints the result
`Program_A | Program_B`

---
<!-- 
  backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)"
-->
<style scoped>
  h1, h2, {
    color: #efefef;
  }
</style>
# <!--fit--> Any Question?
