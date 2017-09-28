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
        
        printf("a = %d\n",a);
        printf("p = %p\n",p);
        printf("&a = %p\n",&a);
        printf("&p = %p\n",&p);
        printf("*p = %d\n",*p);
        
        *p = 8;
        
        printf("After dereferencing, a = %d\n",a);
        
        return 0;
    }

    //output

    a = 5
    p = 0x7ffeb0b1ed7c
    &a = 0x7ffeb0b1ed7c
    &p = 0x7ffeb0b1ed80
    *p = 5
    After dereferencing, a = 8

    ```

- `<datatype> *p`

   `p+1 will point to the address (p + size of datatype of p points to)`

- **Pointer to Pointer**
    ```c
    int a = 10;

    int *p = &a; // address of a

    int **q = &p; // address of p

    int ***r = &q; // address of q

    print r; // adress of q

    print *r; // value at q || (address of p)

    print **r; // value at *q or *(address of p) || (address of a)

    print ***r; // value at *p or *(address of a) || **q || value of a

    ```

- **Function Call By Reference**
    ```c
    void Increment(int *p) {
        //int *p -> Formal Argument

        *p = (*p) + 1;

        // increase the value at p by 1
    }
    int main() {
        int a = 10;
        Increment(&a);

        // pass the address
        // &a -> Actual Argument
    }

    ```

- 