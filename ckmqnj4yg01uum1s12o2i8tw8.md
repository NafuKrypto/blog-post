## Simple Truth and Dare game in Python

In a truth & dare game, we usually spin a bottle to pick a person among us. So the main task here is to pick a person's name randomly. We can do that random picking of names with Python and can still play truth and dare virtually.

```
import random

choice = ["Mike","Rita","John","Simon","Oporajita"]

result = random.choice(choice)
print(result)

``` 
In the list "choice" add the names of the players. The random.choice() function will pick the Players name randomly each time.

```
Output:
Oporajita

``` 

```
Output:
Mike
``` 

```
Output:
Simon
``` 

So each time whoever's name comes up they have to pick between Truth and dare and play along with the rest of the rules.

