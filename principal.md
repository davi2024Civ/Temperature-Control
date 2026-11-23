## ok, lets start
First, we are developing aproject of a Temperature Control
<img width="1600" height="900" alt="WhatsApp Image 2026-11-22 at 18 55 21" src="https://github.com/user-attachments/assets/0df6be8c-0d6b-4b69-a1e6-7e6c22b7e5d7" />
Now, we have codes in Arduino and MatLab to develop all this project.

First, in *datos.txt* i collected all the temperature values, with a sample time of 1 second.

Then print the response: (*graph1.m*)
<img width="684" height="620" alt="image" src="https://github.com/user-attachments/assets/a9f13496-dffe-4e6d-9636-0c47603018cc" />
(This is the response of the code 40porciento.imo)
As we can see we have something similar like a funciont of first order.

Now, we have to know the value of L,K,T
- L is calculated just by inspection, is the delay of the response.
- T is the constant of time, so it´s gonna be the settling time divided by4. My settling time is aprox 425.
- K is the difference between the settling value and the start point.
- All these things can be viewd in *MathModelPlan.m*
<img width="698" height="628" alt="image" src="https://github.com/user-attachments/assets/f3f6b3e2-ad10-49f4-ade8-b11638f9b2e9" />
The value of K has to be divided by 40 because it is the percent of the input value. So its units are C/%
Then, I have:
K =       13.905/40
T =                 106.25
L = 10

I noticed that, we can also consider the constant of time like the time that the maximum slope of the function take from the start point to the settling value. But we have to work eith a filter, because we have discrete points.

Now we have our plant.
$`a_1 + a_2 = a_3`$
