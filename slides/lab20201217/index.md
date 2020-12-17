---
marp: true
title: Computer Programming 1 Lab - Lecture 12
date: 2020-12-17
paginate: true 
---
<style>
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>
# Computer Programming 1 Lab
## 2020-12-17

---

# Outline

- bitwise operations
- Examples
- Exercise11

--- 

# bitwise operations

---

# bitwise operations

## 0x (zero X) prefix
 - A prefix to indicate the number is in hexadecimal
 - Often used to show memory address.

---

### example:

```c
int a = 7414;
if(a == 0x1CF6){    // 7414 in hex
    printf("True\n");
}
else{
    printf("False\n");
}
return 0;
```
### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c 
darkknive@1091cp1:~$ ./a.out 
True
darkknive@1091cp1:~$ 
```

---

# bitwise operations

## operators
 - AND( `&` )
 - OR( `|` )
 - NOT( `~` )
 - XOR( `^` )
 - shift operators( `<<`, `>>`)
---

# bitwise operations
## operator AND( `&` )

<style>
.center{
    margin-left: auto;
    margin-right: auto;
}
td{
    width:100px;
    height:100px;
}
</style>

 - Only when both bits are 1 will result in 1.

<div class="center">



|   | 0 | 1 |
|:-:|:-:|:-:|
| 0 | 0 | 0 |
| 1 | 0 | 1 |

</div>

---

### example:

```c
int a = 0x0000000F;
a &= 0x0000000A;    //  a = a & 0x0000000A
printf("%d\n", a);
```
### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c
darkknive@1091cp1:~$ ./a.out
10
darkknive@1091cp1:~$
```

---

<div class="center">

|       |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|
|   F   | 1 | 1 | 1 | 1 |
|   A   | 1 | 0 | 1 | 0 |
|results| 1 | 0 | 1 | 0 |

</div>

---
# bitwise operations
## operator OR( `|` )

 - Either one of two bits is 1 will result in 1.

<div class="center">

|   | 0 | 1 |
|:-:|:-:|:-:|
| 0 | 0 | 1 |
| 1 | 1 | 1 |

</div>

---

### example:

```c
int a = 0x00000006;
a |= 0x0000000A;    //  a = a | 0x0000000A;
printf("%d\n", a);
```
### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c
darkknive@1091cp1:~$ ./a.out
14
darkknive@1091cp1:~$
```

---

<div class="center">

|       |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|
|   6   | 0 | 1 | 1 | 0 |
|   A   | 1 | 0 | 1 | 0 |
|results| 1 | 1 | 1 | 0 |

</div>

---

# bitwise operations
## operator NOT( `~` )

 - Not operation will negate the bit

<div class="center">

|   | 0 | 1 |
|:-:|:-:|:-:|
| ~ | 1 | 0 |

</div>

---

### example:

```c
int a = 0xFFFFFFFA;
a = ~a;
printf("%d\n", a);
```
### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c
darkknive@1091cp1:~$ ./a.out
5
darkknive@1091cp1:~$
```

---

<div class="center">

|       |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|
|   F   | 1 | 1 | 1 | 1 |
|results| 0 | 0 | 0 | 0 |

|       |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|
|   A   | 1 | 0 | 1 | 0 |
|results| 0 | 1 | 0 | 1 |

</div>

---

# bitwise operations
## operator XOR( `^` )

 - Only when one of the bits is 1 will result in 1.

<div class="center">

|   | 0 | 1 |
|:-:|:-:|:-:|
| 0 | 0 | 1 |
| 1 | 1 | 0 |

</div>

---

### example:

```c
int a = 0x00000006;
a ^= 0x0000000A;    //  a = a ^ 0x0000000A;
printf("%d\n", a);
```
### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c
darkknive@1091cp1:~$ ./a.out
12
darkknive@1091cp1:~$
```

---

<div class="center">

|       |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|
|   6   | 0 | 1 | 1 | 0 |
|   A   | 1 | 0 | 1 | 0 |
|results| 1 | 1 | 0 | 0 |

</div>

---

# bitwise operations
## operator shift( `<<`, `>>` )

 - the least-significant bit is lost
 - 0 is inserted on the other end

---

### example:

```c
int a = 0x000000F1;
a >>= 2;    //  a = a >> 2;
printf("%d\n", a);
a <<= 2;    //  a = a << 2;
printf("%d\n", a);
```

### results:

```bash
darkknive@1091cp1:~$ gcc ./main.c
darkknive@1091cp1:~$ ./a.out
60
240
darkknive@1091cp1:~$
```

---

<div class="center">

|       |   |   |   |   |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0xF1  | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 1 |
| >>=2  | 0 | 0 | 1 | 1 | 1 | 1 | 0 | 0 |

|       |   |   |   |   |   |   |   |   |
|  :-:  |:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0x3C  | 0 | 0 | 1 | 1 | 1 | 1 | 0 | 0 |
| <<=2  | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 |

</div>

---

# bitwise operations
## example:

A list of numbers is given, and every number appears twice except one. Please find out which one is it.

---

# bitwise operations
## example:
### method 1

Put every number into a list, sort and find which number only appears once.
 
Time complexity: O(NlogN)

---

# bitwise operations
## example:
### method 2

Start with 0, and do XOR operation with each number read.
 
Time complexity: O(N)

---

# bitwise operations
## example:
### method 2

```c
int a = 0;
int tmp;
while(scanf("%d", &tmp) != EOF){
    a ^= tmp;
}
printf("%d\n", a);
```

---

# [Exercise11](https://oj.mozix.ebg.tw/contest/53/problem/1091CP1%20Exercise11)

---

<!-- 
  backgroundImage: "linear-gradient(to bottom, #67b8e3, #0288d1)"
-->
<style scoped>
  h1, h2 {
    color: #efefef;
  }
</style>
# <!--fit--> Any Question?
## <!--fit--> Course? Assignment? Exercise? TA?
