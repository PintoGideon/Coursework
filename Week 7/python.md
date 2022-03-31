### Dictionaries

When you have a collection of data, the most natural choice that Python developers reach for first has got to be a list.

Let's look at two different algorithms.

We start


```python

import collections
import datetime
import random
import sys

DataPoint= collections.namedtuple("DataPoint", "id x y temp quality")
 
def main():
    print("Creating Data....", end='')
    sys.stdout.flush()

    data_list=[] #500,000 datapoint items
    random.seed(0)
    for d_id in range(5000000):
        x=random.randint(0,1000)
        y=random.randint(0,1000)
        temp=random.randint(-10,50)
        quality=random.random()
        data_list.append(DataPoint(d_id,x,y,temp,quality))

    print("done.")
    sys.stdout.flush()

    ### Create a set of random IDs to locate without duplication

    interesting_ids={random.randint(0,len(data_list)-1) for _ in range(0,100)}

    print("Creating {} interesting Ids to seek.".format(len(interesting_ids)))

    # locating data in list

    print("Locating data in list....", end='')
    sys.stdout.flush()

    # we are going to start a little timer, figure at the end what the total seconds pass were, and during that time, we want to go and actually pull out the interesting points that correspond to the interesting ids. So we are going to go for each interesting id, emember, it's about a 100, we are going to say "find the point in the list like so,  and then add it", and if we look quickly at this, you can see we just go through each item on the list  and if the item matches the id we are looking for, we are done.

    t0=datetime.datetime.now()
    interesting_points=[]

    for i in intersting_ids:
        pt=find_point_by_id_in_list(data_list,i)
        interesting_points.appent(pt)

    t1= datetime.datetime.now()
    dt_list=(t1-t0).total_seconds()

    print("done.")
    sys.stdout.flush()

    print("dt: {} sec".format(dt_list))

    #Remember, it's only the locating data in the list part that is actually timed. All right, so this took 7.9 seconds
    print(interesting_points)



def find_point_by_id_in_list(data_list, i):
    for d in data_list:
        if d.id == i:
            return d

    return None


if __name__ == '__main__':
    main()

```

So we start out with a list of data, here you can see in our example
we are going to be using half of million items, so we are calling a data list and it's going to contain some rich objects with multiple values or measurements - details aren't actually important.

Then, suppose for some reason we have done some computation and we've come up with a hundred pieces of data, we would like to go look up in our list. So we are going to go loop over each of those 100 and then we are going to find the item in the list.

We can't just use interesting "item in list" in operator, because we actually have to filter on a particular value, what we did instead is wrote this method called `find_point_by_id_in_list` and it just walks through the list, it compares the id it's looking for against the ids that it finds in the list, as soon as it finds the match, it returns that one, it's assuming to be unique and then it appends it to this interesting_points. So this is one version of the algorithm.

The other one is well, maybe we could do a little bit better
if we actually used a dictionary.

```python
to = datetime.datetime.now()

# Create dictionary via comprehension key=id
#so the first thing we want to do is create a dictionary, before we had data_list, now we are going to have data_dict

# we want to map for each item in the dictionary the id to the actual object.  So, we create set and dictionary comprehensions like so but the difference is we have a "key:value" for the dictionaries where we just have the value for sets.

# You kind of have to write this in reverse, I am going to name the elements we are going to look at "d", so I am going to say "d.id", maps the "d for d in data_list", right, so this is going to create a dictionary of all half a million items and mapping the id to the actual value.

data_dict={d.id: d for d in data_list}

interesting_points.clear()
#"for id", we call it "d.id" so it doesn't conflict with the id built in
for d_id in interesting_ids:
    d= data_dict[d_id]
    interesting_points.append(d)

    
# So now, let's start a little timer,
t1= datetime.datetime.now()
dt_dict=(t1-t0).total_seconds()

# This is 0.000069 seconds.


print("Done")
sys.stdout.flush()

```

So if we wrote it like this, here we have a dictionary of half a million of items, again the same dynamically discovered 100 interesting points, and instead of doing this lookup by walking through the items, we can actually map the id to the objects that we are looking for so we can just index into the dictionary.

Obviously, indexing into the dictionary is going to be faster,
but possibly the computation, the building of the dictionary itself might be way slower, if we are going to do this a 100 times, we have half a million items, right, it's much more complicated to generate a dictionary with half a million items than it is a list.

If you saw this statement and wanted me to explain it, 


```python
interesting_ids={random.randint(0,len(data_list)-1) for _ in range(0,100)}

# we have the set of approximately 100 ids,
```

What we are building here is a set using something called a set comprehension and each item in the set is going to be a random number between zero and the length of that list which is half a million, so quite a large range there. And we are just going to range across zero to 100. In Python, when you are looping across something like this range set here or you are possibly unpacking a tuple and there is only a few of the values, not all the values you care about, it's Pythonic to use the underscore for the variable name to say.

We found an algorithm that is actually easier to use than writing our silly list lookup and it took literally one line of a dictionary comprehension, that's a beautiful combination of how dictionaries work for performance, bringing together these Pythonic ideas like dictionary comprehensions and so on, it made our algorithm both easier and dramatically faster. What if we had to create this dictionary just one time to do this work?

If you went through that and felt, what the heck was that? I can explain better. This was just to give you a glimpse into a world of coding where the learning never stops