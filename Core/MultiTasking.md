# MultiTasking in Python
Multitasking in Python refers to the ability of a program to execute multiple tasks simultaneously or concurrently. Python provides various mechanisms for multitasking, enabling developers to write programs that perform multiple tasks concurrently, thereby improving efficiency and responsiveness. Here are some of the common ways to achieve multitasking in Python:

Multithreading in Python allows you to run multiple threads (smaller units of a process) concurrently within a single process. This concurrency enables you to perform multiple tasks simultaneously and can be particularly useful for tasks that involve waiting for I/O operations (e.g., reading/writing to files or making network requests). However, due to the Global Interpreter Lock (GIL) in CPython, multithreading might not fully utilize multiple CPU cores for CPU-bound tasks. For CPU-bound tasks, consider using multiprocessing instead.

In Python, you can achieve multithreading using the threading module, which provides classes and functions to work with threads. Here's a basic example of multithreading in Python:

```python

import threading
import time

# Function to be executed by the thread
def print_numbers():
    for i in range(1, 6):
        print(f"Number: {i}")
        time.sleep(1)  # Simulate some work

def print_letters():
    for letter in "ABCDE":
        print(f"Letter: {letter}")
        time.sleep(1)  # Simulate some work

# Create two threads
thread1 = threading.Thread(target=print_numbers)
thread2 = threading.Thread(target=print_letters)

# Start the threads
thread1.start()
thread2.start()

# Wait for both threads to finish
thread1.join()
thread2.join()

print("Both threads have finished.")
```

In this example, we define two functions, print_numbers() and print_letters(), which print numbers and letters respectively. We then create two threads (thread1 and thread2) and assign each function to be executed by its respective thread using the target parameter.

After starting the threads with start(), they run concurrently, executing their respective tasks. The join() method is used to wait for both threads to finish before proceeding with the next part of the code.

Keep in mind that when working with threads, you should be careful about potential race conditions and synchronization issues, especially when multiple threads access shared resources simultaneously. To manage concurrent access to shared resources, consider using synchronization mechanisms like locks or semaphores provided by the threading module.

Again, if you have CPU-bound tasks and want to fully utilize multiple CPU cores, consider using the multiprocessing module for parallel processing instead of the threading module.

# Race Condition in threads
A race condition is a common concurrency-related issue that occurs when multiple threads or processes access a shared resource or perform a sequence of operations concurrently, and the final outcome of the program depends on the timing of the threads' execution. The result becomes unpredictable, and the program may behave unexpectedly or produce incorrect results.

Race conditions in Python (and other programming languages) are often caused by a lack of proper synchronization or coordination between threads or processes that access shared data. The Global Interpreter Lock (GIL) in Python further exacerbates race condition issues in multi-threaded programs, making them more prominent in CPU-bound tasks.

Let's illustrate a simple example of a race condition in Python:

```python
import threading

# A shared variable
shared_variable = 0

# Function that increments the shared variable
def increment_variable():
    global shared_variable
    for _ in range(100000):
        shared_variable += 1

# Function that decrements the shared variable
def decrement_variable():
    global shared_variable
    for _ in range(100000):
        shared_variable -= 1

if __name__ == "__main__":
    # Creating multiple threads
    thread1 = threading.Thread(target=increment_variable)
    thread2 = threading.Thread(target=decrement_variable)

    # Starting the threads
    thread1.start()
    thread2.start()

    # Wait for both threads to complete
    thread1.join()
    thread2.join()

    print("Final value of shared_variable:", shared_variable)
```

In this example, two threads (thread1 and thread2) are concurrently modifying the shared variable shared_variable. The threads increment and decrement the variable 100,000 times each. Due to the lack of proper synchronization, the final value of shared_variable is non-deterministic, and the program suffers from a race condition.

The output may vary each time you run the program, and you may see results like:

```sql
Final value of shared_variable: -2774
```

or

