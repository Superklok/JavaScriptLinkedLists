# JavaScript Intersection of Two Linked Lists

## Challenge:

Given the heads of two singly linked-lists `headA` and `headB`, return the node at which the two lists intersect. If the two linked lists have no intersection at all, return `null`.

Note that the linked lists must retain their original structure after the function returns.

Custom Judge:

The inputs to the judge are given as follows (your program is not given these inputs):

`intersectVal` - The value of the node where the intersection occurs. This is 0 if there is no intersected node.

`listA` - The first linked list.

`listB` - The second linked list.

`skipA` - The number of nodes to skip ahead in `listA` (starting from the head) to get to the intersected node.

`skipB` - The number of nodes to skip ahead in `listB` (starting from the head) to get to the intersected node.

The judge will then create the linked structure based on these inputs and pass the two heads, `headA` and `headB` to your program. If you correctly return the intersected node, then your solution will be accepted.

### 1<sup>st</sup> Example:

`Input: intersectVal = 8, listA = [4,1,8,4,5], listB = [5,6,1,8,4,5], skipA = 2, skipB = 3`
<br/>
`Output: Intersected at '8'`
<br/>
`Explanation: The intersected node's value is 8 (note that this must not be 0 if the two lists intersect).`
<br/>
`From the head of A, it reads as [4,1,8,4,5]. From the head of B, it reads as [5,6,1,8,4,5]. There are 2 nodes before the intersected node in A; There are 3 nodes before the intersected node in B.`
<br/>
`- Note that the intersected node's value is not 1 because the nodes with value 1 in A and B (2nd node in A and 3rd node in B) are different node references. In other words, they point to two different locations in memory, while the nodes with value 8 in A and B (3rd node in A and 4th node in B) point to the same location in memory.`

### 2<sup>nd</sup> Example:

`Input: intersectVal = 2, listA = [1,9,1,2,4], listB = [3,2,4], skipA = 3, skipB = 1`
<br/>
`Output: Intersected at '2'`
<br/>
`Explanation: The intersected node's value is 2 (note that this must not be 0 if the two lists intersect).`
<br/>
`From the head of A, it reads as [1,9,1,2,4]. From the head of B, it reads as [3,2,4]. There are 3 nodes before the intersected node in A; There are 1 node before the intersected node in B.`

### 3<sup>rd</sup> Example:

`Input: intersectVal = 0, listA = [2,6,4], listB = [1,5], skipA = 3, skipB = 2`
<br/>
`Output: No intersection`
<br/>
`Explanation:  From the head of A, it reads as [2,6,4]. From the head of B, it reads as [1,5]. Since the two lists do not intersect, intersectVal must be 0, while skipA and skipB can be arbitrary values.`
<br/>
`Explanation: The two lists do not intersect, so return null.`

### Constraints:

The number of nodes of `listA` is in the `m`.
<br/>
The number of nodes of `listB` is in the `n`.
<br/>
`1 <= m, n <= 3 * 10⁴`
<br/>
`1 <= Node.val <= 10⁵`
<br/>
`0 <= skipA < m`
<br/>
`0 <= skipB < n`
<br/>
`intersectVal` is `0` if `listA` and `listB` do not intersect.
<br/>
`intersectVal == listA[skipA] == listB[skipB]` if `listA` and `listB` intersect.

## Solution:

`const getIntersectionNode = (headA, headB) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let currA = headA,`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`currB = headB;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`while(currA !== currB) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if(!currA) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`currA = headB;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`} else {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`currA = currA.next;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if(!currB) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`currB = headA;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`} else {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`currB = currB.next;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return currA;`
<br/>
`};`
<br/>
<br/>

## Explanation:

I've defined a function called `getIntersectionNode` that takes in two linked lists as parameters, `headA` and `headB`. The purpose of this function is to find the intersection node of the two linked lists and return it.
<br/>

The function begins by initializing two variables, `currA` and `currB`, to the heads of the linked lists `headA` and `headB` respectively.
<br/>

Next, it enters a while loop that continues until `currA` is equal to `currB`, indicating that the intersection node has been found.
<br/>

Inside the while loop, it checks if `currA` is null, which indicates the end of linked list A. If it is null, it sets `currA` to the head of linked list B, as we need to continue traversing list B to find the intersection.
<br/>

If `currA` is not null, it moves `currA` to the next node in linked list A by setting it to `currA.next`.
<br/>

Similarly, it checks if `currB` is null, indicating the end of linked list B. If it is null, it sets `currB` to the head of linked list A, as we need to continue traversing list A to find the intersection.
<br/>

If `currB` is not null, it moves `currB` to the next node in linked list B by setting it to `currB.next`.
<br/>

Once the while loop breaks, indicating that `currA` is equal to `currB` and the intersection node has been found, the function returns `currA` which represents the intersection node.
<br/>

In summary, this function iterates through both linked lists simultaneously, moving to the next node in each list until it finds the intersection node. The intersection node is determined when the two pointers, `currA` and `currB`, are equal.
<br/>
<br/>