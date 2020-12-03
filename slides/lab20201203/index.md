---
marp: true
title: Computer Programming 1 Lab - Lecture 10
date: 2020-12-03
paginate: true 
---

# Computer Programming 1 Lab
## 2020-12-03
張麒竑

---

# Outline
- [Input/Output](#Input/Output)
- [Struct](#Struct)
- [Exercise 9](#Exercise-9)
- [Assign9 Hint](#Assign9-Hint)

---

# Input/Output

---

# Input/Output
## `printf`
- Specifier
    ```c
    /* Signed decimal integer */
    printf("%d\n", 455);    // 455
    printf("%d\n", +455);   // 455
    printf("%d\n", -455);   // -455
    printf("%ld\n", 2000000000L);   // 2000000000
    /* Unsigned octol integer */
    printf("%o\n", 455);    // 707
    /* Unsigned decimal integer */
    printf("%u\n", 455);    // 455
    printf("%u\n", -455);   // 4294966841
    /* Unsigned hexadecimal integer */
    printf("%x\n", 455);    // 1c7
    ```

---

# Input/Output
## `printf`
- Output format - integer
    ```c
    printf("%8d***\n", 123);
    printf("%8d***\n", -123);
    printf("%-8d***\n", 123);
    printf("%-8d***\n", -123);
    printf("%8d***\n", 123456789);
    printf("%8d***\n", -123456789);
    printf("\n");
    printf("%d\n%d\n", 64, 64);
    printf("%04d\n%04d\n", 64, 64);
    ```

---

# Input/Output
- Output format - integer (cont.)
    ```bash
        123***
        -123***
    123     ***
    -123    ***
    123456789***
    -123456789***

    64
    64
    0064
    0064
    ```

---

# Input/Output
- Output format - float
    ```c
    printf("%f\n", 3.14159);
    printf("%10f\n", 3.14159);
    printf("%.2f\n", 3.14159);
    printf("%10.2f\n", 3.14159);
    ```
    Output:
    ```bash
    3.141590
      3.141590
    3.14
          3.14
    ```

---

# Input/Output
## `sprintf`
Write formatted data to string
```
int sprintf( char* str, const char* format, ...)
```
- `str`: string being processed
- `format`: string format you want
- Retuen value:
    - On success, the total number of characters written is returned.
    - On failure, a negative number is returned.

---

# Input/Output
```c
#include <stdio.h>
int main(){
    char buf[50];
    int n;
    int a = 5;
    int b = 3;

    n = sprintf(buf, "%d + %d = %d", a, b, a+b);
    printf("%s\n", buf);
    printf("%d\n", n);
    return 0;
}
```
Output:
```bash
5 + 3 = 8
9
```

---

# Input/Output
## `scanf`
Precise input formatting can be accomplished with `scanf`
```c
scanf(format_control_string, other_arguments);
```
- `format_control_string` describes the formats of the input.
- `ither_arguments` are pointers to variables in which the input will be stored.

---

# Input/Output
```c
// year, month, and day are "int"
scanf("%d-%d-%d", &year, &month, &day);

// year, month, and day are "int"
scanf("%d%*c%d%*c%d", &year, &month, &day);

// character is a "char"
scanf("%c\n", &c);

// string is a "char" array
scanf("%s", string);
```

---

# Input/Output
## `gets`
```c
char *gets(char* str)
```
- Reads a line from stdin and stores it into the string pointed to by str.
- It stops when either the newline character is read or when the end-of-file is reached, whichever comes first.

---

# Input/Output
```c
#include <stdio.h>

int main () {
   char str[50];

   printf("Enter a string : ");
   gets(str);

   printf("You entered: %s", str);

   return(0);
}
```
Output:
```bash
Enter a string : This is a cat.
You entered: This is a cat.
```

---

# Struct

---

# Struct
- Structures are collections of related variables under one name.
- **Structures** may contain variables of **many different data types**.
    - **Arrays** contain only elements of **the same data types**.
```c
struct student{
    char name[20];
    char gender;
    int age;
    struct student* next;
};
```

---

```c
struct student stud;
strcpy(stud.name, "Chi-Hung");
stud.gender = 'M';
stud.age = 22;

printf("Name: %s\n", stud.name);
printf("Gender: %c\n", stud.gender);
printf("Age: %d\n", stud.age);
```
Output:
```bash
Name: Chi-Hung
Gender: M
Age: 22
```

---

# Typedef
- Define the structure first, then use `typedef`.
    ```c
    struct student{
        char name[20];
        char gender;
        int age;
        struct student* next;
    };
    typedef struct student Student;
    ```
- Use `typedef` when defining the structure.
    ```c
    typedef struct student{
        char name[20];
        char gender;
        int age;
        struct student* next;
    } Student;
    ```

---

# Exercise 9
計算文章出現的每個單字所出現的次數
- 所有標點符號及數字都不能出現
- 輸入不只一行
- 所有的單字都要用小寫來計算（例：The和the視為同一個單字）
- 輸出的單字順序要用字典排序

Get exercise 9 folder by command line
```bash
oj get_assign ex9
```

Submit your exercise 9 script by command line
```bash
oj submit ex9 <your_script_file>
```

---

- Input
    ```text
    I have a pen. I have an apple.
    Uhh!! Apple-pen.

    I have a pen. I have a pineapple.
    Uhh!! Pineapple-pen.

    Apple-pen. Pineapple-pen.
    Uhh!! Pen pineapple apple pen.
    ```
- Output
    ```text
    a 3
    an 1
    apple 4
    have 4
    i 4
    pen 8
    pineapple 4
    uhh 3
    ```

---

# Assign9 Hint
因為打英文太累，而且麒竑的英文頗爛，所以我打中文

---

# Assign9 Hint
- 輸入格式
    - 車站
        - 站數
        - 停靠站及停靠順序（由北往南或由南往北，不會有亂跳的狀況）
    - 訂位
        ```text
        RESERVE NAME, FROM, TO, #tickets, SEAT(s)
        ```
    - 取消
        ```text
        CANCEL NAME, FROM, TO, SEAT
        ```
    - 查詢
        ```text
        CANCEL NAME, SEAT
        ```

---

# Assign9 Hint
- 輸出格式
    - 訂位
        ```text
        RESERVE SUCCESSED!! -> NAME SEAT (FROM - TO)
        RESERVE FAILED.... (station information has something wrong)
        RESERVE FAILED.... (too many seats)
        RESERVE FAILED.... (repest seats)
        ```
    - 取消
        ```text
        CANCELLATION SUCCESSED!! SEAT (FROM - TO)
        CANCELLATION FAILED.... (cannot find the stations information)
        CANCELLATION FAILED.... (cannot find the seat information)
        ```
    - 查詢
        ```text
        CHECK NAME SEAT -> (FROM - TO)
        CHECK FAILED.... (cannot find the reservation data)
        ```

---

# Assign9 Hint
- **訂位**
    1. 一次**最多訂4張票**
    2. **全部座位都成功才算那一筆的訂位是成功的**！否則該筆訂位就是失敗
    3. 有關車站的訂位失敗
        - 起訖站有出現列車不會停靠的車站
        - 起訖站與列車行進方向相反
    4. 有關車票張數的訂位失敗
        - 訂票超過4張
    5. 有關座位的訂位失敗
        - 訂票的位子已經有被預訂走了
        - 同一筆訂位出現重複的位子
    6. 若有多個訂位失敗原因，印出原因的優先順序為「**車站->車票張數->座位**」

---

# Assign9 Hint
- **取消**
    1. 當**那個"人"在輸入的"指定區間"內在"指定座位"都有訂位**，則可成功取消該訂位（三個條件缺一不可）
    2. 取消**不是**取消那個座位訂位時的區間，而去取消**現在"這個取消指令"所指定的區間的訂位**
    3. 只需要看現在的指定區間，不需要看區間前後的訂位狀況（所以有可能會出現一段訂位但中間被取消的狀況）
    4. 只需要看現在的指定座位，不需要看這個座位在訂位時同時訂的其他座位

---

# Assign9 Hint
- **查詢**
    1. 需印出**那個人在指定座位的起訖站**
    2. 只要那個人在該指定座位沒有任何訂位，則顯示查詢錯誤
    3. 如果那個人在指定座位有多段區間（例：新竹->台中、台南->高雄），則需要**將所有區間都印出來**，並用**空格分隔每個區間**，印出順序是依照列車的行進順序（如：列車是由北往南行駛，則「新竹->台中」先印出，「台南->高雄」後印出）
    4. 如果有兩次的訂位在同一個座位，且區間為相連的（例：台北->新竹、新竹->台中），則在查詢時**須將兩個區間相連**一起顯示（如：台北->台中）

---

# Assign9 Hint
- 貼心(??)小提示
    1. 測資中有許多的分隔行，記得也要將這些分隔行讀進來
    2. 每個`,`後面**都有一個空格**，在做字串分割的時候要注意！！
    3. 建議讀取測資用`gets`來讀取，再來做字串分割
    4. 有關輸出格式，如果上面的投影片不清楚，可以去範例輸出看，我有把所有可能的輸出狀況都列出來了
    5. 麒竑很友善，拜託不要來揍我OAO

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