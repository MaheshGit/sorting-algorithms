Thanks to a careless technical specialist at Neev, selection sort and quick sort just stopped working.
As a fresher, debug the program with the help of browser developer tools using breakpoints and save the day by fixing the program.

The catch - also document your steps below. 

Name : 


Selection Sort
==============

## Steps

1. I started debugging in Google Chrome using Developers Tools .
2. To debug page open it in chrome and press F12 
3. Then in Sources we can select .js file to debug it.
4. now in selection sort i started to analyze the code.
5. then i put three break points to analyze the values of the variables to find the problem .
      first breakpoint : for (var i = 0; i < this.a.length; i++)
      second breakpoint :  max = i; to check value
      third breakpoint : in for loop  max = i; to check whether correct value swapped or not.
6. using F5 we iterate through the loop and find following changes : 

      original :   for (var j = 0; j < i; j++)
            {
                if (this.a[j] < this.a[max])
                    max = i;
            }

       changed for loop :  for (var j = i+1; j < this.a.length; j++)
            {
                if (this.a[j] < this.a[max])
                    max = j;
            }
7. to check value of max we can hover over it . it will show the value.
8.  we can see array elements in scope variables.
9.  In this way i bebug the selection sort .



QuickSort
=========

## Steps

1. I started debugging in Google Chrome using Developers Tools .
2. To debug page open it in chrome and press F12 
3. Then in Sources we can select .js file to debug it.
4. now in quick sort i started to analyze the code.
5. for quick sort we should know pivot element . 
6. In this function first element is used as pivot element.
7. then i put  break points in lineno. 230,234,240 to analyze the values of the variables to find the problem 
8. after putting breakpoint by pressing F5 we can iterate through it and see the local variables values
9. by looking at the scope variables we find that its taking value of r 50 but the index of last element in the array is 49
   so we modify it like this:
   var j = r-1;
10. inside if condition there is no need of increment and decrement so i commented them and again debug them and desired output       come . 
11. when its subpartioning array its taking variables in both arrays so we changed the function like this:
     qsort: function(p, r) {
    if (p < r)
    {
        var q = this.part(p, r);
        this.qsort(p, q);
        this.qsort(q+1, r);  //change is made here
    }
    }

12. In this way i debug the quick sort.
