# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.


Using our pivot from the first element chosen on the leftmost side, we have a 50% chance of choosing a good pivot. From the block shown on slide 34 from the powerpoint, we can we divide it into three blocks, the left most being 1/4, the middle being 1/2 and the right most being 1/4 to get a probability of 1 together. Giving each of these a variable for each respective block, where L represents lower than pivot (left),G being good pivot (middle) and B being bigger than pivot (right). 

L = 1/4
G = 1/2
B = 1/4

We can consider our bad cases where our median pivot would not work. 

We have multiple cases where this is the case:

BBB - (1/4)^3

LLL - (1/4)^3

GLL - 1/2 * (1/4)^2 

GBB - 1/2 * (1/4)^2 

Now we are able to add these up and subtract them from 1.

BBB - one permutation so just 1/64  from  (1/4)^3

LLL - one permutation so just 1/64 from (1/4)^3

GLL - 3 permutations so  (1/2) * (1/4)^2 = 3/32

GBB - 3 permutations so  (1/2) * (1/4)^2 = 3/32 

LBB - 3 permutations so (1/4)^3 = 3/64

BLL - 3 permuations so (1/4)^3 = 3/64 


3/32 + 3/32 + 1/64 + 1/64 + 3/64 + 3/64 = 20/64

20/64 = .6875

1 - .3125 = 0.6875



This ends up in a chance of 68.75% chance choosing a good pivot with the median of three pivots compared to the slide method which had a 50% success rate.


* my calculations were way off and I was missing 2 combinations from second try. 




Sources: 
https://graphics.stanford.edu/courses/cs161-18-winter/Recitations/section3win2018_withsols.pdf  

TA Ali - helped break down how median of 3 worked and some processes above ^


https://github.com/COSC3020/quicksort-pivot-Dhruv8806 -  viewed the process on how to derive probabilities 


"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
