---
marp: true
title: Computer Programming 1 Lab - Lecture 7
date: 2020-10-29
paginate: true 
---

# Computer Programming 1 Lab
## 2020-10-29
Chang, Chi-Hung

---

# Outline
- OJ-CLI
- Array
    - Sort Array
    - Search in Array
- Pointer
- const
- Exercise 6

---

# [OJ-CLI](https://github.com/josix/oj-cli)

---

# OJ-CLI
**Installation**
- Ghost Server
    ```bash
    echo 'export PATH="~f103207425/.local/bin:$PATH"' >> ~/.profile
    source ~/.bashrc
    ```
- Install from Source Code
    1. Clone this project
        ```bash
        git clone https://github.com/josix/oj-cli.git
        ```
    2. Update `HOST` variable value in file `oj-cli/constants.py` to the OnlineJudge URL you accessing
    3. Update Shebang(`#!/opt/csw/bin/python2.7`) value to a suitable one in `oj.py`

---

# OJ-CLI
**Commands**
- `oj login`
    - Use `oj login` to login to the account in OnlineJudge. It required you to enter your account information so that `oj-cli` could access OnlineJudge service successfully. After entering your username and password. `oj-cli` will respond if you login successfully or not.
    ```bash
    $ oj login
    Username:
    Password:
    ```

---

# OJ-CLI
**Commands**
- `oj get_assign <assign_no>`
    - Use `oj get_assign <assign_no>` to download the latest assignment from contest. The downloaded files are stored in folder `hwX` or `exX`. The folder includes testing data, output data, and template C script, which are named as `1.in`, `1.out`, and `hwX.c`(or `exX.c`) separately.
    ```bash
    $ oj get_assign hw2
    $ oj get_assign ex2
    ```

---

# OJ-CLI
**Commands**
- `oj submit <assign_no> <code_file>`
    - Use oj `submit <assign_no> <code_file>` to submit your code to contest.
    ```bash
    $ oj submit hw2 hw2.c
    $ oj submit ex3 ../ex3.c
    ```

---

# Array
- Sort Array
- Search in Aray

---

# Array
- Sort Array
[**Bubble sort**](https://www.youtube.com/watch?v=JP5KkzdUEYI)
    ```c
    int SIZE = 5;
    int array[SIZE] = {2, 3, 5, 1, 4};
    for(int i = 0 ; i < SIZE ; i++){
        for(int j = i + 1 ; j < SIZE ; j++){
            if(array[i] > array[j]){
                int temp = array[i];
                array[i] = array[j];
                array[j] = temp;
            }
        }
    }
    ```

---

# Array
- Search in Array
    - **Linear search**
        ```c
        int SIZE = 5;
        int array[SIZE] = {2, 3, 5, 1, 4};
        int target = 4;
        for(int i = 0 ; i < SIZE ; i++){
            if(array[i] == target){
                printf("index = %d\n", i);
                break;
            }
        }
        ```

---

# Array
- Search in Array
    - **Binary search**
        ```c
        int binarySearch(const int array[], int target, int low, int high){
            int middle;
            while(low <= high){
                middle = (low + high) / 2;
                if(target == array[middle]){
                    return middle;
                }
                else if(target < array[middle]){
                    high = middle - 1;
                }
                else{
                    low = middle + 1;
                }
            }
            return -1;
        }
        ```

---

- Search in Array
    - **Binary search**
        ```c
        int SIZE = 5;
        int array[SIZE] = {1, 2, 3, 4, 5, 6, 7, 8};
        int target = 7;
        printf("%d\n", binarySearch(array, target, 0, SIZE-1);  // 6
        ```

        |STEP   |---1---|---2---|---3---|---4---|---5---|---6---|---7---|---8---|
        |:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|
        |(1)    |L      |       |       |       |       |       |       |H      |
        |       |       |       |       |(M)    |       |       |       |       |
        |(2)    |       |       |       |       |L      |       |       |H      |
        |       |       |       |       |       |       |(M)    |       |       |
        |(3)    |       |       |       |       |       |       |L      |H      |
        |       |       |       |       |       |       |       |(M)    |       |

---

# Pointer

---

# Pointer
```c
void main(){
    int a = 1;
    int b = 2;
    int c = 3;
}
```

|Memory Address |Value  |Variable   |
|:-------------:|:-----:|:---------:|
|0X0012FF70     |1      |a          |
|0X0012FF74     |2      |b          |
|0X0012FF78     |3      |c          |

---

# Pointer
- `*`
    1. Pointer (指標)
        Declare that the type of the variable is a pointer. $\rightarrow$ It stores **address**.
    2. Dereference operator (取值運算子)
        Apart from variable declaration, we use `*` to get the value which is stored in the variable's address.
- `&`
    Address-of operator (取址運算子)  $\rightarrow$ Get the variable's **memory address**.

---

# Pointer
```c
void main(){
    int a = 1;
    int* ptr = &a;  // Declare a int pointer named "ptr" and it points to a's address

```

|Memory Address |Value      |Variable   |
|:-------------:|:---------:|:---------:|
|0X0012FF70     |1          |a          |
|0X0012FF74     |0X0012FF70 |ptr        |

- **Pointer variable**: a variable that stores pointer
- **Pointer**: point to a variable's address

---

# const

---

# const
- `int* ptr;`
    - 指標指的位址可以被改變
    - 所指位址的值可以被改變
- `int* const ptr;`
    - 指標指的位址不能被改變
    - 所指位址的值可以被改變
- `const int* ptr;`
    - 指標指的位址可以被改變
    - 所指位址的值不能被改變
- `const int* const ptr;`
    - 指標指的位址不能被改變
    - 所指位址的值不能被改變

---

# Exercise 6
**Matrix Multiplication**
$$
\begin{bmatrix}
    5 & 8 & -4 \\
    6 & 9 & -5 \\
    4 & 7 & -2 \\
\end{bmatrix}
\times
\begin{bmatrix}
    2 \\
    -3 \\
    1 \\
\end{bmatrix}
=
\begin{bmatrix}
    -18 \\
    -20 \\
    -15 \\
\end{bmatrix}
$$

- Input: Pairs of matrices we want to multiple until end-of-file. Each pair has two matrices.
- Output: Print the multiplied matrices, or print "Invalid calculation!!" if two matrices cannot be multiplied.

**Get repository on Ghost**: `oj get_assign ex6`
**Submit on Ghost**: `oj submit ex6 <code_file>`
*(Remember to login first!!)*

---

# Any Questions?
