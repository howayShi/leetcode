## 203-移除链表元素

涉及到的一个链表结构体：
```
struct ListNode {
       int val;    //定义val变量值，存储节点值
       struct ListNode *next;   //定义next指针，指向下一个节点，维持节点连接
  }
```
#### 题解-2022.4.16
```
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        struct ListNode* dummyHead = new ListNode(0, head);
        struct ListNode* temp = dummyHead;
        while (temp->next != NULL) {
            if (temp->next->val == val) {
                temp->next = temp->next->next;
            } else {
                temp = temp->next;
            }
        }
        return dummyHead->next;
    }
};
```





