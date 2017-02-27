what is array?
->Array is one of the simpliest data structure used to store collection of elements for grouping all together.
  Array allocates memory contiguously that means it's allocate blocks of memory at a time according to the size of the array.
  As array allocates memory contiguously, it is possible to access array elements by index.
  In C we can store only similar type of data in one array(eg. int arr[5] -> array of five integers).

Array Declareation:
->We can declare an array in C by specifying its type before the name of it. We need to specify size of the array.
  type arrayName[size];
  So to decalare array of 5 integer, we will write
  int arr[5]; //type -> integer, arrayName -> arr, size -> 5
  according to the type and the size of the array, we can calculate the space it will allocate in the memory
  we can get the size of the array by using sizeof(arrayName);//returns total space

Types of Array:
->Arrays are generally two type.
  1)Single Dimentional Array : Single or One Dimensional array is used to represent and store data in a linear form.
                       Array having only one subscript variable is called One-Dimensional array.
                       Syntax : <data-type> <array_name> [size];
                                int a[3];

  2)Multi Dimentional Array : Array having more than one subscript variable is called Multi-Dimensional array.
                              Multi Dimensional Array is also called as Matrix.
                              Syntax : <data-type> <array_name> [row_subscript][column-subscript];
                                      int a[3][3];
Array Initialization:
->  we can initialize array in different way in C.
    If we do not initialize array, some garbage value will be store to that index.
    1) int arr[5] = {1, 3, 5, 2, 6};
    2) we don't need to specify size explicitly if we initialize the array in the same place.
        char arr[] = {'a', 'b', 'c', 'd'};
        compiler will automatically calculate the size of that array.
    3) we can also inialize an array later where we need to initialize it.
        int x[2];
        x[0] = 1, x[1] = 5; // we can use loop to initialize
**Note : array is indexed from zero as the first element in array will be array[0].**
    Example :
    we will take one example to understand array in depth where we will take user input from keyboard and will display it in console.

    #include<stdio.h>
    int main() {
      int n; //variable to store size of the array
      printf("Enter Size of the Array: ");
      scanf("%d", &n); // taking user input from keyboard for array size
      int arr[n]; // declaring a integer array of size n
      for(int i =0; i < n; i++) { // loop to store each element from user input
        printf("\nEnter %d Element: ", i+1);
        scanf("%d", &arr[i]); //taking user input and storing it to array indexes like 1st input will be store in 0th index
      }
      printf("\n");
      for (int i = 0; i < n; i++) {
          printf("%d Element is: %d\n",i+1, arr[i]); // printing every elements of the array
      }
      return 0;
    }

Some Basic examples where we can use array :
->example 1) printing the sum of first 10 integer number starting from 1.
             code :
            
            
            #include<stdio.h>
             int main() {
               int num[10]; // declaring an array of 10 integers
               int sum = 0;
               for(int i = 0; i < 10; i++) {
                 num[i] = i + 1; // initializing each elements of the array where num[0] =1, num[1] = 2 etc.
               }
               for(int i = 0; i < 10; i++) {
                 sum += num[i]; // doing sum of all element by adding with the previous sum (sum = sum + num[i])
                 //like sum = sum(0) + (num[0] = 1) // sum = 1
                 //next sum = (sum = 1) + (num[1] = 2) // sum = 3
                 //it will continue
               }
               printf("%d\n", sum);
               return 0;
             }
             
             
  example 2) Highest Marks in a class of n students
              code:
             
             
             #include<stdio.h>
              int main() {
                int n;
                printf("Enter the Number of Students in the Class : ");
                scanf("%d", &n);// user input for declaring the size of students marks array
                float marks[n];

                for(int i = 0; i < n; i++) {
                  printf("\nEnter marks of %d student: ", i+1 );
                  scanf("%f", &marks[i]);//storing each students marks in the array
                }

                int highest_marks_index = 0;//variable to keep track of the student who got the highest marks, initializing it to 1st student
                float highest_marks = marks[highest_marks_index]; // variable to store the highest mark and iniatializing it to 1st student mark

                for(int i = 1; i < n; i++) {//looping over the array
                  if(marks[i] > highest_marks) { // checking whether the next array elemet is larger than highest_marks
                    highest_marks = marks[i]; // if its larger stroing it to highest_marks var
                    highest_marks_index = i; // setting ith index as highest_marks_index
                  }
                }
                printf("Student %d Got the Highest Marks which is %.2f\n", highest_marks_index + 1, highest_marks);//printing higest mark
                return 0;
              }

