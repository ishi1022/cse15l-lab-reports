# Lab Report 5
## Part 1
## Orignal post from student 
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Student%20Post%20on%20Edstem.png?raw=true)

Code: 
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Code%20with%20Bug.png?raw=true)

Symptom: 
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Symptom.png?raw=true)

## Response from TA
Hi! Your approach seems correct, but try to insect your loop when you are making the new array. Consider how you are iterating through the input array and accessing elements. Make sure to double check if you are properly copying every other element into the result array! Let me know what you find. 

## Student response after changes
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Student%20Response.png?raw=true)

## The file & directory structure
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/File:Directory%20Structure.png?raw=true)

## The contents of each file before fixing the bug
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/Array%20Filter%20before%20edit.png?raw=true)
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/test.png?raw=true)

## The full command line (or lines) you ran to trigger the bug
![Image](https://github.com/ishi1022/cse15l-lab-reports/blob/main/command%20line.png?raw=true)

## A description of what to edit to fix the bug
To fix the bug I had to change the for loop content. Changing the loop from ```for(int i = 1; i < input.length; i+=2)``` to ```for(int i = 0; i < input.length; i+=2)``` makes sure that it starts from the first element being the ```0``` ```index``` and not the ```1``` ```index```. 
## Part 2 
In the second half of this quarter something I learned in depth is how to use the ```vim``` command to edit. I leanred many ways to edit my code through this command and different keys i could press to achieve different things. Something cool (and unrelated to cse15) that i learned is that there is a gene in certain people that makes corriander/cilantro taste like soap!
