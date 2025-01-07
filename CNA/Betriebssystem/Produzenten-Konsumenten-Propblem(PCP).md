Als PCP Problem bezeichnet man ein Problem der [[Interprocess Communication]]. Dabei geht es darum das mehrere [[CNA/Betriebssystem/Prozesse]] auf gemeinsame Daten zugreifen und zwar in dem die einen [[CNA/Betriebssystem/Prozesse]] diese Daten erzeugen (produce) und die anderen diese Daten verbrauchen (consume). 

Es wird auch das [[Bounded Buffer]] Problem genannt

![[PCP Problem.png]]

# Code Beispiel
````c
# define N 100                             /* number of slots in the buffer */  
typedef int semaphore;                     /* semaphores are a special kind of int */  
semaphore mutex = 1;                       /* controls access to critical region */  
semaphore empty = N;                       /* counts empty buffer slots */  
semaphore full = 0;                        /* counts full buffer slots */  
void producer(void)  
	{  
		int item;  
		while (TRUE) {                     /* TRUE is the constant 1 */  
			item = produce item( );        /* generate something to put in buffer */  
			down(&empty);                  /* decrement empty count */  
			down(&mutex);                  /* enter critical region */  
			inser t item(item);            /* put new item in buffer */  
			up(&mutex);                    /* leave critical region */  
			up(&full);                     /* increment count of full slots */  
}  
	}  
void consumer(void)  
	{  
		int item;  
		while (TRUE) {                      /* infinite loop */  
			down(&full);                    /* decrement full count */  
			down(&mutex);                   /* enter critical region */  
			item = remove item( );          /* take item from buffer */  
			up(&mutex);                     /* leave critical region */  
			up(&empty);                     /* increment count of empty slots */  
			consume item(item);             /* do something with the item */  
	}  
}  
```