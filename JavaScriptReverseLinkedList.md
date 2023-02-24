# JavaScript Reverse Linked List

## Challenge:

Given the `head` of a singly linked list, reverse the list, and return the reversed list.

### 1<sup>st</sup> Example:

`Input: head = [1,2,3,4,5]`
<br/>
`Output: [5,4,3,2,1]`

### 2<sup>nd</sup> Example:

`Input: head = [1,2]`
<br/>
`Output: [2,1]`

### 3<sup>rd</sup> Example:

`Input: head = []`
<br/>
`Output: []`

### Constraints:

The number of nodes in the list is the range `[0, 5000]`.
<br/>
`-5000 <= Node.val <= 5000`

## Solution:

`const reverseList = (head) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let backward = null,`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`forward  = head;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`while(forward) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let n = forward.next;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`forward.next = backward;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`backward     = forward;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`forward      = n;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return backward;`
<br/>
`};`
<br/>
<br/>