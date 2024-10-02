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


LLL = (1/4^3) = 1/64

GGG = (1/2^3) = 1/8

BBB = (1/4^3) = 1/64 

LGB = 1/4 * 1/2 * 1/4 = 1/32

LLB = (1/4^3) = 1/64 

LLG = 1/4 * 1/4 * 1/2 = 1/32

GBB = 1/2 * 1/4 * 1/4 = 1/32

LGG = 1/4 * 1/2 * 1/2 = 1/16 

GGB = 1/2 * 1/2 * 1/4 = 1/16

LLB = (1/4^3) = 1/64

Now taking away our good pivot possibilities,we can add them up together by considering all their possible permutations and multiplying the number above from their possible permutations. 

GGG = 8/64 (8/64 * 1) - this has one possible permutation only being GGG 

LGG = 12/64 (4/64 * 3) - this has three possible permutations being LGG,GLL and GLG

BBG = 12/64 (4/64 * 3 ) -  this has three possible permuations being BGB,GBB and BBG

LGB = 12/64 (2/32 * 6) - this six possible permutaions being LGB,BGL,GBL,GLB,BLG and LBG 

When we add the four together,we get 

8/64 + 12/64 + 12/64 + 12/64 = 44/64

44/64 = 0.6875

This gives us a 68.75% chance to get a good pivot with median of three used which is better compared to the method we used in the slides that gives us a 50% chance. 








Sources: 
https://graphics.stanford.edu/courses/cs161-18-winter/Recitations/section3win2018_withsols.pdf  

TA Ali - helped break down how median of 3 worked and some processes above ^


https://github.com/COSC3020/quicksort-pivot-Dhruv8806 -  viewed the process on how to derive probabilities 


"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
