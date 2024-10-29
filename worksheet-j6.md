## Worksheet J6

**Question 1:**  
The output of this program consists of "good morning" and "good afternoon" repeatedly over and over. Upon re-running, there is no specific order to the programs, it differentiates.  

**Question 2:**  
The sleep function will allow for one of the threads to, in simple words, "take a break". This will cause there to me more space between the printing out of the greeting messages - the messages are still inconsistent though.  

**Question 3:**  
This is because the main thread finishing has no affect on the morningthread or afternoonthread - they both will continue to run.  

**Question 4:** 
The output is a lot more orderly than the output of the code previously. This is because of the waiting before the morning and afternoon threads in which it is print only when the wait is completed, giving the output a break in between.  

**Question 5:**  
Join() forces the thread to wait until the current thread is completely done. Join(int) allows the thread to wait a specified time for the current thread to be finished.  

**Question 6:**  
When isAlive is called, it returns a check of true or false if the referenced thread is currently running or not. Join() will simply wait for the thread to terminate before starting the thread.  

**Question 7:**  
The output is a cluster of animal types and their laps - like cheetah, hare, tortise and their lap numbers. The print is like this because of the different wait times for each thread. For example, the wait times consist of 1000/ the animal speed which is different for each animal. This is why some print out repeatedly and then why others break those cycles.  

**Question 8:**  
``` Java
public class AnimalFootRace {
    public static void main(String[] args) {
        Thread tortoiseThread = new AnimalRacerThread("Tortoise", 5);
        Thread hareThread = new AnimalRacerThread("Hare", 20);
        Thread cheetahThread = new AnimalRacerThread("Cheetah", 50);

        System.out.println("On your marks, get set, go!");
        hareThread.start();
        try {
            System.out.println("Hare start");
            hareThread.join(200);
        } catch (InterruptedException e) {
            System.out.println("Failure");
        }
        tortoiseThread.start();
        cheetahThread.start();
    }
}
```
My edits worked because I had hare start before the rest of the animals, and I had the thread wait using the join(int) method.

**Question 9:**  
``` Java
public class AnimalFootRace {
    public static void main(String[] args) {
        Thread tortoiseThread = new AnimalRacerThread("Tortoise", 5);
        Thread hareThread = new AnimalRacerThread("Hare", 20);
        Thread cheetahThread = new AnimalRacerThread("Cheetah", 50);
        Thread lionThread = new AnimalRacerThread("Lion", 5000)
        System.out.println("On your marks, get set, go!");
        lionThread.start();
        tortoiseThread.start();
        hareThread.start();
        cheetahThread.start();
    }
}
```

**Question 10:**
Yes it is possible to create two singleton cases - this can be done if the methods are callled at precisely the same time.  

**Question 11:**  
If the synchornized keyword is added it is not possible as the keyword restircts the possibility of this occurring.  

**Question 12:**  
There is no output as there is an infinite loop - this is because the flag status while always be true and not updated.  

**Question 13:**  
Adding the volatile keyword gives the varaible the flexibility to change between different running threads - because the status is now volatile, the compiler is able to read and change it appropriately to the wanted behavior.  

**Question 14:**  
This would result in a race condition - this means that the performance will be dependent on the order of the code. To avoid this, the synchronized keyword should be added to the makebid method name. 


