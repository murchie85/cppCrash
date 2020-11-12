# C++ Refresher

![](https://engineering.fb.com/wp-content/uploads/2015/06/1522635669452_11.jpg)

  

## GET INPUT 

```cpp
cin >> age 
```
  
## get string input 


```cpp 


getline(cin,name);
// input, var

cout << "hello " << name;

```



# ARRAYS 

```cpp
int mynumbers[]  = {4,5,6,7};


// empty array 

int mynumbers[20];
```

## Add number 

```cpp
mynumbers[4] = 8;
```

# Threading  


**PROS**

- Fast to start 
- Shares mem
- Unlike multiprocessing, all bloat isn't needed to prevent them stepping on each others toes 
- Low overhead

**CONS**
  
- Difficult to implement
- Can't run on distributed system   

 

```cpp
#include <thread>
#include <iostream>
using namespace std;


// FUNCTION WE WISH TO THREAD 

void function_1(){

	std::cout << " a random print statement" << std::endl;
}

int main(){
	std::thread t1(function_1); // t1 starts running
	

	// DEPENDENT 


	t1.join(); // main thread waits for t1 to finish

	// DEAOMON PROCESS 
	// DETACH means it runs freely (main wont wait)
	// If you ran this, it wouldn't print beause main finishes first
	t1.detach(); 

	return 0;
}

```

### functions 

```cpp 

// DECLARE THREAD 
std::thread t1(function_1);

// JOIN
t1.join();
  
// DETACH
t1.detach();


// Check detached
if (t1.joinable())
	t1.join();

```




### NOTES 

COMPARING PRIMATIVES  

#### mutual exclusion lock  
  
The most efficient mechanism in both memory use and execution time. The basic use of a mutual exclusion lock is to serialize access to a resource.

#### condition variable  

The basic use of a condition variable is to block on a change of state; that is it provides a thread wait facility. Remember that a mutex lock must be acquired before blocking on a condition variable and must be unlocked after returning from pthread_cond_wait(). The mutex lock must also be held across the change of state that occurs before the corresponding call to pthread_cond_signal().

#### Sephamore 

The semaphore uses more memory than the condition variable. It is easier to use in some circumstances because a semaphore variable functions on state rather than on control. Unlike a lock, a semaphore does not have an owner. Any thread can increment a semaphore that has blocked.    

#### Read-Write lock   

The read-write lock permits concurrent reads and exclusive writes to a protected resource. The read-write lock is a single entity that can be locked in read or write mode. To modify a resource, a thread must first acquire the exclusive write lock. An exclusive write lock is not permitted until all read locks have been released.


  
# BASICS 

## Class definition

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Classes-and-Objects-in-C.png)

## Declaration 

```cpp
    string characterName = "Adam";
    int characterAge = 35;
```


## Print 

```cpp
cout << "My name is " << characterName << endl;
cout << "My name is " << characterName << "\n";


```

## String functions 

`string mystring = "Adam";`     

`mystring.len()`  
  
`mystring.find("d",0);`  

`mystring.substr(1,3);`  





	

