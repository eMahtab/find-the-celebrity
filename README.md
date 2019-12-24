# Find the celebrity

```java
public int findCelebrity(int n) {
    int probableCelebrity = 0;
    // We find a 'i' who is known by everyone, but doesn't know anyone.
    for (int i = 1; i < n; i++) {
	 if (knows(probableCelebrity, i))
		probableCelebrity = i;
    }
     
     /* To make sure the value we found out is actually the celebrity, we
	check if probableCelebrity knows none and everyone knows probableCelebrity.
      */
    
    for (int i = 0; i < n; i++) {
	  if (i != probableCelebrity && (knows(probableCelebrity, i) || !knows(i, probableCelebrity)))
		return -1;
    }

    return probableCelebrity;
}
```
