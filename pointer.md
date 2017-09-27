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

    ```c
    //code
    #include <stdio.h>
    int main()
    {
        int a;
        int *p;
        p = &a;
        a = 5;
        
        printf("value of a is %d\n",a);
        printf("value of p is %p\n",p);
        printf("value of &a is %p\n",&a);
        printf("value of &p is %p\n",&p);
        printf("value of *p is %d\n",*p);
        
        *p = 8;
        
        printf("value of a is %d\n",a);
        
        return 0;
    }

    //output

    value of a is 5
    value of p is 0x7ffdc179cc5c
    value of &a is 0x7ffdc179cc5c
    value of &p is 0x7ffdc179cc60
    value of *p is 5
    value of a is 8
    ```
    