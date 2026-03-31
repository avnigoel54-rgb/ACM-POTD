# LeetCode 2. **Add Two Numbers**

## **Approach** -
    - Column-wise addition of two numbers represented as linked lists. 
    - It iterates through both lists, adds corresponding digits along with any carry.
    - It creates new nodes for the sum, and handles any leftover carry at the end.
    
   
## **Code** -
    
```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode * t1=l1;
        ListNode* t2=l2;
        int carry=0;
        ListNode* dummy=new ListNode();
        dummy->val=-1;
        ListNode* curr=dummy;
        while(t1!=NULL or t2!=NULL){
            int sum=carry;
            if(t1)sum+=t1->val;
            if(t2)sum+=t2->val;
            ListNode* neww=new ListNode() ;
            neww->val=sum%10;
            carry=sum/10;
            curr->next=neww;
            curr=curr->next;
            if(t1)t1=t1->next;
            if(t2)t2=t2->next;
        }
        if(carry){
            ListNode* neww=new ListNode();
            neww->val=carry;
            curr->next=neww;
        }
        return dummy->next;
    }
};
```

![Output Screenshot](AvniGoel_31-03-26_Day10.png) 
