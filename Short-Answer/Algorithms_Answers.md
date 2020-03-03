#### Please add your answers to the **_Analysis of Algorithms_** exercises here.

## Exercise I

a) The main while loop seems to set an upper bound of n^3, which implies a possible runtime of O(n^3), however each iteration steps through growing at a rate of n^2. This ends up reducing the amount of actual iterations being run so the runtime complexity ends up being linear at **O(n)**.

b) Initially there is are nested loops that both depend on n, which implies O(n^2). However the inner loop doesn't iterate through n all the way, since each step increases by the square, making it faster than O(n^2), my best guess would be **O(n \* log base 2( n))**.

c) Since it's a recursive function with just one recursive call that counts down at each time, as N grows to positive infinity, the runtime complexity ends up being linear at **O(n)**.

## Exercise II

You can use a binary search algorithm to find the highest floor where a dropped egg won't break.

1. Go to the middle floor of the building (n / 2) where n is the number of floors.
2. If the egg breaks, turns out you are too high, so go to the middle floor of your current posiion.
   - so the new ceiling becomes your current position (n/ 2), and you want to go to the middle ((ceiling - ground) /2)
3. If the egg doesn't break:
   - it is important you go up one floor (n+1) and check if the egg breaks then, which means you found the max
     - if the egg doesn't break, it means you are still too low, and need to cut your search in half again
     - contrary to step#2, your current position becomes the new ground, while the ceiling stays the same
     - you will want to repeat step 1 where the middle is ((ceiling - ground)/2)
4. Repeat 1 - 3 until you get a sequence where the egg doesn't break, and then breaks after moving one floor up directly.
