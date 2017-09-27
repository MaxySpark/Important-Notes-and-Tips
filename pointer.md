# Pointer in C and C++

- **Def :** _Variable that stores address of other variables_

    `p //address`

    `*p // value at address`
    ‎
- Code
    ```c
        int a;

        int *p;

        p = &a;

        a = 5;

        print p //204 (address of a)

        print &a // 204

        print &p // 64 (address of p)

        print *p // 5 ( value at address 204/value of a)

        *p = 8; ( changed the value of a)

        print a; // 8
    ```