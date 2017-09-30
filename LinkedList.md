#### keep adding things for linked list related problem

#### reversing a linked list with two pointers,@hirak, needed for leetcode;
#### prepend and append code

```cpp
//  Definition for singly-linked list.
//struct ListNode {
//     int val;
//    ListNode *next;
//    ListNode(int x) : val(x), next(NULL) {}
//};

class Solution {
    public:
    ListNode* prepend(ListNode* l1, int new_val){
        ListNode* l2 = new ListNode(new_val) ;
        l2->next = l1 ;
        l1 = l2 ;
        return l1 ;
    }
    ListNode* append(ListNode* lastPtr, int new_val){
        ListNode* l2 = new ListNode(new_val) ;
        lastPtr->next = l2 ;
        lastPtr = l2 ; 
        
        return lastPtr ;
    }
    void printAll(ListNode * l1){
        while(l1 != NULL){
            std::cout << l1->val << " ";
            l1 = l1->next ;
        }
        std::cout << "\n" ;
    }
    ListNode* inPlaceReverse(ListNode* l1){
        //copy the start
        if(l1->next == NULL)
            return l1 ;
        ListNode *start = l1 ;
        //create two tmp pointers
        ListNode* prev = NULL ;
        ListNode* next = NULL ;
        //initialize
        do{
            prev = l1 ;
            l1 = (next == NULL)?l1->next:next ;
            next = (next == NULL)?l1->next:next->next ;
            l1->next = prev ;
        }while(next);
        start->next = NULL ;
        return l1 ;
    }
};
```
