# Stopwatch

## Fortran code: Stopwatch class to measure computation times.

   This class is a stopwatch to measure computation times. It handles 
  multiple simultaneous events, and allows for pausing and resetting each
  one individually. It measures both the elapsed time, and the total
  CPU time (different when computing in parallel). This program can be 
  invoked from other source files by using the module StopwatchClass
  ```fortran
program main
  use StopwatchClass
  ...
```

  The user just interacts with the Stopwatch class. The process to measure
  times is:

  1. Create an event. Each event is identified by a name (character)
  ```fortran
call Stopwatch % CreateNewEvent("EventName")
```
           

  2. Start the event:
  
  ```fortran
call Stopwatch % Start("EventName")
```
           

  3. Pause the event:
  
  ```fortran
call Stopwatch % Pause("EventName")
```

  4. Get the times:
  
  ```fortran
call Stopwatch % ElapsedTime("EventName")
call Stopwatch % CPUTime("EventName")
```


   5. Reset the event (if desired):
   
  ```fortran
call Stopwatch % Reset("EventName")
```
  **NOTE:** The time can be measured **while the event is running**. It just takes
  a measure of the actual time and compares it to the previous register.
 