```sql

Final value of shared_variable: 313
```

To avoid race conditions, you need to use synchronization primitives like locks, semaphores, or threading constructs that ensure exclusive access to shared resources. These mechanisms enforce proper order of execution and prevent multiple threads from accessing critical sections of the code simultaneously. Synchronization helps maintain data consistency and ensure predictable program behavior when working with shared data.

# locks in threads
In Python, accessing variables across different threads can lead to potential race conditions and data inconsistency issues if not handled properly. To safely access variables in different threads, you should use synchronization mechanisms like locks to ensure that only one thread can modify the variable at a time.

Here's an example of how you can safely access a variable in different threads using a Lock from the threading module:

```python
import threading

# Global variable shared by multiple threads
shared_variable = 0

# Lock to synchronize access to the shared variable
lock = threading.Lock()

# Function that increments the shared variable
def increment_variable():
    global shared_variable
    for _ in range(1000000):
        # Acquire the lock before modifying the shared variable
        with lock:
            shared_variable += 1

# Function that decrements the shared variable
def decrement_variable():
    global shared_variable
    for _ in range(1000000):
        # Acquire the lock before modifying the shared variable
        with lock:
            shared_variable -= 1

if __name__ == "__main__":
    # Creating multiple threads
    thread1 = threading.Thread(target=increment_variable)
    thread2 = threading.Thread(target=decrement_variable)

    # Starting the threads
    thread1.start()
    thread2.start()

    # Wait for both threads to complete
    thread1.join()
    thread2.join()

    print("Final value of shared_variable:", shared_variable)
```

In this example, we have a shared variable shared_variable that is accessed by two threads thread1 and thread2. To ensure safe access, we use a Lock called lock. Before modifying the shared_variable, each thread acquires the lock using the with lock statement. This ensures that only one thread can modify the variable at any given time, preventing race conditions.

Keep in mind that using locks can introduce some performance overhead, and it's essential to use them judiciously. In some cases, you might consider using other synchronization primitives, such as Semaphore or Condition, depending on the specific requirements of your multithreaded application.

### Semaphore
In Python, a Semaphore is a synchronization primitive provided by the threading module that allows you to control access to a shared resource. A Semaphore is essentially a counter that restricts the number of threads that can access the shared resource concurrently. It can be used to prevent thread contention and manage access to resources with limited capacity.

The Semaphore has two primary methods: acquire() and release(). When a thread calls acquire(), the Semaphore decrements its internal counter, and if the counter becomes zero or negative, the acquire() call blocks the thread until another thread calls release() to increment the counter.

Here's an example of how to use a Semaphore in Python:

```python

import threading

# A shared resource with a capacity of 3
shared_resource = []
semaphore = threading.Semaphore(3)

# Function that adds an item to the shared resource
def add_item(item):
    semaphore.acquire()
    shared_resource.append(item)
    print(f"Added item {item} to the shared resource.")
    semaphore.release()

# Function that removes an item from the shared resource
def remove_item():
    semaphore.acquire()
    if len(shared_resource) > 0:
        item = shared_resource.pop(0)
        print(f"Removed item {item} from the shared resource.")
    else:
        print("Shared resource is empty.")
    semaphore.release()

if __name__ == "__main__":
    # Creating multiple threads
    threads = []

    for i in range(5):
        thread = threading.Thread(target=add_item, args=(i,))
        threads.append(thread)

    for i in range(3):
        thread = threading.Thread(target=remove_item)
        threads.append(thread)

    # Starting the threads
    for thread in threads:
        thread.start()

    # Wait for all threads to complete
    for thread in threads:
        thread.join()

    print("Final shared resource:", shared_resource)
```

In this example, we have a shared resource shared_resource, which is a list with a capacity of 3. We use a Semaphore with an initial value of 3 to control access to this shared resource. Three threads are responsible for adding items to the resource, and two threads are responsible for removing items from the resource.

