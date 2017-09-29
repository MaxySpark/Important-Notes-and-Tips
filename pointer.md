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

- **Pointer and Array**
    ```c
    int A = {1,2,3,4,5};

    print A; // Adress of the first element of the Array || &A[0]

    int *p = A;

    // We can do p++ but not A++

    print (A+1); // Address of 2nd element or adress of index 1 || &A[1]

    print *(A); // Value at index 0 or first element || A[0] 
    print *(A+2); // Value at index 2 or first element || A[2]

    ```

- **Array as Function Argument**

    ```c
    int SOE(int A[],int size){
        // Here Array is Passed as Reference
        // int A[] = int *A
        // Always Pass the size of the array
    }
    int main() {
        int A[] = {1,2,3,4,5};

        int size = sizeof(A)/sizeof(A[0]);

        SOE(A,size);
        // or we can write SOE(&A[0],size);
        // Since array as function argument only returns the address of the first element
    }

    ```

- **Pointer and String/Character Array**
    ```c
    #include <stdio.h>

    void print(char* C) // void print(char C[])
    {
        // int i =0;
        while(*C != '\0') // while(C[i] != '\0')
        {
            printf("%c",*C); // printf("%c",C[i])
            C++; // i++
        }
        printf("\n");
    }

    int main() 
    {
        char C[20] = "Hello";
        print(C);
        return 0;
    }
    ```

    ```c
    char C1[6] = "hello";
    
    char* C2 = C1; // valid
    
    C1 = C2; // not valid

    char *C = "hello"; // it works but we can't use C[0] = 'A' etc.
    ```

- **Pointer and 2D Array**
    ```c
    A[i][j] = *(B[i]+j)
            = *(*(B+i)+j)
    ```

- **Dynamic Memory Allocation in Heap**
    ```c
    // In C Funcyion-
    malloc // data_type *p = (data_type *)malloc(number_of_el * sizeof(data_type))
           // malloc does not initialize the variable

    calloc // data_type *p = (data_type *)calloc(number_of_el, sizeof(data_type))
           // calloc initialize the variable with "zeros" (0)
    
    realloc // data_type *p = (data_type *)realloc(previous_pointer, number_of_el * sizeof(data_type))
           // data_type *p = (data_type *)realloc(NULL, number_of_el * sizeof(data_type)) || malloc
           // data_type *p = (data_type *)realloc(p, 0) || free(p)

    free

    // In C++ Function - 
    new
    delete
    ```

    ```c
    // in C

    int *p;
    p = (int *)malloc(sizeof(int));
    // malloc returns a void pointer from "HEAP"
    // to cast void pointer to int pointer uses (int *) here
    *p = 10;

    free(p); // freed any memory allocated by malloc

    int *a;
    a = (int *)malloc(20*sizeof(int)); // a[20]
    ```

    ```c++
    // in c++

    int *p;
    p = new int;
    *p = 10;
    delete p;

    p = new int[20];
    delete[] p;

    // don't have to type cast
    ```