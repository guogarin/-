/*
    剑指 Offer 06. 从尾到头打印链表：输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。

    示例 1：
        输入：head = [1,3,2]
        输出：[2,3,1]


    限制： 0 <= 链表长度 <= 10000
*/ 

/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */

#include<vector>
using namespace std;

class Solution {
public:
    vector<int> reversePrint(ListNode* head) {
        int num =0;
        ListNode* cur_node = head;
        vector<int>result;
        if(head == NULL){
            return result;
        }
        do{   
            ++num;
            result.push_back(cur_node->val);
            cur_node = cur_node->next;
        }while(cur_node != NULL);

        if(num > 1){
            int j = num/2;
            for(int i = 0; i < j; i++){
                swap(result[i], result[num-i-1]);
            }
        }
        return result;
    }
};