# JavaScript Add Two Numbers

## Challenge:

You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number `0` itself.

### 1<sup>st</sup> Example:

`Input: l1 = [2,4,3], l2 = [5,6,4]`
<br/>
`Output: [7,0,8]`
<br/>
`Explanation: 342 + 465 = 807.`

### 2<sup>nd</sup> Example:

`Input: l1 = [0], l2 = [0]`
<br/>
`Output: [0]`

### 3<sup>rd</sup> Example:

`Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]`
<br/>
`Output: [8,9,9,9,0,0,0,1]`

### Constraints:

The number of nodes in each linked list is in the range `[1, 100]`.
<br/>
`0 <= Node.val <= 9`
<br/>
It is guaranteed that the list represents a number that does not have leading zeros.

## Solution:

`const addTwoNumbers = (l1, l2) => {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`let list  = new ListNode(0),`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`head  = list,`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum   = 0,`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`carry = 0;`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`while(l1 !== null || l2 !== null || sum > 0) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if(l1 !== null) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum = sum + l1.val;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`l1 = l1.next;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if(l2 !== null) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum = sum + l2.val;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`l2 = l2.next;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`if(sum >= 10) {`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`carry = 1;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum = sum - 10;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`head.next = new ListNode(sum);`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`head = head.next;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`sum = carry;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`carry = 0;`
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`}`
<br/>
<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`return list.next;`
<br/>
`};`
<br/>
<br/>

## Explanation:

I've written a function called `addTwoNumbers` that takes in two linked lists as parameters (`l1` and `l2`). The purpose of this function is to add the numbers represented by the linked lists and return a new linked list representing the sum.
<br/>

Inside the function, several variables are initialized: `list`, `head`, `sum`, and `carry`. `list` and `head` are set to a new ListNode object with a value of 0, which will be the head of the resulting linked list. `sum` and `carry` are set to 0 to keep track of the current sum and any carry values.
<br/>

The function enters a while loop that continues until both `l1` and `l2` are null and the `sum` is greater than 0. This ensures that all digits of both linked lists are processed, as well as any remaining carry values.
<br/>

Inside the loop, it checks if `l1` is not null. If it is not null, the value of `l1` is added to the `sum`, and `l1` is moved to the next node.
<br/>

Similarly, it checks if `l2` is not null. If it is not null, the value of `l2` is added to the `sum`, and `l2` is moved to the next node.
<br/>

After adding the values, it checks if the `sum` is greater than or equal to 10. If it is, the `carry` is set to 1, and 10 is subtracted from the `sum` to keep the value within a single digit.
<br/>

It then creates a new ListNode with the value of `sum` and assigns it to `head.next`, effectively adding a new node to the resulting linked list.
<br/>

The `head` is moved to the next node to prepare for the next iteration.
<br/>

The `sum` is updated with the value of `carry`, and the `carry` is reset to 0 for the next calculation.
<br/>

The loop continues until the while loop condition is no longer true, ensuring all digits and carry values are processed.
<br/>

Finally, the function returns the next node of `list`, which is the head of the resulting linked list.
<br/>

In summary, this function performs digit-by-digit addition of two linked lists, taking into account carry values, and returns a new linked list representing the sum.
<br/>
<br/>