When adding or removing an item, the respective thread first calls acquire() on the semaphore to decrease its internal counter. If the counter is positive, the thread proceeds to perform the operation. Otherwise, it waits until another thread releases the semaphore by calling release(). After the operation is done, the thread calls release() to increment the counter, allowing other threads to access the shared resource.

Using Semaphores is a way to manage concurrent access to shared resources, and it helps in preventing issues like data inconsistency and race conditions.
## Multiprocessing:
1. Multiprocessing allows you to create multiple processes that run independently and concurrently.
2. Python's multiprocessing module allows you to create and manage processes.
3. Multiprocessing is suitable for tasks that are CPU-bound (such as computations) since it can take advantage of multiple CPU cores.
```python
# importing the multiprocessing module
import multiprocessing
import time

def print_cube(num):
    """
    function to print cube of given num
    """
    print("Cube: {}".format(num * num * num))
    #time.sleep(20)


def print_square(num):
    """
    function to print square of given num
    """
    print("Square: {}".format(num * num))
    #time.sleep(20)


if __name__ == "__main__":
    # creating processes
    p1 = multiprocessing.Process(target=print_square, args=(10,))
    p2 = multiprocessing.Process(target=print_cube, args=(10,))

    # starting process 1
    p1.start()
    # starting process 2
    p2.start()

    # wait until process 1 is finished
    p1.join()
    # wait until process 2 is finished
    p2.join()

    # both processes finished
    print("Done!")

```
## Coroutine-based Libraries:
Python has various coroutine-based libraries like aiohttp (for asynchronous HTTP requests), aiomysql (for asynchronous MySQL database access), etc., which allow you to perform asynchronous tasks efficiently.

Multitasking in Python allows you to leverage the system's resources effectively, leading to better performance and responsiveness in certain scenarios. However, it's important to be mindful of potential concurrency issues, such as race conditions or deadlocks, when working with multiple threads or processes. Proper synchronization mechanisms like locks or semaphores should be used when shared resources are accessed by multiple tasks simultaneously.


### Locking in multiprocessing

In Python's multiprocessing module, you can use a shared variable among multiple processes using the Value or Array objects from the multiprocessing module. These objects enable you to create shared memory locations accessible by multiple processes. Unlike threads, processes have separate memory spaces, so sharing data between processes requires using these specialized data structures.

Here's an example of how to use a shared variable with Value in the multiprocessing module:

```python

import multiprocessing

# A shared variable
shared_variable = multiprocessing.Value('i', 0)

# Function that increments the shared variable
def increment_variable(shared_var):
    for _ in range(100000):
        with shared_var.get_lock():
            shared_var.value += 1

# Function that decrements the shared variable
def decrement_variable(shared_var):
    for _ in range(100000):
        with shared_var.get_lock():
            shared_var.value -= 1

if __name__ == "__main__":
    # Creating multiple processes
    process1 = multiprocessing.Process(target=increment_variable, args=(shared_variable,))
    process2 = multiprocessing.Process(target=decrement_variable, args=(shared_variable,))

    # Starting the processes
    process1.start()
    process2.start()

    # Wait for both processes to complete
    process1.join()
    process2.join()

    print("Final value of shared_variable:", shared_variable.value)
```

In this example, we use multiprocessing.Value('i', 0) to create a shared integer variable initialized to 0. The 'i' argument specifies the data type (integer). The Value object is used to create the shared variable, and the get_lock() method ensures that access to the shared variable is protected by a lock to avoid race conditions.

When accessing the shared variable within the functions increment_variable and decrement_variable, we use a with statement and the lock to make sure that only one process can modify the variable at a time.

Keep in mind that shared variables introduce synchronization overhead due to the need for locks, so it's essential to use them only when necessary. In some cases, alternative communication methods like multiprocessing.Queue or multiprocessing.Pipe may be more suitable, depending on the specific requirements of your application.
