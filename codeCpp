#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#include <optional>
using namespace std;

/*
    数组题1:  二分法查找元素位置， 非递归实现，时间复杂度为 n
*/
class Solution {
public:
    int search(vector<int>& nums, int target) {
        
        int left = 0;
        int right = nums.size() - 1;

        while (left <= right)
        {
            int mid = (left + right) / 2;
            if (target < nums[mid])
            {
                right = mid - 1;
            }else if (target > nums[mid])
            {
                left = mid + 1;
            }else{
                return mid;
            }
            
        }
        
        return -1;

    }
};

/*
 数组题2：快慢指针  解决两个for循环问题（时间复杂度为 n2）   ->   时间复杂度为  n    
 原地查找给定目标元素，并将其删掉，非目标元素前移
*/
class Solution2 {
public:
    int removeElement(vector<int>& nums, int val) {
        
      int slowIndex = 0;
        for (int fastIndex = 0; fastIndex < nums.size();  fastIndex++) {
            if (val != nums[fastIndex]) {
                nums[slowIndex++] = nums[fastIndex];
            }
        }
        return slowIndex;

    }
};


/*
数组题3：将给定非递减数组元素平方后按照非递减排列
1、有序数组的平方   暴力解法    时间复杂度  n + n*logn    ->   n*logn
2、双指针法   首尾指针解决大小比较问题
*/

class Solution3
{
private:
    /* data */
public:
    Solution3
(/* args */);
    ~Solution3
();

    // 暴力解法
    vector<int> sortedSquares(vector<int>& nums) {
        
        for (auto i = nums.begin(); i != nums.end(); i++)
        {
        *i = (*i) * (*i);
        }

        sort(nums.begin(), nums.end());

        return nums;

    }

    // 双指针实现
    vector<int> sortedSquares2(vector<int> &nums) {
        
        int i = 0;
        int j = nums.size() - 1;
        int k = nums.size() - 1;

        vector <int> res(nums.size(), 0);
        
        while (i <= j)
        {
            
            if (nums[i] * nums[i] > nums[j] * nums[j])
            {
                res[k--] = nums[i] * nums[i];
                i++;
            }else{
                res[k--] = nums[j] * nums[j];
                j--;
            }
            
        }

        return res;

    }
};

Solution3::Solution3(/* args */)
{
}

Solution3::~Solution3()
{
}


template <typename E>
void Print(const vector <E> nums){

    for (auto i = nums.begin(); i != nums.end(); i++)
    {
        cout << *i << endl;
    }

}


/*
    数组题4：长度最小的子数组     回溯思想   递归解决     "注意"  ：   大于等于目标值    连续子数组   所以利用 “滑动窗口” 方法  
    1、暴力解法  时间复杂度   n2
    2、滑动窗口  时间复杂度   2n
*/
class Solution4
{
private:
    /* data */
public:
    Solution4(/* args */);
    ~Solution4();


    int minSubArrayLen(int target, vector<int>& nums) {
        
        if (nums.size() == 1 && nums[0] != target)
        {
            return 0;
        }
        
        if (nums.size() == 1 && nums[0] == target)
        {
            return 1;
        }


        int sum = 0;
        int res = 0;
        int index = 0;
        vector<int> temp;
        vector<int> result;


        dfs(target, nums, temp, sum, result, index);
        
        sort(result.begin(), result.end());

        if ( result.size() == 0)
        {
            return 0;
        }
        
        res = result[0];

        cout << result.size() << endl;
        return res;

    }

    void dfs(int target, vector<int>& nums, vector<int> &temp, int sum, vector<int> &result, int index){

      
       
        if ( sum == target)
        { 
            
            result.push_back(temp.size());
            cout << "----------------------" << endl;
            Print <int> (temp);
            return;
        }
        


        for (auto i = index; i < nums.size(); i++)
        {
            temp.push_back(nums[i]);
            index += 1;
            sum += nums[i];


            dfs(target, nums, temp, sum, result, index);

            temp.pop_back();
            sum -= nums[i];


            
        }


    }



};

Solution4::Solution4(/* args */)
{
}

Solution4::~Solution4()
{
}


/*
    数组题5：螺旋矩阵   
    给你一个正整数 n ，生成一个包含 1 到 n2 所有元素，且元素按顺时针顺序螺旋排列的 n x n 正方形矩阵 matrix 


    1、可以尝试回溯   顺时针 定义  移动顺序优先级    右 -> 下 -> 左  -> 上    定义一个矩阵标记 该位置是否已有元素  或者 是否是边界  （回溯实现）
    2、本方法实现
*/
class Solution5
{
private:
    /* data */
public:
    Solution5(/* args */);
    ~Solution5();

    vector<vector<int>> generateMatrix(int n) {

        // 初始化二维vector   方法一
        // vector<vector<int>> res(n);

        // for (int i = 0; i < res.size(); i++)
        // {
        //     res[i].resize(n);
        // }


        // 初始化二维vector   方法二
        vector<vector<int>> res(n, vector<int>(n, 0));

        

        int l = 0, r = n - 1, t = 0, b = n - 1;
        int start = 1;
        int end = n * n;


        while (start <= end)
        {
            
            for (int i = l; i <= r; i++)
            {
                res[t][i] = start ++;
            }
            t ++;

            for (int i = t; i <= b; i++)
            {
                res[i][r] = start ++; 
            }
            
            r --;

            for (int i = r; i >= l; i--)
            {
                res[b][i] = start ++;
            }
            
            b --;


            for (int i = b; i >= t; i--)
            {
                res[i][l] = start ++;
            }
            
            l ++;

        }
        


        return res;
    }

};

Solution5::Solution5(/* args */)
{
}


Solution5::~Solution5()
{
 
}


/*
    链表题1 ： （简单类型)   移除链表元素   
    给你一个链表的头节点 head 和一个整数 val ，请你删除链表中所有满足 Node.val == val 的节点，并返回 新的头节点 。

    可以采用递归实现，也可以采用while循环实现
*/

/*
 Definition for singly-linked list.
 */
struct ListNode {
int val;
ListNode *next;
ListNode() : val(0), next(nullptr) {}
ListNode(int x) : val(x), next(nullptr) {}
ListNode(int x, ListNode *next) : val(x), next(next) {}

};

class Solution6
{
private:
    /* data */
public:
    Solution6();
    ~Solution6();

    // 非递归实现
    ListNode* removeElements(ListNode* head, int val);

};

ListNode* Solution6 ::removeElements(ListNode* head, int val){
        

        while (head != NULL && head->val == val)
        {
            ListNode* temp = head;
            head = head->next;
            delete temp;
        }
        

        ListNode* temp = head;
        while (temp != NULL && temp->next != NULL)
        {
            if (temp->next->val == val)
            {
                ListNode* temp2 = temp->next;
                temp->next = temp->next->next;
                delete temp2;
            }else{
                temp = temp->next;
            }
            
        }
        
        return head;
}

Solution6::Solution6(){};
Solution6::~Solution6(){};



/*
    链表题2：设计链表，实现查询  首插  尾插   中间插入   删除  功能

*/


class MyLinkedList
{
private:
    /* data */
    ListNode* head;
public:
    MyLinkedList();
    ~MyLinkedList();

    int get(int index);
    
    void addAtHead(int val);
    
    void addAtTail(int val);
    
    void addAtIndex(int index, int val);
    void deleteAtIndex(int index);

    ListNode* getData();

};

ListNode* MyLinkedList::getData(){
    return head;
}

MyLinkedList::MyLinkedList()
{   
    head = new ListNode();

    // int arr[0] = {};

    // ListNode* temp = head;

    // for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    // {
    //     while (true)
    //     {
    //         if (temp->next == NULL)
    //         {
    //             temp->next = new ListNode(arr[i]);
    //             break;
    //         }else{
    //             temp = temp->next;
    //         }
            
    //     }
        
    // }
    
}

MyLinkedList::~MyLinkedList()
{
}


int MyLinkedList::get(int index){
    ListNode* temp = head;

    int count = 0;
    while (temp != NULL)
    {   
        
        if (count == index)
        {   
            return temp->val;
        }
        temp = temp->next;
        count ++;
    }

    return -1;

}

void MyLinkedList::addAtHead(int val) {
    
    if (head != NULL)
    {
        ListNode* newHead = new ListNode(val);
        newHead->next = head;
        head = newHead;
    }else{
        head->val = val;
    }
    
}


void MyLinkedList::addAtTail(int val) {
    
    ListNode* temp = head;

    if (temp == NULL)
    {
        head->val = val;
    }
    

    while (temp->next != NULL)
    {
        
        temp = temp->next;
    }

    temp->next = new ListNode(val);

    
}


void MyLinkedList::addAtIndex(int index, int val) {
    ListNode* temp = head;

    if (index <= 0)
    {
        if (head != NULL)
        {
            ListNode* newHead = new ListNode(val);
            newHead->next = head;
            head = newHead;
            return;
        }else{
            head->val = val;
        }
    }
    
    int count = 0;

    bool flag = false;
    while (temp->next != NULL)
    {   
        if (count == index - 1)
        {   
            ListNode* addNode = new ListNode(val);
            ListNode* tt = temp->next;
            temp->next = addNode;
            addNode->next = tt;
            flag = true;
            return;
        }
        temp = temp->next; 
        count ++;
    }

   temp->next = new ListNode(val);

}


void MyLinkedList::deleteAtIndex(int index) {

    ListNode* temp = head;

    if (index == 0 && temp != NULL)
    {
        ListNode* temp2 = head;
        head = head->next;
        delete temp2;
    }

    int count = 1;
    while (temp->next != NULL) 
    {
       
        if (count == index)
        {   
            ListNode* ss = temp->next;
            temp->next = temp->next->next;
            delete ss;
        }else{
            temp = temp->next;
        }
         count ++;
        
    }
    
    
}



/*
    打印单链表
*/

static void printLinkedList(ListNode* head){

    if (head == NULL)
    {
        return;
    }

    ListNode* temp = head;

    while (temp != NULL)
    {
        std::cout << temp->val << "    ";
        temp = temp->next;
    }
    std::cout << endl;

} 


class Solution7
{
private:
    ListNode* head;
public:
    Solution7(/* args */);
    ~Solution7();

    ListNode* reverseList(ListNode* head);

    ListNode* getDate();

};

ListNode* Solution7::getDate(){
    return head;
}
Solution7::Solution7(/* args */)
{   
    head = new ListNode();


    int arr[5] = {1, 2, 3, 4, 5};

    ListNode* temp = head;

    for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr[i]);
                break;
            }else{
                temp = temp->next;
            }
            
        }
        
    }
}

Solution7::~Solution7()
{

}


/*
    链表题3：反转链表
*/
ListNode* Solution7::reverseList(ListNode* head) {
    
    ListNode* pre = NULL;
    ListNode* cur = head;
    ListNode* temp = NULL;
    while (cur != NULL)
    {
        temp = cur->next;
        cur->next = pre;

        pre = cur;
        cur = temp;
    }
    
        
    return pre;
    
}


/*
    链表题4：两两交换链表中的节点
*/

class Solution8
{
private:
    ListNode* head;
public:
    Solution8(/* args */);
    ~Solution8();


    ListNode* swapPairs(ListNode* head);

    ListNode* setDate();
};

ListNode* Solution8::setDate(){
    return head;
}



Solution8::Solution8(/* args */)
{
    head = new ListNode();

    ListNode* temp = head;

    int  arr [4] = {1, 2, 3, 4};
    for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr[i]);
                break;
            }else{
                temp = temp->next;
            }
            
        }
        
    }
    head = head->next;

}

Solution8::~Solution8()
{
}

ListNode* Solution8::swapPairs(ListNode* head){
    
    ListNode* virtualHeadNode = new ListNode(0);

    virtualHeadNode->next = head;

    ListNode* cur = virtualHeadNode;
    
    while (cur->next != NULL && cur->next->next != NULL)
    {   
        ListNode* temp = cur->next;

        ListNode* temp2 = cur->next->next->next;

        cur->next = cur->next->next;

        cur->next->next = temp;

        cur->next->next->next = temp2;
        

        cur = cur->next->next;
    }
    
    printf("--------------");
    printLinkedList(head);
    head = virtualHeadNode->next;
    return virtualHeadNode->next;
}

/*
    链表题5：删除链表的倒数第 N 个节点， 并返回链表头节点
*/
class Solution9
{
private:
    ListNode* head;
public:
    Solution9(/* args */);
    ~Solution9();

    ListNode* removeNthFromEnd(ListNode* head, int n);
    ListNode* removeNthFromEnd2(ListNode* head, int n);

    ListNode* getDate();
};

Solution9::Solution9(/* args */)
{
    head = new ListNode();

    ListNode* temp = head;

    int  arr [5] = {1, 2, 3, 4, 5};
    for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr[i]);
                break;
            }else{
                temp = temp->next;
            }
            
        }
        
    }
    head = head->next;
}

Solution9::~Solution9()
{
}

/*
    思路一： 先遍历一遍链表，获取链表长度，再遍历一次删除指定的节点

    思路二： 定义fast指针和slow指针，初始值为虚拟头节点
*/
ListNode* Solution9::removeNthFromEnd(ListNode* head, int n){
    
    // 思路一：  加入头节点
    if (head == nullptr)
    {
        return head;
    }
    
    ListNode* nullHead = new ListNode(0);

    nullHead->next = head;
    
    ListNode* temp = nullHead;

    int count = 0;
    while (temp->next != nullptr)
    {
        count ++;
        temp = temp->next;
    }

    temp = nullHead;

    int c = 0;
    while (temp->next != nullptr)
    {
        if (n > count)
        {
            break;
        }

        if (c == count - n)
        {
            temp->next = temp->next->next;
            break;
        }
        
        temp = temp->next;
        c ++;

    }
    
    return nullHead->next;
 
};

ListNode* Solution9::removeNthFromEnd2(ListNode* head, int n){

    // 思路二： 双指针
    ListNode* dummyHead = new ListNode(0);
    dummyHead->next = head;
    ListNode* slow = dummyHead;
    ListNode* fast = dummyHead;
    while(n-- && fast != NULL) {
        fast = fast->next;
    }
    fast = fast->next; // fast再提前走一步，因为需要让slow指向删除节点的上一个节点
    while (fast != NULL) {
        fast = fast->next;
        slow = slow->next;
    }
    slow->next = slow->next->next; 
    
    return dummyHead->next;
}


ListNode* Solution9::getDate(){
    return head;
}


/*
    链表题6：链表相交
*/
class Solution10
{
private:
    ListNode* headA;
    ListNode* headB;
public:
    Solution10(/* args */);
    ~Solution10();

    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB);

    pair<ListNode*, ListNode*> getData();



};
pair<ListNode*, ListNode*> Solution10::getData(){
    return make_pair(this->headA, this->headB);
};

static void printPairLinkedList(pair<ListNode*, ListNode*> res){

    if (res.first == NULL)
    {
        return;
    }

    ListNode* temp = res.first;

    while (temp != NULL)
    {
        std::cout << temp->val << "    ";
        temp = temp->next;
    }
    std::cout << endl;
    std::cout << "===========================" << endl;


    if (res.second == NULL)
    {
        return;
    }

    temp = res.second;

    while (temp != NULL)
    {
        std::cout << temp->val << "    ";
        temp = temp->next;
    }
   
}

Solution10::Solution10(/* args */)
{
    headA = new ListNode();

    ListNode* temp = headA;

    int  arr [5] = {4, 1, 8, 4, 5};
    for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr[i]);
                break;
            }else{
                temp = temp->next;
            }
            
        }
        
    }
    headA = headA->next;

    headB = new ListNode();

    temp = headB;

    int  arr2 [6] = {5, 0, 1, 8, 4, 5};
    for (int i = 0; i < sizeof(arr2) / sizeof(arr2[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr2[i]);
                break;
            }else{
                temp = temp->next;
            }
            
        }
        
    }
    headB = headB->next;

}

Solution10::~Solution10()
{
}

ListNode* Solution10::getIntersectionNode(ListNode *headA, ListNode *headB){

        // 添加头节点
        ListNode* newHeadA = new ListNode(0);
        newHeadA->next = headA;
        ListNode* newHeadB = new ListNode(0);
        newHeadB->next = headB;
        
        ListNode* temp1 = newHeadA;
        ListNode* temp2 = newHeadB;

        int lenA = 0;
        int lenB = 0;
        while (temp1->next != nullptr)
        {
            temp1 = temp1->next;
            lenA ++;
        }

        while (temp2->next != nullptr)
        {
            temp2 = temp2->next;
            lenB ++;
        }
        std:: cout << endl;
        temp1 = newHeadA;
        temp2 = newHeadB;
        if (lenA == lenB)
        {
            while (temp1->next != nullptr && temp2->next != nullptr)
            {
                if (temp1->next->val == temp2->next->val)
                {
                    return temp1->next;
                }else{
                    temp1 = temp1->next;
                    temp2 = temp2->next;
                }  
            }
            
        }else if (lenA < lenB)
        {    
            
            int count = 0;
            // 移动到相等位置
            while (temp2->next != nullptr)
            {
                if (count == lenB - lenA)
                {
                    break;
                }else{
                    temp2 = temp2->next;
                }
                count ++;
            }

            // 判断相交点
            ListNode* temp3 = temp2;
            while (temp1->next != nullptr && temp3->next != nullptr)
            {
                if (temp1->next->val == temp3->next->val)
                {   
                    return temp1->next;
                }else{
                    temp1 = temp1->next;
                    temp3 = temp3->next;
                }
            }

            
        }else{
            int count = 0;
            while (temp1->next != nullptr)
            {
                if (count == lenA - lenB)
                {
                    break;
                }else{
                    temp1 = temp1->next;
                }
                count ++;
            }

            ListNode* temp4 = temp1;
            while (temp2->next != nullptr && temp4->next != nullptr)
            {
                if (temp2->next->val == temp4->next->val)
                {
                    return temp2->next;
                }else{
                    temp2 = temp2->next;
                    temp4 = temp4->next;
                }
                
            }

        }
    
        return nullptr;

};

class Solution11
{
private:
    ListNode* head;
public:
    Solution11(/* args */);
    ~Solution11();

    ListNode *detectCycle(ListNode *head);
    
    ListNode* getData();

};

ListNode* Solution11::getData(){
    return head;
}

Solution11::Solution11(/* args */)
{
    head = new ListNode();

    ListNode* temp = head;

    int  arr [4] = {3, 2, 0, -4};
    for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++)
    {
        while (true)
        {
            if (temp->next == NULL)
            {
                temp->next = new ListNode(arr[i]);
                break;
            }else{
                temp = temp->next;
            }
        } 
    }
    temp->next = head->next->next;
    
}

Solution11::~Solution11()
{

}

ListNode * Solution11::detectCycle(ListNode *head){
    head = head->next;
    ListNode* fast = head;
    ListNode* slow = head;

    while (fast != nullptr && fast->next != nullptr)
    {
        slow = slow->next;
        fast = fast->next->next;

        if (slow == fast)
        {
            ListNode* index1 = fast;
            ListNode* index2 = head;

            while (index1 != index2)
            {
                index1 = index1->next;
                index2 = index2->next;
            }
            
            return index2;
        }
        
    }
    return nullptr;
}


/*

    哈希表题1：有效的字母异位词
*/


class Solution12
{
private:
    /* data */
public:
    Solution12(/* args */);
    ~Solution12();

    bool isAnagram(string s, string t);

};

/*
    需要把字符映射到数组也就是哈希表的索引下标上，因为字符a到字符z的ASCII是26个连续的数值，
    所以字符a映射为下标0，相应的字符z映射为下标25。
    再遍历 字符串s的时候，只需要将 s[i] - ‘a’ 所在的元素做+1 操作即可，并不需要记住字符a的ASCII，
    只要求出一个相对数值就可以了。 这样就将字符串s中字符出现的次数，统计出来了。
*/
bool Solution12::isAnagram(string s, string t){
    
    int record[26] = {0};

    for (int i = 0; i < s.size(); i++)
    {
        record[s[i] - 'a'] ++;
    }

    for (int i = 0; i < t.size(); i++)
    {
        record[t[i] - 'a'] --;
    }
    
    for (int i = 0; i < sizeof(record) / sizeof(record[0]); i++)
    {
        if (record[i] != 0)
        {
            return false;
        }
        
    }
    
    return true;
}
Solution12::Solution12(/* args */)
{
}

Solution12::~Solution12()
{
}

/*
    哈希表题2：两个数组的交集
*/
#include <set>
class Solution13
{
private:
    /* data */
public:
    Solution13(/* args */);
    ~Solution13();
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2);

};

vector<int> Solution13::intersection(vector<int>& nums1, vector<int>& nums2){
    vector<int> res;

    set<int> temp(nums1.begin(), nums1.end());
    set<int> temp2(nums2.begin(), nums2.end());
    // res.resize(std::min(temp.size(), temp2.size()));      使用 back_inserter 不用resize 调用 back_inserter，返回一个插入迭代器，这个迭代器会调用push_back添加元素到容器中
    std::set_intersection(temp.begin(), temp.end(), temp2.begin(), temp2.end(), std::back_inserter(res));
     
    return vector<int>(res.begin(), res.end());


};
Solution13::Solution13(/* args */)
{
}

Solution13::~Solution13()
{
}

/*
    哈希表题3：快乐数

*/

class Solution14
{
private:
    /* data */
public:
    Solution14(/* args */);
    ~Solution14();

    bool isHappy(int n);
};

#include <unordered_set>
bool Solution14::isHappy(int n){


    // 创建一个hash表，如果存在一个已经记录的数字则存在循环，则返回false
    unordered_set<int> judge; 

    while (true)
    {   
        if (judge.find (n) != judge.end())
        {
            return false;
        }else{
            
            judge.insert(n);
        }
        
        // 针对单个数字
        if (n == 1)
        {
            return true;
        }

        // 针对多个数字，取出每一个数字
        vector<int> temp;
        while ( n / 10 != 0 )
        {   
            int temp2 = n % 10; 
            temp.push_back(temp2);
            n = n / 10;
        }
        temp.push_back(n);
        
        int res = 0;  // 计算每次的结果，更新n值
        for (auto i = temp.begin(); i != temp.end(); i++)
        {
            res += (*i) * (*i);
        }
    
        if (res == 1)
        {
            return true;
        }
        
        n = res;

    }

    return false;

}

Solution14::Solution14(/* args */)
{
}

Solution14::~Solution14()
{
}

/*
    哈希表题4：四数相加2
*/
class Solution15
{
private:
    /* data */
public:
    Solution15(/* args */);
    ~Solution15();

    int fourSumCount(vector<int>& nums1, vector<int>& nums2, vector<int>& nums3, vector<int>& nums4);
    
};

Solution15::Solution15(/* args */)
{
}

Solution15::~Solution15()
{
}

# include<unordered_map>
int Solution15::fourSumCount(vector<int>& nums1, vector<int>& nums2, vector<int>& nums3, vector<int>& nums4){
    int res = 0;

    unordered_map<int, int> m; 
    for (int i = 0; i < nums1.size(); i++)
    {
        for (int j = 0; j < nums2.size(); j++)
        {
            m[nums1[i] + nums2[j]] ++;
        }
        
    }
    
    for (int i = 0; i < nums3.size(); i++)
    {
        for (int j = 0; j < nums4.size(); j++)
        {
            if (m.find(0 - (nums3[i] + nums4[j])) != m.end())  // find这里找取key的值是否存在，若存在获取其key出现的次数
            {
                res += m[0 - (nums3[i] + nums4[j])];
            }
            
        }
        
    }
    
    return res;
}


class Solution16
{
private:
    /* data */
public:
    Solution16(/* args */);
    ~Solution16();

    bool canConstruct(string ransomNote, string magazine);
};

Solution16::Solution16(/* args */)
{
}

Solution16::~Solution16()
{
}

/*
   哈希表题5：赎金信
   给你两个字符串：ransomNote 和 magazine ，判断 ransomNote 能不能由 magazine 里面的字符构成。

    如果可以，返回 true ；否则返回 false 。

    magazine 中的每个字符只能在 ransomNote 中使用一次。
*/
bool Solution16::canConstruct(string ransomNote, string magazine){

    // 记录magazine里每个字符使用情况，若使用则该位置为1，否则该位置为0
    unordered_map<int, int> record;
    int count = 0;
    for (int i = 0; i < ransomNote.length(); i++)
    {
        for (int j = 0; j < magazine.length(); j++)
        {
            if (magazine[j] == ransomNote[i] && record[j] != 1)
            {
                record[j] = 1;
                count ++;
                break;
            }else{
                record[j] = 0;
            }
            
        }
        
    }
    if (count == ransomNote.length())
    {
        return true;
    }
    
    return false;
}

/*
    哈希表题6： 三数之和，   排序+双指针
*/

class Solution17
{
private:
    /* data */
public:
    Solution17(/* args */);
    ~Solution17();

    vector<vector<int>> threeSum(vector<int>& nums);
    vector<vector<int>> threeSum2(vector<int>& nums);
};

Solution17::Solution17(/* args */)
{
}

Solution17::~Solution17()
{
}

/*
    思路一：排序+双指针  思路： 暴力for循环  要用三重for循环  如果使用排序+双指针  则时间复杂度 n2
    时间复杂度分析：
    循环数组  n   第一个元素
    排序时间复杂度 nlogn    
    双指针时间复杂度 n
    所以时间复杂度：nlogn + n * n
    思路二: 哈希表解法   
*/
vector<vector<int>> Solution17::threeSum(vector<int>& nums) {
    vector<vector<int>> res;
    
    if (nums.size() == 3)
    {
        if (nums[0] + nums[1] + nums[2] == 0)
        {   
            vector<int> temp;
            temp.push_back(nums[0]);
            temp.push_back(nums[1]);
            temp.push_back(nums[2]);
            res.push_back(temp);
            return res;
        }else{
            return res;
        }
        
    }
    
    sort(nums.begin(), nums.end());

    // 循环数组
    for (int i = 0; i < nums.size() - 2; i++)
    {

        if (i > 0 && nums[i] == nums[i - 1]){
            continue;
        }

        // 剪枝
        if (nums[i] + nums[i+1] + nums[i+2] > 0){
            break;
        }
        if (nums[i] + nums[nums.size() - 2] + nums[nums.size() - 1] < 0){
            continue;
        }

        int left = i+1;
        int right = nums.size() - 1;

        while (left < right)
        {   

            if (nums[i] + nums[left] + nums[right] == 0){
                vector<int> temp;
                temp.push_back(nums[i]);
                temp.push_back(nums[left]);
                temp.push_back(nums[right]);
                res.push_back(temp);
                
                while (left < right && nums[left] == nums[left+1]){
                    left ++;
                }
                left ++;
                while (left < right && nums[right] == nums[right-1]){
                    right --;
                }
                right --;

            }else if (nums[i] + nums[left] + nums[right] < 0)
            {
                left ++;
            }else{
                right --;
            }

        }
        
    }
    
    return res;
}

// 思路二：哈希表
vector<vector<int>> Solution17::threeSum2(vector<int>& nums) {
    vector<vector<int>> result;
        sort(nums.begin(), nums.end());
        // 找出a + b + c = 0
        // a = nums[i], b = nums[j], c = -(a + b)
        for (int i = 0; i < nums.size(); i++) {
            // 排序之后如果第一个元素已经大于零，那么不可能凑成三元组
            if (nums[i] > 0) {
                break;
            }
            if (i > 0 && nums[i] == nums[i - 1]) { //三元组元素a去重
                continue;
            }
            unordered_set<int> set;
            for (int j = i + 1; j < nums.size(); j++) {
                if (j > i + 2
                        && nums[j] == nums[j-1]
                        && nums[j-1] == nums[j-2]) { // 三元组元素b去重
                    continue;
                }
                int c = 0 - (nums[i] + nums[j]);
                if (set.find(c) != set.end()) {
                    result.push_back({nums[i], nums[j], c});
                    set.erase(c);// 三元组元素c去重
                } else {
                    set.insert(nums[j]);
                }
            }
        }
    return result;
}

/*
    哈希表题7：四数之和
*/
class Solution18
{
private:
    /* data */
public:
    Solution18(/* args */);
    ~Solution18();

    vector<vector<int>> fourSum(vector<int>& nums, int target);

};

Solution18::Solution18(/* args */)
{
}

Solution18::~Solution18()
{
}

// 类比于三数之和: 可以两个for循环遍历数组 + 双指针    n3 时间复杂度 
vector<vector<int>> Solution18::fourSum(vector<int>& nums, int target) {
    vector<vector<int>> res;

    if (nums.size() == 4)
    {
        
       if ((long)(nums[0] + nums[1] + nums[2] + nums[3]) == target)
       {
            vector<int> temp;
            temp.push_back(nums[0]);
            temp.push_back(nums[1]);
            temp.push_back(nums[2]);
            temp.push_back(nums[3]);
            res.push_back(temp);
            return res;
       }else{
            return res;
       }
    }
    sort(nums.begin(), nums.end());
    for (int i = 0; i < nums.size() - 3; i++)
    {   

        // 剪枝
        if ((long)(nums[i] + nums[i+1] + nums[i+2] + nums[i+3]) > target){
            break;
        }
        if ((long)(nums[i] + nums[nums.size() - 3] + nums[nums.size() - 2] + nums[nums.size() - 1]) < target){
            continue;
        }

        if (i > 0 && nums[i] == nums[i-1])
        {
            continue;
        }

        for (int j = i+1; j < nums.size() - 2; j++)
        {
            
            if (j > i + 1 && nums[j] == nums[j-1])
            {
                continue;
            }
            
            int left = j + 1;
            int right = nums.size() - 1;
            
            while (left < right)
            {
                if ((long)(nums[i] + nums[j] + nums[left] + nums[right]) == target)
                {
                    vector <int> temp;
                    temp.push_back(nums[i]);
                    temp.push_back(nums[j]);
                    temp.push_back(nums[left]);
                    temp.push_back(nums[right]);

                    res.push_back(temp);
                    while (left < right && nums[left] == nums[left + 1])
                    {
                       left ++;
                    }
                    
                    while (left < right && nums[right] == nums[right - 1])
                    {
                       right --;
                    }
                    left ++;
                    right --;

                }else if ((long)(nums[i] + nums[j] + nums[left] + nums[right]) <= target)
                {
                    left ++;
                }else{
                    right --;
                }
                
            }
            
        }
        
    }
    
    return res;
}

/*
    字符串题1：反转字符串
*/
class Solution19
{
private:
    /* data */
public:
    Solution19(/* args */);
    ~Solution19();

    void reverseString(vector<char>& s);
};

Solution19::Solution19(/* args */)
{
}

Solution19::~Solution19()
{
}

void Solution19::reverseString(vector<char>& s) {

    int size = s.size();

    // 交换
    for (int i = 0; i < size / 2; i++)
    {
        char temp = s[i];
        s[i] = s[size - i - 1];
        s[size - i - 1] = temp;
    }
    
    for (int i = 0; i < size; i++)
    {
        cout << s[i] << endl;
    }
    
}

/*
    字符串题2：反转字符串2
    给定一个字符串 s 和一个整数 k，从字符串开头算起，每计数至 2k 个字符，就反转这 2k 字符中的前 k 个字符。

    如果剩余字符少于 k 个，则将剩余字符全部反转。
    如果剩余字符小于 2k 但大于或等于 k 个，则反转前 k 个字符，其余字符保持原样。
*/

class Solution20
{
private:
    /* data */
public:
    Solution20(/* args */);
    ~Solution20();

    string reverseStr(string s, int k);

};

Solution20::Solution20(/* args */)
{
}

Solution20::~Solution20()
{
}

string Solution20::reverseStr(string s, int k) {
    
     for (int i = 0; i < s.size(); i += (2 * k)) {
            // 1. 每隔 2k 个字符的前 k 个字符进行反转
            // 2. 剩余字符小于 2k 但大于或等于 k 个，则反转前 k 个字符
            if (i + k <= s.size()) {
                reverse(s.begin() + i, s.begin() + i + k );
            } else {
                // 3. 剩余字符少于 k 个，则将剩余字符全部反转。
                reverse(s.begin() + i, s.end());
            }
        }
        return s;
}

/*
    字符串题3：替换空格
    请实现一个函数，把字符串 s 中的每个空格替换成"%20"。
*/
class Solution21
{
private:
    /* data */
public:
    Solution21(/* args */);
    ~Solution21();

    string replaceSpace(string s);
};

/*
如果想把这道题目做到极致，就不要只用额外的辅助空间了！
首先扩充数组到每个空格替换成"%20"之后的大小。
然后从后向前替换空格，也就是双指针法，过程如下：
i指向新长度的末尾，j指向旧长度的末尾。
其实很多数组填充类的问题，都可以先预先给数组扩容带填充后的大小，然后在从后向前进行操作。
1、不用申请新数组。
2、从后向前填充元素，避免了从前向后填充元素时，每次添加元素都要将添加元素之后的所有元素向后移动的问题。
*/
string Solution21::replaceSpace(string s) {

    int count = 0; // 统计空格的个数
    int sOldSize = s.size();
    for (int i = 0; i < s.size(); i++) {
        if (s[i] == ' ') {
            count++;
        }
    }
    // 扩充字符串s的大小，也就是每个空格替换成"%20"之后的大小
    s.resize(s.size() + count * 2);
    int sNewSize = s.size();
    // 从后向前将空格替换为"%20"
    for (int i = sNewSize - 1, j = sOldSize - 1; j < i; i--, j--) {
        if (s[j] != ' ') {
            s[i] = s[j];
        } else {
            s[i] = '0';
            s[i - 1] = '2';
            s[i - 2] = '%';
            i -= 2;
        }
    }
    return s;
    
}

Solution21::Solution21(/* args */)
{
}

Solution21::~Solution21()
{
}

/*
    字符串题4：反转字符串中单词
    思路：
*/
class Solution22
{
private:
    /* data */
public:
    Solution22(/* args */);
    ~Solution22();

    string reverseWords(string s);
};

string Solution22::reverseWords(string s) {
    // 反转整个字符串
        reverse(s.begin(), s.end());

        int n = s.size();
        int idx = 0;
        for (int start = 0; start < n; ++start) {
            if (s[start] != ' ') {
                // 填一个空白字符然后将idx移动到下一个单词的开头位置
                if (idx != 0) s[idx++] = ' ';

                // 循环遍历至单词的末尾
                int end = start;
                while (end < n && s[end] != ' ') s[idx++] = s[end++];

                // 反转整个单词
                reverse(s.begin() + idx - (end - start), s.begin() + idx);

                // 更新start，去找下一个单词
                start = end;
            }
        }
        s.erase(s.begin() + idx, s.end());
        return s;
}

Solution22::Solution22(/* args */)
{
}

Solution22::~Solution22()
{
}

// 字符串题5：左旋转字符串
class Solution23
{
private:
    /* data */
public:
    Solution23(/* args */);
    ~Solution23();

    string reverseLeftWords(string s, int n);
};


/*
    reverse(s.begin(), s.begin() + n);
    reverse(s.begin() + n, s.end());
    reverse(s.begin(), s.end());
*/
string Solution23::reverseLeftWords(string s, int n) {
    string res = "";
    string temp = "";

    if (n > s.size())
    {
        return s;
    }
    
    int sizeofS = s.size();
    for (int i = 0; i < sizeofS; i++)
    {
        if (i == n)
        {   
            res += s;
            res += temp;
            return res;
        }else{
            temp += s[0];
            s.erase(s.begin());
        }
        
    }
    
    return res;
}

Solution23::Solution23(/* args */)
{
}

Solution23::~Solution23()
{
}

// 字符串题6：找出字符串中第一个匹配项的下标     KMP 算法
    // 本题是KMP经典题目

// 需要总结算法思路
/*
    KMP算法 解决字符串匹配问题

    部分匹配表： 每一个子串（包括模式串本身）最长相等前后缀长度

*/

class Solution24
{
private:
    /* data */
public:
    Solution24(/* args */);
    ~Solution24();

    int strStr(string haystack, string needle);
};

// KMP 算法对 重要的一步 求next数组，即部分匹配表
void getNext(int* next, string s){

    int j = 0;
    next[0] = 0;
    for(int i = 1; i < s.size(); i++) {
        while (j > 0 && s[i] != s[j]) { // j要保证大于0，因为下面有取j-1作为数组下标的操作
            j = next[j - 1]; // 注意这里，是要找前一位的对应的回退位置了
        }
        if (s[i] == s[j]) {
            j++;
        }
        next[i] = j;
    }
      
};
int Solution24::strStr(string haystack, string needle) {
    if (needle.size() == 0) {
            return 0;
        }
    int next[needle.size()];
    getNext(next, needle);
    int j = 0;
    for (int i = 0; i < haystack.size(); i++) {
        while(j > 0 && haystack[i] != needle[j]) {
            j = next[j - 1];
        }
        if (haystack[i] == needle[j]) {
            j++;
        }
        if (j == needle.size() ) {
            return (i - needle.size() + 1);
        }
    }
    return -1;
}

Solution24::Solution24(/* args */)
{
}

Solution24::~Solution24()
{
}

/*
    字符串题7：重复的子字符串

    思路一：移动循环法
    思路二：KMP算法
*/

class Solution25
{
private:
    /* data */
public:
    Solution25(/* args */);
    ~Solution25();

    bool repeatedSubstringPattern1(string s);
    bool repeatedSubstringPattern2(string s);
};

// 判断大字符串是否可以由其子串构造（重复构成）
bool Solution25::repeatedSubstringPattern1(string s) {
    
    string s2 = s + s;

    s2.erase(s2.begin());
    s2.erase(s2.end() - 1);

    if (s2.find(s) != std::string::npos)  // std::string::npos 它实际上意味着直到字符串的末尾。
    {
        return true;
    }
    
    return false;
}

void getNext2(int * next, string s){

    int j = 0;
    next[0] = j;

    for (int i = 1; i < s.size(); i++)
    {
        while (j > 0 && s[i] != s[j])
        {
            j = next[j - 1];
        }
        if (s[i] == s[j])
        {
            j++;
        }
        next[i] = j;
    }
  
}
bool Solution25::repeatedSubstringPattern2(string s) {
    if (s.size() == 0)
    {
        return false;
    }
    

    int next[s.size()];
    getNext2(next, s);

    if (next[s.size() - 1] != 0 && s.size() % (s.size() - next[s.size() - 1]) == 0)
    {
        return true;
    }
    
    return false;

}

Solution25::Solution25(/* args */)
{
}

Solution25::~Solution25()
{
}


/*
    双指针法题1：移除元素
    通过快慢指针将暴力解法的 n2 时间复杂度降为 n
*/

class Solution26
{
private:
    /* data */
public:
    Solution26(/* args */);
    ~Solution26();

    int removeElement(vector<int>& nums, int val);
};
int Solution26::removeElement(vector<int>& nums, int val) {

    int slow = 0;
    for (int fast = 0; fast < nums.size(); fast++)
    {
        if (nums[fast] == val)
        {
            nums[slow++] = nums[fast];   // 这里其实nums数组里大小没有改变，只是将数组前面的元素变成了新的元素
        }
        
    }
    
    return slow;

}

Solution26::Solution26(/* args */)
{
}

Solution26::~Solution26()
{
}

/*
    双指针法题2：反转字符串，该题已在字符串专题中解决 
    通过快慢指针解决时间复杂度为 n2 的问题 将时间复杂度降为 n
    解决思路是通过前后指针指向数组首尾元素         终点是 size() / 2       所以双指针分为快慢指针和首尾指针  此题为首尾指针，上题为快慢指针

    主要是交换首尾指针的值
*/

/*
    双指针法题3：替换空格
    思路：一个指针指向新数组，一个指针指向旧数组     简称：新旧指针
    步骤：1、先循环遍历获取空格个数
         2、按照空格个数，扩容新数组大小
         3、利用双指针产生新数组
*/

class Solution27
{
private:
    /* data */
public:
    Solution27(/* args */);
    ~Solution27();

    string replaceSpace(string s);
};

string Solution27::replaceSpace(string s) {

    int count = 0;
    int sOldSize = s.size();
    for (int i = 0; i < s.size(); i++)
    {
        if (s[i] == ' ')
        {
            count ++;
        }
        
    }
    
    s.resize(s.size() + count * 2);
    int sNewSize = s.size();
    // 从后往前   因为扩容原因
    for (int i = sNewSize - 1, j = sOldSize - 1; j < i; i --, j--)   // j < i   最终 i=j=0  跳出循环
    {
        if (s[j] != ' ')
        {
            s[i] = s[j];
        }else{
            s[i] = '0';
            s[i - 1] = '2';
            s[i - 2] = '%';
            i -= 2;

        }        
        
    }
    return s;
    // return s.replace(" ","%20");
}

Solution27::Solution27(/* args */)
{
}

Solution27::~Solution27()
{
}

/*
    双指针法题4：翻转字符串里的单词
    本题未解决
*/
class Solution28
{
private:
    /* data */
public:
    Solution28(/* args */);
    ~Solution28();


};

Solution28::Solution28(/* args */)
{
}

Solution28::~Solution28()
{
}


/*
    双指针法题5：反转链表    cur  和 pre 指针     前后指针的用法
    在链表题中已解决
*/

/*
    双指针法题6：删除链表的第N个节点    快慢指针的用法
    在链表题中已解决
*/

/*
    双指针法题7：链表相交      
    在链表题中已解决
*/

/*
    双指针法题8：环形链表2     快慢指针的用法
    在链表题中已解决
*/


/*
    双指针法题9：三数之和     双指针法  和   哈希表法    排序 + 剪枝  减少时间复杂度
    在链表题中已解决
*/

/*
    双指针法题10：四数之和     双指针法  和  哈希表法
    在链表题中已解决
*/

/*
    栈与队列题1：用栈实现队列   
    已用 python 实现

*/
class Solution29
{
private:
    
public:
    Solution29(/* args */);
    ~Solution29();

    void push(int x);
    int pop();
    int peek();
    bool empty();
};

void Solution29::push(int x){

}
int Solution29::pop(){

    return 0;
}
int Solution29::peek(){

    return 0;
}
bool Solution29::empty(){
    return 0;
}

Solution29::Solution29(/* args */)
{
}

Solution29::~Solution29()
{
}


/*
    栈与队列题2：队列模拟栈    思路：采用双队列模拟栈
*/
#include <queue>
class Solution30
{
private:
    queue<int> qMain;
    queue<int> qAssist;
public:
    Solution30(/* args */);
    ~Solution30();

    void push(int x);
    
    int pop();
    
    int top();
    
    bool empty();
};

void Solution30::push(int x) {
    qMain.push(x);
}

int Solution30::pop() {
    int size = qMain.size();

    int count = 0;   // 这里拿到了size  可以在while里使用 size --  去掉count 减少代码量  while（size -- ）
    while (count != size - 1)
    {
        qAssist.push(qMain.front());  // 这里需要拿到头部  再pop  因为pop 不反悔pop掉的元素
        qMain.pop();
        count ++;
    }

    int res = qMain.front();
    qMain.pop();

    while (qAssist.size() != 0)
    {
        qMain.push(qAssist.front());
        qAssist.pop();
    }
    
    return res;
    
}

int Solution30::top() {
    return qMain.back();
}

bool Solution30::empty() {
    return qMain.empty();
}

Solution30::Solution30(/* args */)
{   
}

Solution30::~Solution30()
{
}

/*
    栈与队列题3：有效的括号    括号不匹配分三种情况： 左括号多余、左右括号不匹配、右括号多余
    只要处理完这三种情况，则可以判定。
    巧妙在于，栈顶元素刚好是最里左括号需要的右括号
*/
#include<stack>
class Solution31
{
private:
    /* data */
public:
    Solution31(/* args */);
    ~Solution31();

    bool isValid(string s);
};

bool Solution31::isValid(string s) {
    stack<char> stack;

    for (int i = 0; i < s.size(); i++)
    {
        if (s[i] == '(')
        {
            stack.push(')');
        }else if (s[i] == '[')
        {
            stack.push(']');
        }else if (s[i] == '{')
        {
            stack.push('}');
        }else if (stack.empty() || stack.top() != s[i])   // 第三中情况 !stack.empty()      第二种情况 stack.top() != s[i]
        { 
            return false;
        }else{
            stack.pop();
        }
        
    }
    // 第一种情况
    return stack.empty();
}
Solution31::Solution31(/* args */)
{
}

Solution31::~Solution31()
{
}

/*
    栈与队列题4：
    题目描述：给出由小写字母组成的字符串 S，重复项删除操作会选择两个相邻且相同的字母，并删除它们。
            在 S 上反复执行重复项删除操作，直到无法继续删除。
            在完成所有重复项删除操作后返回最终的字符串。答案保证唯一。
*/
class Solution32
{
private:
    /* data */
public:
    Solution32(/* args */);
    ~Solution32();

    string removeDuplicates(string s);
};

/*
    思路： 依次入栈，将即将入栈的元素和栈顶元素比较，如果元素相等，则出栈，如不相等则入栈
*/
string Solution32::removeDuplicates(string s) {

    stack<char> res;

    for (int i = 0; i < s.size(); i++)
    {
        if (!res.empty() && res.top() == s[i])
        {
            res.pop();
        }else{
            res.push(s[i]);
        }
        
    }
    string result = "";
    result.resize(res.size());
    while (!res.empty())
    {
        result += res.top();
        res.pop();
    }
    reverse(result.begin(), result.end());
    return result;

}
Solution32::Solution32(/* args */)
{
}

Solution32::~Solution32()
{
}

/*
    栈与队列题5：逆波兰表达式求值
*/
class Solution33
{
private:
    /* data */
public:
    Solution33(/* args */);
    ~Solution33();

    int evalRPN(vector<string>& tokens);
};
/*
    思路：可以使用两个栈，一个存放数字栈，一个存放运算符栈
    输入：tokens = ["2","1","+","3","*"]
    输出：9
    解释：该算式转化为常见的中缀算术表达式为：((2 + 1) * 3) = 9


    // 逆波兰表达式 (也即后缀表达式) 不用考虑优先级问题

    去掉括号后表达式无歧义，上式即便写成 1 2 + 3 4 + * 也可以依据次序计算出正确结果。

    适合用栈操作运算：遇到数字则入栈；遇到运算符则取出栈顶两个数字进行计算，并将结果压入栈中
*/
int Solution33::evalRPN(vector<string>& tokens) {
    stack<int> numStack;
    // stack<int> signStack;

    for (int i = 0; i < tokens.size(); i++)
    {
        
        if (tokens[i] == "+")
        {
            if (numStack.size() >= 2)
            {
                int b = numStack.top();
                numStack.pop();
                int a = numStack.top();
                numStack.pop();
                int c = a + b;
                numStack.push(c);
            }
            
        }else if (tokens[i] == "-")
        {
            int b = numStack.top();
            numStack.pop();
            int a = numStack.top();
            numStack.pop();
            int c = a - b;
            numStack.push(c);
        }else if (tokens[i] == "*")
        {
            int b = numStack.top();
            numStack.pop();
            int a = numStack.top();
            numStack.pop();
            int c = a * b;
            numStack.push(c);
        }else if (tokens[i] == "/")
        {
            int b = numStack.top();
            numStack.pop();
            int a = numStack.top();
            numStack.pop();
            int c = a / b;
            numStack.push(c);
        }else{
            numStack.push(atoi(tokens[i].c_str()));    // int a = atoi(s.c_str());  将string转换成int
        } 
        
    }
    
    return numStack.top();
}

Solution33::Solution33(/* args */)
{
}

Solution33::~Solution33()
{
}

/*
    栈与队列题6：滑动窗口最大值（困难）
    输入：nums = [1,3,-1,-3,5,3,6,7], k = 3
    输出：[3,3,5,5,6,7]
*/
class Solution34
{
private:
    /* data */
public:
    Solution34(/* args */);
    ~Solution34();

    vector<int> maxSlidingWindow(vector<int>& nums, int k);
};

// 需要实现一个单调栈  具体是单调递减栈  使用deque实现

class MyQueue
{
private:
    /* data */
public:
    deque<int> queue;

    MyQueue(/* args */);
    ~MyQueue();


    void pop(int value);

    void push(int value);

    int front(); // 拿到最大值，出口元素即最大值
};

void MyQueue::pop(int value){

    if (!queue.empty() && value == queue.front())
    {
        queue.pop_front();
    }     

}

void MyQueue::push(int value){

    // 保证单调性
    while (!queue.empty() && value > queue.back())
    {
        queue.pop_back();
    }
    
    queue.push_back(value);

}

int MyQueue::front(){

    return queue.front();

}

MyQueue::MyQueue(/* args */)
{
}

MyQueue::~MyQueue()
{
}


vector<int> Solution34::maxSlidingWindow(vector<int>& nums, int k) {
    vector<int> res;

    MyQueue mq;
    for (int i = 0; i < k; i++)
    {
        mq.push(nums[i]);
    }
    
    res.push_back(mq.front());
    for (int i = k; i < nums.size(); i++)
    {
        mq.pop(nums[i - k]);
        mq.push(nums[i]);
        res.push_back(mq.front());
    }
    
    return res;
}

Solution34::Solution34(/* args */)
{
}

Solution34::~Solution34()
{
}

/*
    栈与队列题7：前 K 个高频元素
    给你一个整数数组 nums 和一个整数 k ，请你返回其中出现频率前 k 高的元素。你可以按 任意顺序 返回答案。

    思路一：优先级队列
    思路二: python字典
*/

class Solution35
{
private:
    /* data */
public:
    Solution35(/* args */);
    ~Solution35();

    vector<int> topKFrequent(vector<int>& nums, int k);
};

vector<int> Solution35::topKFrequent(vector<int>& nums, int k) {
    vector<int> ret;
    unordered_map<int, int> mp;   // unordered_map 底层又哈希表实现  无序  
    priority_queue<pair<int, int>> pq; // 优先队列   如果元素为 pair  则按照 first 排序， 默认为大顶堆，所以first取反  top 元素最小
    for (auto i : nums) mp[i]++;  // 字典获取元素及频次
    for (auto p : mp) {
        pq.push(pair<int, int>(-p.second, p.first));  // 优先队列在push时自动按照first排序
        if (pq.size() > k) pq.pop();  // 不用将全部元素放入，减少时间消耗
    }
    while (k--) {
        ret.push_back(pq.top().second);  // 放入结果集
        pq.pop();
    }
    return ret;

}

Solution35::Solution35(/* args */)
{
}

Solution35::~Solution35()
{
}

/*
    二叉树题1：前序遍历
*/

struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
    TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
};

class Solution36
{
private:
    /* data */
public:
    Solution36(/* args */);
    ~Solution36();

    vector<int> preorderTraversal(TreeNode* root);
};
/*
    两种遍历方法：递归法和迭代法（非递归法）
*/
void preOrder(TreeNode* root, vector<int>& v){
    if (root == NULL)
    {
        return;
    }
    
    v.push_back(root->val);
    preOrder(root->left, v);
    preOrder(root->right, v);


}
vector<int> Solution36::preorderTraversal(TreeNode* root) {
    
    // 先使用递归实现
    vector<int> res;
    
    preOrder(root, res);

    return res;
} 

Solution36::Solution36(/* args */)
{
    
}

Solution36::~Solution36()
{
}

/*
    二叉树题2：中序遍历
*/
class Solution37
{
private:
    /* data */
public:
    Solution37(/* args */);
    ~Solution37();

    vector<int> midorderTraversal(TreeNode* root);
};

void midOrder(TreeNode* root, vector<int>& v){
    if (root == NULL)
    {
        return;
    }
    
    midOrder(root->left, v);
    v.push_back(root->val);
    midOrder(root->right, v);


}
vector<int> Solution37::midorderTraversal(TreeNode* root) {
    
    // 先使用递归实现
    vector<int> res;
    
    midOrder(root, res);

    return res;
} 

Solution37::Solution37(/* args */)
{
}

Solution37::~Solution37()
{
}

/*
    二叉树题3：后序遍历
*/
class Solution38
{
private:
    /* data */
public:
    Solution38(/* args */);
    ~Solution38();
    vector<int> postorderTraversal(TreeNode* root);
};


void postOrder(TreeNode* root, vector<int>& v){
    if (root == NULL)
    {
        return;
    }
    
    postOrder(root->left, v);
    postOrder(root->right, v);
    v.push_back(root->val);


}
vector<int> Solution38::postorderTraversal(TreeNode* root) {
    
    // 先使用递归实现
    vector<int> res;
    
    postOrder(root, res);

    return res;
} 

Solution38::Solution38(/* args */)
{
}

Solution38::~Solution38()
{
}

/*
    二叉树题4：  迭代遍历（非递归遍历二叉树） 以及迭代法的统一写法    未实现
*/

/*
    二叉树题5：二叉树的层序遍历   广度优先思想
*/

class Solution39
{
private:
    /* data */
public:
    Solution39(/* args */);
    ~Solution39();

    vector<vector<int>> levelOrder(TreeNode* root);
};

vector<vector<int>> Solution39::levelOrder(TreeNode* root) {

    vector<vector<int>> res;
    if (root == nullptr) return res;
    
    // 使用队列实现
    queue<TreeNode*> q;
    q.push(root);

    while (!q.empty())
    {
        
        int size = q.size();
        vector<int> temp;
        for (int i = 0; i < size; i++)
        {   
            TreeNode* node = q.front();
            temp.push_back(node->val);
            q.pop();
            if (root->left) q.push(root->left); 
            if (root->right) q.push(root->right); 
        }
        res.push_back(temp);
    }
    
    return res;
}

Solution39::Solution39(/* args */)
{
}

Solution39::~Solution39()
{
}

/*
    二叉树题5：翻转二叉树
*/

class Solution40
{
private:
    /* data */
public:
    Solution40(/* args */);
    ~Solution40();

    TreeNode* invertTree(TreeNode* root);
};

TreeNode* Solution40::invertTree(TreeNode* root) {
    if (root == nullptr) return root;
    stack<TreeNode*> s;
    s.push(root);
    while (!s.empty())
    {
        TreeNode* temp = s.top();
        s.pop();
        swap(temp->left, temp->right);
        if (root->right) s.push(root->right);
        if (root->left) s.push(root->left);
    }
    return root;
    
}

Solution40::Solution40(/* args */)
{
}

Solution40::~Solution40()
{
}
/*
    二叉树题6: 二叉树的最大深度
*/

class Solution41
{
private:
    /* data */
public:
    Solution41(/* args */);
    ~Solution41();

    int maxDepth(TreeNode* root);
};

Solution41::Solution41(/* args */)
{
}

Solution41::~Solution41()
{
}
// 思路一，二叉树的最大深度可以使用层序遍历去实现，记录层数个数就行
// 思路二，使用递归实现
/*
    int getdepth(treenode* node) {
        if (node == NULL) return 0;
        int leftdepth = getdepth(node->left);       // 左
        int rightdepth = getdepth(node->right);     // 右
        int depth = 1 + max(leftdepth, rightdepth); // 中
        return depth;
    }
    int maxdepth(treenode* root) {
        return getdepth(root);
    }
*/
int Solution41::maxDepth(TreeNode* root) {

    if (root == NULL) return 0;
    
    queue<TreeNode*> q;
    q.push(root);
    int depth = 0;   // int 需要初始化为 0   如果不初使化int变量,将得到一个随机值。
    while (!q.empty())
    {
        int size = q.size();

        for (int i = 0; i < size; i++)
        {
            TreeNode* node = q.front();
            q.pop();
            if (node->left) q.push(node->left); 
            if (node->right) q.push(node->right); 
        }
         
        depth ++;

    }
     
    return depth;
}

/*
    二叉树题7：二叉树的最小深度
*/

class Solution42
{
private:
    /* data */
public:
    Solution42(/* args */);
    ~Solution42();

    int minDepth(TreeNode* root);
};
// 思路一：
// 思路二：参照求二叉树的最大深度，可以使用递归法求最小深度, 但要注意还是有很大区别的
int getDepth(TreeNode* node){
    int leftDepth = getDepth(node->left);           // 左
    int rightDepth = getDepth(node->right);         // 右
    // 当一个左子树为空，右不为空，这时并不是最低点
    if (node->left == NULL && node->right != NULL) { 
        return 1 + rightDepth;
    }   
    // 当一个右子树为空，左不为空，这时并不是最低点
    if (node->left != NULL && node->right == NULL) { 
        return 1 + leftDepth;
    }
    int result = 1 + min(leftDepth, rightDepth);
    return result;

}

int Solution42::minDepth(TreeNode* root) {

    return getDepth(root);
}

Solution42::Solution42(/* args */)
{
}

Solution42::~Solution42()
{
}

/*
    二叉树题8：完全二叉树的节点个数
*/

class Solution43
{
private:
    /* data */
public:
    Solution43(/* args */);
    ~Solution43();

    int countNodes(TreeNode* root);
};

// 思路 借助层序遍历的思想实现
int Solution43::countNodes(TreeNode* root) {

    if (root == NULL)
    {
        return 0;
    }
    
    int count = 0;

    queue<TreeNode*> q;
    q.push(root);

    while (!q.empty())
    {
        int size = q.size();

        for (int i = 0; i < size; i++)
        {
            TreeNode* node = q.front();

            q.pop();

            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);

            count ++;    
        }
   
    }
    
    return count;
}

Solution43::Solution43(/* args */)
{
}

Solution43::~Solution43()
{
}

/*
    二叉树题9：平衡二叉树      定义：一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过 1 。

    求二叉树的深度需要从上至下，所以可以用前序遍历
    求二叉树的高度需要从下至上，所以可以用后续遍历

    前序遍历求深度（递归）   最大深度（高度） 也可以用层序遍历（非递归）    最大高度和最大深度一样，但是平衡二叉树要求每个节点高度满足条件，就不同于求深度问题
    int result;
    void getDepth(TreeNode* node, int depth) {
        result = depth > result ? depth : result; // 中
        if (node->left == NULL && node->right == NULL) return ;
        if (node->left) { // 左
            getDepth(node->left, depth + 1);
        }
        if (node->right) { // 右
            getDepth(node->right, depth + 1);
        }
        return ;
    }
    int maxDepth(TreeNode* root) {
        result = 0;
        if (root == 0) return result;
        getDepth(root, 1);
        return result;
    }

*/
class Solution44
{
private:
    /* data */
public:
    Solution44(/* args */);
    ~Solution44();

    bool isBalanced(TreeNode* root);
};
// 1、递归后续遍历求高度（左右中）   2、迭代法     未实现

int getHight(TreeNode* root){
    if (root == NULL) return 0;

    int leftHight = getHight(root->left);
    if (leftHight == -1) return -1;
    int rightHight = getHight(root->right);
    if (rightHight == -1) return -1;
    
    return abs(leftHight - rightHight) > 1? -1: 1+max(leftHight, rightHight);

}

bool Solution44::isBalanced(TreeNode* root) {
    return getHight(root) == -1? false : true;
}

Solution44::Solution44(/* args */)
{
}

Solution44::~Solution44()
{
}

/*
    二叉树题10：二叉树的所有路径

    给你一个二叉树的根节点 root ，按 任意顺序 ，返回所有从根节点到叶子节点的路径。
*/
class Solution45
{
private:
    /* data */
public:
    Solution45(/* args */);
    ~Solution45();

    vector<string> binaryTreePaths(TreeNode* root);
};

// 思路：从上往下 前序遍历  递归实现
void getPath(TreeNode* root, vector<string> &res, vector<int> &temp){
    temp.push_back(root->val);
    if (root->left == NULL && root->right == NULL){
        string sPath = "";
        for(int i = 0; i < temp.size() - 1; i ++){
            sPath += std::to_string(temp[i]);
            sPath += "->";
        };
        sPath += to_string(temp[temp.size() - 1]); // 记录最后一个节点（叶子节点）
        res.push_back(sPath);
        return;
    } 

    if (root->left) {
        getPath(root->left, res, temp);
        temp.pop_back();  // 回溯
    }
    if (root->right){
        getPath(root->right, res, temp);  
        temp.pop_back();  // 回溯
    } 
}

vector<string> Solution45::binaryTreePaths(TreeNode* root) {
    vector<string> res;
    vector<int> temp;

    getPath(root, res, temp);

    return res;
}

Solution45::Solution45(/* args */)
{
}

Solution45::~Solution45()
{
}
/*
    二叉树题11：左叶子之和
    给定二叉树的根节点，返回所有左叶子之和
*/

class Solution46
{
private:
    /* data */
public:
    Solution46(/* args */);
    ~Solution46();

    int sumOfLeftLeaves(TreeNode* root);
};

int Solution46::sumOfLeftLeaves(TreeNode* root) {

    if (root == NULL) return 0;
    if (root->left == NULL && root->right== NULL) return 0;

    int leftValue = sumOfLeftLeaves(root->left);    // 左

    if (root->left && !root->left->left && !root->left->right) { // 左子树就是一个左叶子的情况
        leftValue = root->left->val;
    }
    int rightValue = sumOfLeftLeaves(root->right);  // 右

    int sum = leftValue + rightValue;               // 中
    return sum;
}

Solution46::Solution46(/* args */)
{
}

Solution46::~Solution46()
{
}

/*
    二叉树题12：找树左下角的值

    给定一个二叉树的 根节点 root，请找出该二叉树的 最底层 最左边 节点的值。

    假设二叉树中至少有一个节点。
*/

class Solution47
{
private:
    
public:
    Solution47(/* args */);
    ~Solution47();
    int maxDepth = INT_MIN;
    int result = 0;
    int findBottomLeftValue(TreeNode* root);
    void getLeftValue(TreeNode* root, int deepth);
};

Solution47::Solution47(/* args */)
{
}

Solution47::~Solution47()
{
}

// 递归实现   思路：先找到最大深度（即最底层)  然后回去左子节点的值

/*
    递归三部曲
    1、确定参数和返回值
    2、终止条件
    3、确定单层递归（注意，如果有回溯，应该先递归在回溯，写在一起）

*/
// 1、确定参数和返回值
void Solution47::getLeftValue(TreeNode* root, int deepth){

    // 2、终止条件
    if (root->left == NULL && root->right == NULL) {   // 目的是找到最底层（即叶子节点）
        if (deepth > maxDepth) {  // 不断更新值，当然最后会找到深度最深的叶子节点，并且拿到节点值       因为在同一级不会进入这个 if 判断
            maxDepth = deepth;  // 这里因为递归的时候是 先左后右   所以当拿到左子节点的时候就返回了
            result = root->val;
        }
        return;
    }
    
    // 3、单层递归条件
    if (root->left)
    {
        deepth ++;
        getLeftValue(root->left, deepth);
        deepth --;
    }
    
    if (root->right)
    {
        deepth ++;
        getLeftValue(root->right, deepth);
        deepth --;
    }
    
}
int Solution47::findBottomLeftValue(TreeNode* root) {

    getLeftValue(root, 0);
    return 0;
}


/*
    二叉树题13：路径总和     这道题和求所有路径题一个思路
*/

class Solution48
{
public:
    Solution48(/* args */);
    ~Solution48();

    bool hasPathSum(TreeNode* root, int targetSum);
};

void getPath(TreeNode* root, vector<int> &res, vector<int> &temp){
        temp.push_back(root->val);
        if (root->left == NULL && root->right == NULL){
            int sPath = 0;
            for(int i = 0; i < temp.size(); i ++){
                sPath += temp[i];
            };
            res.push_back(sPath);
            return;
        } 

        if (root->left) {
            getPath(root->left, res, temp);
            temp.pop_back();
        }
        if (root->right){
            getPath(root->right, res, temp);  
            temp.pop_back();
        } 
    }


bool Solution48::hasPathSum(TreeNode* root, int targetSum) {
    if(root == NULL) return false;

    vector<int> res;
    vector<int> temp;
    getPath(root, res, temp);

    bool res2 = false;

    for(int i = 0; i < res.size(); i++){

        if(res[i] == targetSum){
            res2 = true;
        }
    }

    return res2;
}

Solution48::Solution48(/* args */)
{
}

Solution48::~Solution48()
{
}

/*
    二叉树题14：路径总和2

    给你二叉树的根节点 root 和一个整数目标和 targetSum ，找出所有 从根节点到叶子节点 路径总和等于给定目标和的路径。
    叶子节点 是指没有子节点的节点。


    找出所有满足目标值的路径    这道题的思路和上一道一样

*/

class Solution49
{
private:
    /* data */
public:
    Solution49(/* args */);
    ~Solution49();

    vector<vector<int>> pathSum(TreeNode* root, int targetSum);
};

void getPathTarget(TreeNode* root, vector<vector<int>> &res, vector<int> &temp, int targetSum){

    temp.push_back(root->val);

    if (root->left == NULL && root->right == NULL)
    {
        int sum = 0;
        for (int i = 0; i < temp.size(); i++)
        {
            sum += temp[i];
        }

        if (sum == targetSum)
        {
            res.push_back(temp);
        }
        
    }
    
    if (root->left)
    {
        getPathTarget(root->left, res, temp, targetSum);
        temp.pop_back();
    }
    
    if (root->right)
    {
        getPathTarget(root->right, res, temp, targetSum);
        temp.pop_back();
    }

}

vector<vector<int>> Solution49::pathSum(TreeNode* root, int targetSum) {

    vector<vector<int>> res;
    if(root == NULL) return res;
    vector<int> temp;
    getPathTarget(root, res, temp, targetSum);
    return res;
    
}

Solution49::Solution49(/* args */)
{
}

Solution49::~Solution49()
{
}

/*
    二叉树题15：从中序与后序遍历序列构造二叉树
*/


class Solution50
{
private:
    /* data */
public:
    Solution50(/* args */);
    ~Solution50();

    TreeNode* buildTree(vector<int>& inorder, vector<int>& postorder);
};
/*
    中序后序遍历二叉树：
    思路：
    1、当根节点为空（无节点），则返回null
    2、当只有一个节点，则返回节点
    3、根据后序数组，获取父节点
    4、根据父节点切割中序数组
    5、根据中序数组前后长度切割后序数组
    6、递归处理切割后的前后区间
*/
TreeNode* Solution50::buildTree(vector<int>& inorder, vector<int>& postorder) {

   
    if (postorder.size() == 0)
    {
        return NULL;
    }
   
    // 后序遍历数组最后一个元素，就是当前的中间节点
    int rootValue = postorder[postorder.size() - 1];
    TreeNode* root = new TreeNode(rootValue);

    // 叶子节点
    if (postorder.size() == 1) return root;

    // 使用左闭右开
    int index = 0;
    for (index = 0; index < inorder.size(); index++)
    {
        if (inorder[index] == rootValue)
        {
            break;
        }
        
    }
    
    vector<int> leftInorder(inorder.begin(), inorder.begin() + index); // 拷贝构造
    vector<int> rightInorder(inorder.begin() + index + 1, inorder.end()); // 拷贝构造

    postorder.resize(postorder.size() - 1);

    vector<int> leftPostorder(postorder.begin(), inorder.begin() + leftInorder.size()); // 拷贝构造
    vector<int> rightPostorder(postorder.begin() + leftInorder.size(), postorder.end()); // 拷贝构造

    // 处理前区间
    root->left = buildTree(leftInorder, leftPostorder);
    // 处理后区间
    root->right = buildTree(rightInorder, rightPostorder);

    return root;
}

Solution50::Solution50(/* args */)
{
}

Solution50::~Solution50()
{
}

/*
    二叉树题16：从中序与前序遍历序列构造二叉树     注意：前序和后序不能唯一确定一棵二叉树
*/

class Solution51
{
private:
    /* data */
public:
    Solution51(/* args */);
    ~Solution51();

    TreeNode* buildTree(vector<int>& preorder, vector<int>& inorder);
};
// 这道题思想和中序后序遍历一样，不再是按后序切割，而是按前序切割
TreeNode* traval(vector<int>& preorder, vector<int>& inorder) {
    if (preorder.size() == 0)
    {
        return NULL;
    }
    
    int val = preorder[0];
    TreeNode* root = new TreeNode(val);
    
    if (preorder.size() == 1)
    {
        return root;
    }
    

    // 切割
    int index = 0;
    for (index = 0; index < inorder.size(); index++)
    {
        if (inorder[index] == val)
        {
            break;
        }
        
    }
    
    vector<int> leftInorder(inorder.begin(), inorder.begin() + index);
    vector<int> rightInorder(inorder.begin() + index + 1, inorder.end());

    preorder.erase(preorder.begin());  // 这里需要将第一个元素去掉

    vector<int> leftPreorder(preorder.begin(), preorder.begin() + leftInorder.size());
    vector<int> rightPreorder(preorder.begin() + leftInorder.size(), preorder.end());


    root->left = traval(leftPreorder, leftInorder);
    root->right = traval(rightPreorder, rightInorder);

    return root;
}

TreeNode* Solution51::buildTree(vector<int>& preorder, vector<int>& inorder) {

    if (preorder.size() == 0 || inorder.size() == 0)
    {
        return NULL;
    }
    

    return traval(preorder, inorder);
}

Solution51::Solution51(/* args */)
{
}

Solution51::~Solution51()
{
}

/*
    二叉树题17：最大二叉树

    给定一个不重复的整数数组 nums 。 最大二叉树 可以用下面的算法从 nums 递归地构建:

    创建一个根节点，其值为 nums 中的最大值。
    递归地在最大值 左边 的 子数组前缀上 构建左子树。
    递归地在最大值 右边 的 子数组后缀上 构建右子树。
    返回 nums 构建的 最大二叉树 。

*/

class Solution52
{
private:
    
public:
    Solution52(/* args */);
    ~Solution52();

    TreeNode* constructMaximumBinaryTree(vector<int>& nums);
};

// 递归构建最大二叉树
    int findMax(vector<int> vec) {
    int max = -999;
    for (auto v : vec) {
        if (max < v) max = v;
    }
    return max;
}

// 递归构建最大二叉树
TreeNode* travalBuildTree(vector<int> &nums){
    
    if (nums.size() == 0)
    {
        return NULL;
    }

    int maxValue = findMax(nums);
    TreeNode* root = new TreeNode(maxValue);
    
    if (nums.size() == 1)
    {
        return root;
    }
    

    int index = 0;
    for ( index = 0; index < nums.size(); index++)
    {
        if (nums[index] == maxValue)
        {
            break;
        }
        
    }
    
    vector<int> leftNums(nums.begin(), nums.begin() + index);
    vector<int> rightNums(nums.begin() + index + 1, nums.end());

    root->left = travalBuildTree(leftNums);
    root->right = travalBuildTree(rightNums);


    return root;

}

TreeNode* Solution52::constructMaximumBinaryTree(vector<int>& nums) {

    if (nums.size() == 0)
    {
        return NULL;
    }
    
    return travalBuildTree(nums);

}

Solution52::Solution52(/* args */)
{
    
}

Solution52::~Solution52()
{
}

/*
    二叉树题18：合并二叉树

    思路：
    可以先前（中或后）序遍历第一棵二叉树，从根节点开始，判断该节点是否有左右孩子，都有则相加合并，没有则将有的加上去
*/
class Solution53
{
private:
    
public:
    Solution53(/* args */);
    ~Solution53();
    TreeNode* root1;
    TreeNode* root2;
    TreeNode* mergeTrees(TreeNode* root1, TreeNode* root2);
};

// 选择前序遍历
TreeNode* Solution53::mergeTrees(TreeNode* root1, TreeNode* root2) {
    if (root1 == NULL) return root2;
    if (root2 == NULL) return root1;
    
    root1->val += root2->val;

    root1->left = mergeTrees(root1->left, root2->left);
    root1->right = mergeTrees(root1->right, root2->right);
    
    return root1;
}

Solution53::Solution53(/* args */)
{
    root1 = new TreeNode(1);
    root1->left = new TreeNode(3);
    root1->right = new TreeNode(2);
    root1->left->left = new TreeNode(5);

    root2 = new TreeNode(2);
    root2->left = new TreeNode(1);
    root2->right = new TreeNode(3);
    root2->left->right = new TreeNode(4);
    root2->right->right = new TreeNode(7);
}

Solution53::~Solution53()
{
}


// 遍历二重vector
template <typename E>
void ShowTowVector(vector<vector<E>> res){
    cout << "[";
    for(auto i : res){
        cout << "[ ";
        for(auto j: i){
            cout << j << " ";
        }
        cout << "],";
    }
    cout << "]" << endl;
    
}

/*
    二叉树题19：二叉树中的搜索

    给定二叉搜索树（BST）的根节点 root 和一个整数值 val。

    你需要在 BST 中找到节点值等于 val 的节点。 返回以该节点为根的子树。 如果节点不存在，则返回 null 。

*/

class Solution54
{
private:
    /* data */
public:
    Solution54(/* args */);
    ~Solution54();

    TreeNode* searchBST(TreeNode* root, int val);
};


// 思路：通过前中后遍历找到等于目标值的节点
TreeNode* Solution54::searchBST(TreeNode* root, int val) {

    if(root == NULL || root->val == val) return root;
    TreeNode* result;
    if(root->val > val) result = searchBST(root->left, val);
    if(root->val < val) result = searchBST(root->right, val);
    return result;

}

Solution54::Solution54(/* args */)
{
}

Solution54::~Solution54()
{
}

/*
    二叉树题20：验证二叉搜索树


    给你一个二叉树的根节点 root ，判断其是否是一个有效的二叉搜索树。

    有效 二叉搜索树定义如下：

    节点的左子树只包含 小于 当前节点的数。
    节点的右子树只包含 大于 当前节点的数。
    所有左子树和右子树自身必须也是二叉搜索树。
 
*/
class Solution55
{
private:
    /* data */
public:
    long long maxVal = LONG_MIN; // 因为后台测试数据中有int最小值
    Solution55(/* args */);
    ~Solution55();

    bool isValidBST(TreeNode* root);
};
/*
    要知道中序遍历下，输出的二叉搜索树节点的数值是有序序列。

    有了这个特性，验证二叉搜索树，就相当于变成了判断一个序列是不是递增的了。
*/


// 思路：1、转换成数组

    // private:
    //     vector<int> vec;
    //     void traversal(TreeNode* root) {
    //         if (root == NULL) return;
    //         traversal(root->left);
    //         vec.push_back(root->val); // 将二叉搜索树转换为有序数组
    //         traversal(root->right);
    //     }
    // public:
    //     bool isValidBST(TreeNode* root) {
    //         vec.clear(); // 不加这句在leetcode上也可以过，但最好加上
    //         traversal(root);
    //         for (int i = 1; i < vec.size(); i++) {
    //             // 注意要小于等于，搜索树里不能有相同元素
    //             if (vec[i] <= vec[i - 1]) return false;
    //         }
    //         return true;
    //     }



//      2、递归实现
bool Solution55::isValidBST(TreeNode* root) {
    
    if (root == NULL)
    {
        return true;
    }
    
    bool left = isValidBST(root->left);

    if ( maxVal < root->val) 
    {
        maxVal = root->val;
    }else{
        return false;
    }
    

    bool right = isValidBST(root->right);

    return left && right;
}

Solution55::Solution55(/* args */)
{
}

Solution55::~Solution55()
{
}

/*
    二叉树题21：二叉搜索树的最小绝对值

*/
class Solution56
{
private:
    
public:
    vector<int> vec;
    Solution56(/* args */);
    ~Solution56();

    int getMinimumDifference(TreeNode* root);
    void traversal(TreeNode* root);
};


void Solution56::traversal(TreeNode* root) {
    if (root == NULL) return;
    traversal(root->left);
    vec.push_back(root->val); // 将二叉搜索树转换为有序数组
    traversal(root->right);
}

int Solution56::getMinimumDifference(TreeNode* root) {

        vec.clear();
        traversal(root);
        if (vec.size() < 2) return 0;
        int result = INT_MAX;
        for (int i = 1; i < vec.size(); i++) { // 统计有序数组的最小差值
            result = min(result, vec[i] - vec[i-1]);
        }
        return result;
}

Solution56::Solution56(/* args */)
{
}

Solution56::~Solution56()
{
}

/*
    二叉树题22：二叉搜索树中的众数
*/

class Solution57
{
private:
    /* data */
public:
    vector<int> vec;
    Solution57(/* args */);
    ~Solution57();

    vector<int> findMode(TreeNode* root);
    void traversal2(TreeNode* root);
};

void Solution57::traversal2(TreeNode* root) {
    if (root == NULL) return;
    traversal2(root->left);
    vec.push_back(root->val); // 将二叉搜索树转换为有序数组
    traversal2(root->right);
}
// 思路：转换成序列，使用undered_map 获取频次  最后获得众数
vector<int> Solution57::findMode(TreeNode* root) {

        vec.clear();
        traversal2(root);
        if (vec.size() < 2) return vec;
        vector<int> res;
        unordered_map<int, int> map;
        int maxCount = 0;
        for (int i = 0; i < vec.size(); i++) { // 统计有序数组的最小差值
            map[vec[i]] ++;
            if (maxCount < map[vec[i]])
            {
                maxCount = map[vec[i]];
            }
            
        }
        for (auto i = map.begin(); i != map.end(); i++)
        {
            if ((*i).second == maxCount)
            {
                res.push_back((*i).first);
            }
            
        }
        
        return res;
}


Solution57::Solution57(/* args */)
{
}

Solution57::~Solution57()
{
}

/*
    二叉树题23：二叉树的最近公共祖先     未解决
*/
class Solution58
{
private:
    /* data */
public:
    Solution58(/* args */);
    ~Solution58();

    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q);
};

TreeNode* Solution58::lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {


    return NULL;   
}

Solution58::Solution58(/* args */)
{
}

Solution58::~Solution58()
{
}

/*
    二叉树题24：二叉搜索树的最近公共祖先    未解决
*/

class Solution59
{
private:
    /* data */
public:
    Solution59(/* args */);
    ~Solution59();

    TreeNode* lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q);
};

TreeNode* Solution59::lowestCommonAncestor(TreeNode* root, TreeNode* p, TreeNode* q) {
    

    return NULL;
}


Solution59::Solution59(/* args */)
{
}

Solution59::~Solution59()
{
}
/*
    二叉树题25：二叉搜索树中的插入操作
*/

class Solution60
{
private:
    /* data */
public:
    Solution60(/* args */);
    ~Solution60();

    TreeNode* insertIntoBST(TreeNode* root, int val);
};

// 思路：可采用递归前序遍历方式，其实对于二叉搜索树，只需要再最底层插入即可，即找到空节点即可
TreeNode* Solution60::insertIntoBST(TreeNode* root, int val) {

    if (root == NULL)
    {   
        TreeNode* node = new TreeNode(val);
        return node;
    }

    if (val < root->val)
    {
        root->left = insertIntoBST(root->left, val);
    }
    
    if (val > root->val)
    {
        root->right = insertIntoBST(root->right, val);
    }
    

    return root;

}

Solution60::Solution60(/* args */)
{
}

Solution60::~Solution60()
{
}

/*
    二叉树题26：删除二叉搜索树中的节点
*/

class Solution61
{
private:
    /* data */
public:
    Solution61(/* args */);
    ~Solution61();

    TreeNode* deleteNode(TreeNode* root, int key);
};

// 思路，就是找到目标值节点后，比较其孩子节点大小，调整关系，再将其删除
TreeNode* Solution61::deleteNode(TreeNode* root, int key) {

    if (root == NULL)
    {
        return root;
    }
    
    if (root->val == key && !root->left && !root->right)
    {
        return NULL;
    }
    
    if (root->val == key && root->left && !root->right)
    {
        return root->left;
    }
    
    if (root->val == key && !root->left && root->right) 
    {
        return root->right;
    }
    
    // 第五种情况：左右孩子节点都不为空，则将删除节点的左子树头结点（左孩子）放到删除节点的右子树的最左面节点的左孩子上，返回删除节点右孩子为新的根节点。
    if (root->val == key && root->left && root->right)
    {
        TreeNode* cur = root->right;
        while (cur->left)
        {
            cur = cur->left;
        }

        cur->left = root->left;
        TreeNode* temp = root;
        root = root->right;
        delete temp;
        return root;
        
    }

    if (root->val > key)
    {
        root->left = deleteNode(root->left, key);
    }
    
    if (root->val < key)
    {
        root->right = deleteNode(root->right, key);
    }
    

    return root;
}

Solution61::Solution61(/* args */)
{
    
}

Solution61::~Solution61()
{
}

/*
    二叉树题27：修剪二叉搜索树                这道题很绕，建议多看看

    给你二叉搜索树的根节点 root ，同时给定最小边界low 和最大边界 high。通过修剪二叉搜索树，
    使得所有节点的值在[low, high]中。修剪树 不应该 改变保留在树中的元素的相对结构 
    (即，如果没有被移除，原有的父代子代关系都应当保留)。
*/
class Solution62
{
private:
    /* data */
public:
    Solution62(/* args */);
    ~Solution62();

    TreeNode* trimBST(TreeNode* root, int low, int high);
};

// 
TreeNode* Solution62::trimBST(TreeNode* root, int low, int high) {
    if (root == nullptr ) return nullptr;
    if (root->val < low) {
        TreeNode* right = trimBST(root->right, low, high); // 寻找符合区间[low, high]的节点
        return right;
    }
    if (root->val > high) {
        TreeNode* left = trimBST(root->left, low, high); // 寻找符合区间[low, high]的节点
        return left;
    }
    root->left = trimBST(root->left, low, high); // root->left接入符合条件的左孩子
    root->right = trimBST(root->right, low, high); // root->right接入符合条件的右孩子
    return root;

}

Solution62::Solution62(/* args */)
{
}

Solution62::~Solution62()
{
}

/*
    二叉树题28：将有序数组转化为二叉搜索树

*/

class Solution63
{
private:
    /* data */
public:
    Solution63(/* args */);
    ~Solution63();

    TreeNode* sortedArrayToBST(vector<int>& nums);
};

// 思路：二叉搜索树的中序遍历就是递增序列， 而此时有序数组的中间元素就是二叉树的根节点，按照此元素进行分割，再递归就能构造完毕
TreeNode* Solution63::sortedArrayToBST(vector<int>& nums) {

    if (nums.size() == 0)
    {
        return NULL;
    }

    TreeNode* root = new TreeNode(nums[nums.size() / 2]);

    if (nums.size() == 1)
    {
        TreeNode* node = new TreeNode(nums[0]);
        return node;
    }
    
    // 分割
    vector<int> leftnums(nums.begin(), nums.begin() + nums.size() / 2);
    vector<int> rightnums(nums.begin() + nums.size() / 2 + 1, nums.end());
    
    root->left = sortedArrayToBST(leftnums);
    root->right = sortedArrayToBST(rightnums);
    
    return root;
}
Solution63::Solution63(/* args */)
{
}

Solution63::~Solution63()
{
}

/*
    二叉树题29：把二叉搜索树转换为累加树                建议多看看

    给出二叉 搜索 树的根节点，该树的节点值各不相同，请你将其转换为累加树（Greater Sum Tree），
    使每个节点 node 的新值等于原树中大于或等于 node.val 的值之和。

*/

class Solution64
{
private:
    /* data */
public:
    Solution64(/* args */);
    ~Solution64();

    TreeNode* convertBST(TreeNode* root);
};

int pre = 0; // 记录前一个节点的数值
void traversal(TreeNode* cur) { // 右中左遍历
    if (cur == NULL) return;
    traversal(cur->right);
    cur->val += pre;
    pre = cur->val;
    traversal(cur->left);
}
// 思路：计算每个节点的右子树之和，作为该节点的新值
TreeNode* Solution64::convertBST(TreeNode* root) {

    pre = 0;
    traversal(root);
    
    return root;
}
Solution64::Solution64(/* args */)
{
}

Solution64::~Solution64()
{
}


/*
    回溯算法题1：组合
*/

class Solution65
{
private:
    /* data */
public:
    Solution65(/* args */);
    ~Solution65();

    vector<vector<int>> combine(int n, int k);
    void backtracking(vector<vector<int>> &res, vector<int> &temp, int k, int n, int index);
};

/*
    给定两个整数 n 和 k，返回范围 [1, n] 中所有可能的 k 个数的组合。
    你可以按 任何顺序 返回答案。
*/

void Solution65::backtracking(vector<vector<int>> &res, vector<int> &temp, int k, int n, int index){
    
    if (temp.size() == k)
    {
        res.push_back(temp);
        return;
    }
    
    for (int i = index; i < n; i++)   // for (int i = startIndex; i <= n - (k - path.size()) + 1; i++) // i为本次搜索的起始位置  “优化剪枝”
    {
        temp.push_back(i);
        backtracking(res, temp, k, n, ++index);
        temp.pop_back();
    }
    
}

vector<vector<int>> Solution65::combine(int n, int k) {
    vector<vector<int>> res;
    vector<int> temp;
    int index = 1;
    backtracking(res, temp, k, n+1, index);

    return res;
}

Solution65::Solution65(/* args */)
{
}

Solution65::~Solution65()
{
}

// int main(){

//     Solution65 s65;

//     int k = 2;

//     int n = 4;

//     auto res = s65.combine(n, k);

//     ShowTowVector(res);

//     return 0;
// }

/*
    回溯算法题2：组合总和3

    找出所有相加之和为 n 的 k 个数的组合，且满足下列条件：

    只使用数字1到9
    每个数字 最多使用一次 
    返回 所有可能的有效组合的列表 。该列表不能包含相同的组合两次，组合可以以任何顺序返回。

*/
class Solution66
{
private:
    /* data */
public:
    Solution66(/* args */);
    ~Solution66();

    vector<vector<int>> combinationSum3(int k, int n);
    void backtracking(vector<vector<int>> &res, vector<int> &temp, int k, int n, int index, int sum);
};

void Solution66::backtracking(vector<vector<int>> &res, vector<int> &temp, int k, int n, int index, int sum){

    
    if (sum > n) { // 剪枝操作
        return;
    }

    if (sum == n && temp.size() == k)
    {
        res.push_back(temp);
        return;
    }
    

    for (int i = index; i < 10; i++)
    {
        temp.push_back(i);
        sum += i;
        backtracking(res, temp, k, n, ++index, sum);
        sum -= i;
        temp.pop_back();
    }
    
}

vector<vector<int>> Solution66::combinationSum3(int k, int n) {
    vector<vector<int>> res;
    vector<int> temp;
    int index = 1;
    int sum = 0;
    backtracking(res, temp, k, n, index, sum);

    return res;
}

Solution66::Solution66(/* args */)
{
}

Solution66::~Solution66()
{
}
// int main(){

//     Solution66 s66;

//     int k = 3;

//     int n = 9;

//     auto res = s66.combinationSum3(k, n);

//     ShowTowVector(res);

//     return 0;
// }


/*
    回溯算法题3：电话号码的字母组合

    给定一个仅包含数字 2-9 的字符串，返回所有它能表示的字母组合。答案可以按 任意顺序 返回。

    给出数字到字母的映射如下（与电话按键相同）。注意 1 不对应任何字母。

*/
#include <unordered_map>
#include <map>
class Solution67
{
private:
    /* data */
public:
    vector<string> result;
    string s;
    Solution67(/* args */);
    ~Solution67();
    
    const string letterMap[10] = {
        "", // 0
        "", // 1
        "abc", // 2
        "def", // 3
        "ghi", // 4
        "jkl", // 5
        "mno", // 6
        "pqrs", // 7
        "tuv", // 8
        "wxyz", // 9
    };
    vector<string> letterCombinations(string digits);
    void backtracking(const string& digits, int index);

};


void Solution67::backtracking(const string& digits, int index) {
    if (index == digits.size()) {
        result.push_back(s);
        return;
    }
    int digit = digits[index] - '0';        // 将index指向的数字转为int
    string letters = letterMap[digit];      // 取数字对应的字符集
    cout << letters << endl;
    for (int i = 0; i < letters.size(); i++) {
        s.push_back(letters[i]);            // 处理
        cout << letters[i] << " ";
        backtracking(digits, index + 1);    // 递归，注意index+1，一下层要处理下一个数字了
        s.pop_back();                       // 回溯
    }
}

vector<string> Solution67::letterCombinations(string digits) {
    s.clear();
    result.clear();
    if (digits.size() == 0) {
        return result;
    }
    backtracking(digits, 0);
    return result;
}



Solution67::Solution67(/* args */)
{
}

Solution67::~Solution67()
{
}

// int main(){

//     Solution67 s67;

//     string s = "23";

//     auto res = s67.letterCombinations(s);

//     for (int i = 0; i < res.size(); i++)
//     {
//         cout << res[i] << "  ";
//     }
//     cout << endl;

//     return 0;
// }


/*
    回溯算法题4：组合总和

    给你一个 无重复元素 的整数数组 candidates 和一个目标整数 target ，找出 candidates 中可以使数字和为目标数 target 的 所有 不同组合 ，
    并以列表形式返回。你可以按 任意顺序 返回这些组合。

    candidates 中的 同一个 数字可以 无限制重复被选取 。如果至少一个数字的被选数量不同，则两种组合是不同的。 

    对于给定的输入，保证和为 target 的不同组合数少于 150 个。

*/
class Solution68
{
private:
    /* data */
public:
    Solution68(/* args */);
    ~Solution68();

    vector<vector<int>> combinationSum(vector<int>& candidates, int target);
    void backtracking(vector<int>& candidates, vector<vector<int>> &res, vector<int> &temp, int target, int sum, int index);
};
void Solution68::backtracking(vector<int>& candidates, vector<vector<int>> &res, vector<int> &temp, int target, int sum, int index){
    // if (sum > target)   // 当可以重复选取的时候，必须加入该判断，否则会进入无限循环    若剪枝，则可以不要该判断
    // {
    //     return;
    // }
    

    if (sum == target)
    {
        res.push_back(temp);

        return;
    }
    for (int i = index; i < candidates.size(); i++)
    {   
        cout << index << "..." << endl;     // 这里 index 的值不是很理解，既然没有增减，为啥不能是 0
        // 剪枝   若要加入剪枝，则需要先排序
        if (sum + candidates[i] > target)
        {
            break;
        }

        temp.push_back(candidates[i]);
        sum += candidates[i];
        backtracking(candidates, res, temp, target, sum, i);
        temp.pop_back();
        sum -= candidates[i];
    }
    

}

// 注意这道题，元素是可重复选取的
vector<vector<int>> Solution68::combinationSum(vector<int>& candidates, int target) {
    vector<vector<int>> res;

    if (candidates.size() == 0)
    {
        return res;
    }
    
    vector<int> temp;
    sort(candidates.begin(), candidates.end());
    backtracking(candidates, res, temp, target, 0, 0);

    return res;

}
 
Solution68::Solution68(/* args */)
{
}

Solution68::~Solution68()
{
}


// int main(){

//     Solution68 s68;
//     vector<int> candidates = {2, 3, 6, 7};
//     int target = 7;
//     auto res = s68.combinationSum(candidates, target);
//     ShowTowVector(res);
//     return 0;
// }

/*
    回溯算法题5：组合总和2
*/
class Solution69
{
private:
    /* data */
public:
    Solution69(/* args */);
    ~Solution69();

    vector<vector<int>> combinationSum2(vector<int>& candidates, int target);
    void backtracking(vector<int>& candidates, set<vector<int>> &res, vector<int> &temp, int target, int index, int sum);

};
// 因为 candidates 里存在重复元素，所以会出现相同的 temp  所以可以使用 set 去重  
void Solution69::backtracking(vector<int>& candidates, set<vector<int>> &res, vector<int> &temp, int target, int index, int sum){

    if (sum == target)   // 加入剪枝，这里可以少加判断条件
    {   
        res.insert(temp);
        return;
    }
    

    for (int i = index; i < candidates.size(); i++)
    {
        if (sum + candidates[i] > target)
        {
            break;
        }

        if (i > index && candidates[i] == candidates[i - 1]){
            continue;
        }
        temp.push_back(candidates[i]);
        sum += candidates[i];
        backtracking(candidates, res, temp, target, i+1, sum);
        temp.pop_back();
        sum -= candidates[i];
    
    }
    
}

vector<vector<int>> Solution69::combinationSum2(vector<int>& candidates, int target) {
    set<vector<int>> res;
    
    vector<int> temp;
    sort(candidates.begin(), candidates.end());
    backtracking(candidates, res, temp, target, 0, 0);

    vector<vector<int>> result(res.begin(), res.end());

    return result;
}

Solution69::Solution69(/* args */)
{
}

Solution69::~Solution69()
{
}


// int main(){

//     Solution69 s69;
//     vector<int> candidates = {10,1,2,7,6,1,5};
//     int target = 8;
//     auto res = s69.combinationSum2(candidates, target);
//     ShowTowVector(res);
//     return 0;
// }


/*
    回溯算法题6：分割回文串 


    对回溯有了些理解，将回溯和 N 叉树结合便于理解    回溯操作数组   二叉树的递归操作二叉树   如果将二叉树转换成数组，那么就变成了这里的回溯，
    由于二叉树本身的结构性质，因此二叉树的遍历分左右递归（左右子树）  但其实道理都是一样的
*/

class Solution70
{
private:
    /* data */
public:
    Solution70(/* args */);
    ~Solution70();

    vector<vector<string>> partition(string s);
    // 回溯
    void backtracking(vector<vector<string>> &res, vector<string> &temp, string s, int index);
    // 判断字符串是否为回文子串
    bool judge(const string& s, int start, int end);

};


bool Solution70::judge(const string& s, int start, int end){
    for (int i = start, j = end; i < j; i++, j--) {
         if (s[i] != s[j]) {
             return false;
         }
     }
     return true;
}


void Solution70::backtracking(vector<vector<string>> &res, vector<string> &temp, string s, int index){

    if (index >= s.size())   // 这里和组合问题不同  
    {
        res.push_back(temp);
        return;
    }
    
    for (int i = index; i < s.size(); i++) {
        
        cout << index << " index" << " ";
        cout << i << " i" << endl;
        if (judge(s, index, i)) { // 是回文子串
            // 获取[index,i]在s中的子串
            string str = s.substr(index, i - index + 1);
            temp.push_back(str);

        } else {                // 如果不是则直接跳过
            continue;
        }
        backtracking(res, temp, s, i + 1); // 寻找i+1为起始位置的子串
        cout << index << ",,," << endl;
        temp.pop_back();        // 回溯过程，弹出本次已经填在的子串

    }
    
}

vector<vector<string>> Solution70::partition(string s) {
    vector<vector<string>> res;
    vector<string> temp;
    if (s.size() == 1)
    {
        temp.push_back(s);
        res.push_back(temp);
        return res;
    }

    backtracking(res, temp, s, 0);

    return res;
}

Solution70::Solution70(/* args */)
{
}

Solution70::~Solution70()
{
}


// int main(){

//     Solution70 s70;
//     string des = "aab";
//     auto res = s70.partition(des);
//     ShowTowVector<string>(res);
//     return 0;
// }


/*
    回溯算法题7：复原Ip地址
*/
class Solution71
{
private:
    /* data */
public:
    Solution71(/* args */);
    ~Solution71();

    vector<string> restoreIpAddresses(string s);

    void backtracking(vector<string> &res, string& s, int startIndex, int pointNum);

    bool judge(const string &s, int start, int end);
};

bool Solution71::judge(const string &s, int start, int end){
    if (start > end) {
            return false;
    }
    if (s[start] == '0' && start != end) { // 0开头的数字不合法
            return false;
    }
    int num = 0;
    for (int i = start; i <= end; i++) {
        if (s[i] > '9' || s[i] < '0') { // 遇到非数字字符不合法
            return false;
        }
        num = num * 10 + (s[i] - '0');
        if (num > 255) { // 如果大于255了不合法
            return false;
        }
    }
    return true;

}

// 有效 IP 地址 正好由四个整数（每个整数位于 0 到 255 之间组成，且不能含有前导 0），整数之间用 '.' 分隔。
void Solution71::backtracking(vector<string> &res, string& s, int startIndex, int pointNum) {
    if (pointNum == 3) { // 逗点数量为3时，分隔结束
        // 判断第四段子字符串是否合法，如果合法就放进result中
        if (judge(s, startIndex, s.size() - 1)) {
            res.push_back(s);
        }
        return;
    }
    for (int i = startIndex; i < s.size(); i++) {
        if (judge(s, startIndex, i)) { // 判断 [startIndex,i] 这个区间的子串是否合法
            s.insert(s.begin() + i + 1 , '.');  // 在i的后面插入一个逗点
            pointNum++;
            backtracking(res, s, i + 2, pointNum);   // 插入逗点之后下一个子串的起始位置为i+2
            pointNum--;                         // 回溯
            s.erase(s.begin() + i + 1);         // 回溯删掉逗点
        } else break; // 不合法，直接结束本层循环
    }
}

vector<string> Solution71::restoreIpAddresses(string s) {
    vector<string> res;
    if (s.size() < 4 || s.size() > 12) return res; 

    backtracking(res, s, 0, 0);
    
    return res;

}
Solution71::Solution71(/* args */)
{
}

Solution71::~Solution71()
{
}



// int main(){

//     Solution71 s71;
//     string des = "25525511135";
//     auto res = s71.restoreIpAddresses(des);
//     for (int i = 0; i < res.size(); i++)
//     {
//         cout << res[i] << " ";
//     }
    
//     cout << endl;
//     return 0;
// }



/*
    回溯算法题8：子集问题
*/

class Solution72
{
private:
    /* data */
public:
    Solution72(/* args */);
    ~Solution72();

    vector<vector<int>> subsets(vector<int>& nums);

    void backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index);
};

void Solution72::backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index){
    res.push_back(temp);
    if (index >= nums.size())
    {
        return;
    }
    
    for (int i = index; i < nums.size(); i++)
    {   
        // 获得子串
        // 将子串放入 temp
        temp.push_back(nums[i]);
        backtracking(nums, res, temp, i+1);
        temp.pop_back();
    }
    
    return;
}

// 思考：能不能当作切割处理
vector<vector<int>> Solution72::subsets(vector<int>& nums) {

    vector<vector<int>> res;
    vector<int> temp;
    
    backtracking(nums, res, temp, 0);

    return res;
}

Solution72::Solution72(/* args */)
{
}

Solution72::~Solution72()
{
}



// int main(){

//     Solution72 s72;
//     vector<int> des = {1, 2, 3};
//     auto res = s72.subsets(des);
//     ShowTowVector(res);
//     return 0;
// }



/*
    回溯算法题9：子集问题2
*/
class Solution73
{
private:
    /* data */
public:
    Solution73(/* args */);
    ~Solution73();

    vector<vector<int>> subsetsWithDup(vector<int>& nums);

    void backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index);
};

void Solution73::backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index){
    res.push_back(temp);
    if (index >= nums.size())
    {
        return;
    }
    
    for (int i = index; i < nums.size(); i++)
    {   
        // 与上一题不同的是，当遇到相同元素，则 continue
        if (i > index && nums[i] == nums[i- 1] )
        {
            continue;
        }
        
        // 获得子串
        // 将子串放入 temp
        temp.push_back(nums[i]);
        backtracking(nums, res, temp, i+1);
        temp.pop_back();
    }
    
    return;

}

vector<vector<int>> Solution73::subsetsWithDup(vector<int>& nums) {
    vector<vector<int>> res;
    vector<int> temp;
    int index = 0;
    sort(nums.begin(), nums.end());
    backtracking(nums, res, temp, index);

    return res;

}


Solution73::Solution73(/* args */)
{
}

Solution73::~Solution73()
{
}


// int main(){

// Solution73 s73;
//     vector<int> des = {1, 2, 2};
//     auto res = s73.subsetsWithDup(des);
//     ShowTowVector(res);
//     return 0;
// }

/*
    回溯算法题10：递增子序列                  不能排序！！！
*/
#include<set>
class Solution74
{
private:
    /* data */
public:
    Solution74(/* args */);
    ~Solution74();

    vector<vector<int>> findSubsequences(vector<int>& nums);

    void backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index, set<vector<int>> &uset);

    // 判断是否递增序列
    bool judge(const vector<int> &v);
};
bool Solution74::judge(const vector<int> &v){

    for (int i = 1; i < v.size(); i++)
    {
        if (v[i] < v[i - 1])
        {
            return false;
        }
        
    }
    
    return true;
}

// 这道题完全可以先排序，达到递增序列条件，再按照上一条求子集问题2的方式进行即可
void Solution74::backtracking(vector<int>& nums, vector<vector<int>> &res, vector<int> &temp, int index, set<vector<int>> &uset){

    if (temp.size() >= 2)   // 当元素大于等于 2 的时候 检查该数组是否递增    需要加入set去重，因为重复元素不一定挨在一起了？（没有排序）
    {   
        if (judge(temp) && uset.find(temp) == uset.end())
        {   
            res.push_back(temp);
        }
        
        if (judge(temp))
        {
            uset.insert(temp);
        }
        
        
    }
    
    if (index >= nums.size())
    {
        return;
    }
    

    for (int i = index; i < nums.size(); i++)
    {
        if (i > index && nums[i] == nums[i - 1]) continue;
        
        temp.push_back(nums[i]);
        backtracking(nums, res, temp, i+1, uset);
        temp.pop_back();
    }
    
}

vector<vector<int>> Solution74::findSubsequences(vector<int>& nums) {

    vector<vector<int>> res;

    vector<int> temp;
    set<vector<int>> uset;
    int index = 0;

    backtracking(nums, res, temp, index, uset);


    return res;

}

Solution74::Solution74(/* args */)
{
}

Solution74::~Solution74()
{
}


// int main(){

// Solution74 s74;
//     vector<int> des = {4, 7, 6, 7};
//     auto res = s74.findSubsequences(des);
//     ShowTowVector(res);
//     return 0;
// }


/*
    回溯算法题10：全排列

    给定一个不含重复数字的数组 nums ，返回其 所有可能的全排列 。你可以 按任意顺序 返回答案。
*/

class Solution75
{
private:
    /* data */
public:
    Solution75(/* args */);
    ~Solution75();

    vector<vector<int>> permute(vector<int>& nums);

    void backtracking(vector<int> &nums, vector<vector<int>> &res, vector<int> &temp, vector<bool> &used);
};
// 与组合问题最大的区别是  需要从零开始
void Solution75::backtracking(vector<int> &nums, vector<vector<int>> &res, vector<int> &temp, vector<bool> &used){

    if (temp.size() == nums.size())
    {
        res.push_back(temp);
        return;
    }
    

    for (int i = 0; i < nums.size(); i++)
    {   
        if (used[i])
        {
            continue;
        }
        temp.push_back(nums[i]);
        used[i] = true;
        backtracking(nums, res, temp, used);
        temp.pop_back();
        used[i] = false;
    }
    
}

vector<vector<int>> Solution75::permute(vector<int>& nums) {
    vector<vector<int>> res;
    vector<int> temp;
    vector<bool> used(nums.size(), false);

    backtracking(nums, res, temp, used);

    return res;


}

Solution75::Solution75(/* args */)
{
}

Solution75::~Solution75()
{
}



// int main(){

//     Solution75 s75;
//     vector<int> des = {1, 2, 3};
//     auto res = s75.permute(des);
//     ShowTowVector(res);
//     return 0;
// }

/*
    回溯算法题11：全排列2
*/
class Solution76
{
private:
    /* data */
public:
    Solution76(/* args */);
    ~Solution76();

    vector<vector<int>> permuteUnique(vector<int>& nums);

    void backtracking(vector<int> &nums, vector<vector<int>> &res, vector<int> &temp, vector<bool> &used);
};

void Solution76::backtracking(vector<int> &nums, vector<vector<int>> &res, vector<int> &temp, vector<bool> &used){
    if (temp.size() == nums.size())
    {
        res.push_back(temp);
        return;
    }
    

    for (int i = 0; i < nums.size(); i++)
    {   
        if (i > 0 && nums[i] == nums[i - 1] && used[i - 1] == false) {  // 不好理解    总结：同一树枝上有两个相同元素可以重复选取，同一树层上有两个相同元素不可重复选取
            continue;
        }
        if (used[i] == false)
        {
            temp.push_back(nums[i]);
            used[i] = true;
            backtracking(nums, res, temp, used);
            temp.pop_back();
            used[i] = false;
        }
        
    }


}

vector<vector<int>> Solution76::permuteUnique(vector<int>& nums) {
    vector<vector<int>> res;
    vector<int> temp;
    vector<bool> used(nums.size(), false);
    sort(nums.begin(), nums.end());
    backtracking(nums, res, temp, used);

    return res;


}

Solution76::Solution76(/* args */)
{
}

Solution76::~Solution76()
{
}



// int main(){

//     Solution76 s76;
//     vector<int> des = {1, 1, 2};
//     auto res = s76.permuteUnique(des);
//     ShowTowVector(res);
//     return 0;
// }




/*
    贪心算法题1：分发饼干

    假设你是一位很棒的家长，想要给你的孩子们一些小饼干。但是，每个孩子最多只能给一块饼干。
    对每个孩子 i，都有一个胃口值 g[i]，这是能让孩子们满足胃口的饼干的最小尺寸；并且每块饼干 j，
    都有一个尺寸 s[j] 。如果 s[j] >= g[i]，我们可以将这个饼干 j 分配给孩子 i ，这个孩子会得到满足。
    你的目标是尽可能满足越多数量的孩子，并输出这个最大数值。

*/

class Solution77
{
private:
    /* data */
public:
    Solution77(/* args */);
    ~Solution77();

    int findContentChildren(vector<int>& g, vector<int>& s);
};

// g 代表胃口   s 代表饼干尺寸   
int Solution77::findContentChildren(vector<int>& g, vector<int>& s) {
    //1、排序后，从后向前遍历 ------> 这里的局部最优就是大饼干喂给胃口大的，充分利用饼干尺寸喂饱一个，全局最优就是喂饱尽可能多的小孩。
    //2、考虑使用双指针 ------> 降低时间复杂度
    sort(g.begin(), g.end());
    sort(s.begin(), s.end());

    int res = 0;
    int index = s.size() - 1;  // 最大一块饼干的索引

    for (int i = g.size() - 1; i >= 0; i--)
    {   
        if (index >= 0 && s[index] >= g[i]) {
            res++;
            index--;
        }
          
    }
    
    return res;

}

Solution77::Solution77(/* args */)
{
}

Solution77::~Solution77()
{
}



// int main(){

//     Solution77 s77;
//     vector<int> g = {1, 2};
//     vector<int> s = {1, 2, 3};
    
//     int res = s77.findContentChildren(g, s);

//     cout << res << endl;
//     return 0;
// }



/*
    贪心算法题2：摆动序列
*/

class Solution78
{
private:
    /* data */
public:
    Solution78(/* args */);
    ~Solution78();

    int wiggleMaxLength(vector<int>& nums);
};

int Solution78::wiggleMaxLength(vector<int>& nums) {
    
    int res = 1;
    if (nums.size() == 1) return res;

    vector<int> record(nums.size() - 1, -1);  // 使用 record 记录上一次查找为正还是负  1 表示正  0 表示负

    if (nums[1] - nums[0] > 0) record[0] = 1;
    if (nums[1] - nums[0] < 0) record[0] = 0;
    
    for (int i = 2; i < nums.size(); i++)
    {
        if ((nums[i] - nums[i - 1] > 0 && record[i - 2] == 0) || (nums[i] - nums[i - 1] < 0 && record[i - 2] == 1))
        {
            res ++;
        }
        if (nums[i] - nums[i - 1] > 0)
        {
            record[i-1] = 1;
        }else if (nums[i] - nums[i - 1] < 0)
        {
            record[i-1] = 0;
        }
    }
    
    return res;
}

Solution78::Solution78(/* args */)
{
}

Solution78::~Solution78()
{
}


// int main(){

//     Solution78 s78;
//     vector<int> des = {0, 0, 0, 0};
    
//     int res = s78.wiggleMaxLength(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题3：最大子数组和
*/

class Solution79
{
private:
    /* data */
public:
    Solution79(/* args */);
    ~Solution79();

    int maxSubArray(vector<int>& nums);
};

int Solution79::maxSubArray(vector<int>& nums) {
    int res = INT32_MIN;

    int count = 0;
    for (int i = 0; i < nums.size(); i++)
    {
        count += nums[i];
        if (count > res)
        {
            res = count;
        }
        if (count <= 0) count = 0;
        
    }
    
    return res;
}

Solution79::Solution79(/* args */)
{
}

Solution79::~Solution79()
{
}



// int main(){

//     Solution79 s79;
//     vector<int> des = {-2,1,-3,4,-1,2,1,-5,4};
    
//     int res = s79.maxSubArray(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题4：买卖股票的最佳时机

    输入：prices = [7,1,5,3,6,4]
    输出：7
    解释：在第 2 天（股票价格 = 1）的时候买入，在第 3 天（股票价格 = 5）的时候卖出, 这笔交易所能获得利润 = 5 - 1 = 4 。
         随后，在第 4 天（股票价格 = 3）的时候买入，在第 5 天（股票价格 = 6）的时候卖出, 这笔交易所能获得利润 = 6 - 3 = 3 。
        总利润为 4 + 3 = 7 。
*/


class Solution80
{
private:
    /* data */
public:
    Solution80(/* args */);
    ~Solution80();

    int maxProfit(vector<int>& prices);
};

int Solution80::maxProfit(vector<int>& prices) {
    int res = 0;
    for (int i = 1; i < prices.size(); i++)
    {
        res += max(prices[i] - prices[i - 1], 0);
    }
    

    return res;
}

Solution80::Solution80(/* args */)
{
}

Solution80::~Solution80()
{
}


// int main(){

//     Solution80 s80;
//     vector<int> des = {-2,1,-3,4,-1,2,1,-5,4};
    
//     int res = s80.maxProfit(des);

//     cout << res << endl;
//     return 0;
// }

/*
    贪心算法题5：跳跃游戏

    输入：nums = [2,3,1,1,4]
    输出：true
    解释：可以先跳 1 步，从下标 0 到达下标 1, 然后再从下标 1 跳 3 步到达最后一个下标。
*/
class Solution81
{
private:
    /* data */
public:
    Solution81(/* args */);
    ~Solution81();

    bool canJump(vector<int>& nums);
};


bool Solution81::canJump(vector<int>& nums) {
    int cover = 0;
    if (nums.size() == 1)
    {
        return true;
    }
    
    for (int i = 0; i <= cover; i++)
    {
        cover = max(i + nums[i], cover);
        if (cover >= nums.size() - 1)
        {
            return true;
        }
        
    }
    
    return false;
}

Solution81::Solution81(/* args */)
{
}

Solution81::~Solution81()
{
}



// int main(){

//     Solution81 s81;
//     vector<int> des = {2, 3, 1, 1, 4};
    
//     bool res = s81.canJump(des);

//     cout << res << endl;
//     return 0;
// }



/*
    贪心算法题6：跳跃游戏2

    
*/
class Solution82
{
private:
    /* data */
public:
    Solution82(/* args */);
    ~Solution82();

    int jump(vector<int>& nums);
};

int Solution82::jump(vector<int>& nums) {
    if (nums.size() == 1)
    {
        return 0;
    }
    

    int res = 0; // 记录步数

    int cur = 0; // 当前最大覆盖范围下标
    int next = 0; // 下一步最大覆盖范围下标

    for (int i = 0; i < nums.size(); i++)
    {
        next = max(nums[i] + i, next); // 更新下一步最大覆盖范围下标
        if (i == cur)
        {
            if (cur != nums.size() - 1)
            {
                
                res ++;
                cur = next;
                if (next >= nums.size() - 1)
                {
                    break;
                }
                
            }else{
                break;
            }
        }
        
    }
    
    return res;
}

Solution82::Solution82(/* args */)
{
}

Solution82::~Solution82()
{
}


// int main(){

//     Solution82 s82;
//     vector<int> des = {2, 3, 1, 1, 4};
    
//     int res = s82.jump(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题7：K 次取反后最大化的数组和
*/

class Solution83
{
private:
    /* data */
public:
    Solution83(/* args */);
    ~Solution83();

    int largestSumAfterKNegations(vector<int>& nums, int k);
};

// 写一个按照绝对值从大到小排序的仿函数  
bool sortFunc(int a, int b){

    return abs(a) > abs(b);

}


// 思路  单数就取 负数绝对值最大的   双数就取一个负的绝对值最大的 一个 0   全正数就取最小的数
int Solution83::largestSumAfterKNegations(vector<int>& nums, int k) {
    int res = 0;

    sort(nums.begin(), nums.end(), sortFunc);

    for (int i = 0; i < nums.size(); i++)
    {
        if (nums[i] < 0 && k > 0)
        {
            nums[i] *= -1;
            k--;
        }
        
    }
    
    if (k > 0 && k % 2 == 1)
    {
        nums[nums.size() - 1] *= -1;
    }

    for(auto i: nums){

        res += i;
    }

    return res;
}
Solution83::Solution83(/* args */)
{
}

Solution83::~Solution83()
{
}


// int main(){

//     Solution83 s83;
//     vector<int> des = {4, 2, 3};
//     int k = 1;
//     int res = s83.largestSumAfterKNegations(des, k);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题8：加油站
*/

class Solution84
{
private:
    /* data */
public:
    Solution84(/* args */);
    ~Solution84();

    int canCompleteCircuit(vector<int>& gas, vector<int>& cost);
};
// 输入: gas = [1,2,3,4,5], cost = [3,4,5,1,2]
// 输出: 3
int Solution84::canCompleteCircuit(vector<int>& gas, vector<int>& cost) {
     int curSum = 0;
    int min = INT_MAX; // 从起点出发，油箱里的油量最小值
    for (int i = 0; i < gas.size(); i++) {
        int rest = gas[i] - cost[i];
        curSum += rest;
        if (curSum < min) {
            min = curSum;
        }
    }
    if (curSum < 0) return -1;  // 情况1
    if (min >= 0) return 0;     // 情况2
                                // 情况3
    for (int i = gas.size() - 1; i >= 0; i--) {
        int rest = gas[i] - cost[i];
        min += rest;
        if (min >= 0) {
            return i;
        }
    }
    return -1;
}

Solution84::Solution84(/* args */)
{
}

Solution84::~Solution84()
{
}


// int main(){

//     Solution84 s84;
//     vector<int> des = {1, 2, 3, 4, 5};
//     vector<int> des2 = {3, 4, 5, 1, 2};

//     int res = s84.canCompleteCircuit(des, des2);

//     cout << res << endl;
//     return 0;
// }



/*
    贪心算法题9：柠檬水找零
*/

class Solution85
{
private:
    /* data */
public:
    Solution85(/* args */);
    ~Solution85();

    bool lemonadeChange(vector<int>& bills);
};

bool Solution85::lemonadeChange(vector<int>& bills) {

    int five = 0, ten = 0, twenty = 0;
    for (int bill : bills) {
        // 情况一
        if (bill == 5) five++;
        // 情况二
        if (bill == 10) {
            if (five <= 0) return false;
            ten++;
            five--;
        }
        // 情况三
        if (bill == 20) {
            // 优先消耗10美元，因为5美元的找零用处更大，能多留着就多留着
            if (five > 0 && ten > 0) {
                five--;
                ten--;
                twenty++; // 其实这行代码可以删了，因为记录20已经没有意义了，不会用20来找零
            } else if (five >= 3) {
                five -= 3;
                twenty++; // 同理，这行代码也可以删了
            } else return false;
        }
    }
    return true;
}

Solution85::Solution85(/* args */)
{
}

Solution85::~Solution85()
{
}



// int main(){

//     Solution85 s85;
//     vector<int> des = {5, 5, 5, 10, 20};

//     int res = s85.lemonadeChange(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题10：根据身高重建队列
*/
class Solution86
{
private:
    /* data */
public:
    Solution86(/* args */);
    ~Solution86();

    vector<vector<int>> reconstructQueue(vector<vector<int>>& people);
};

static bool cmp(const vector<int>& a, const vector<int>& b) {
    if (a[0] == b[0]) return a[1] < b[1];
    return a[0] > b[0];
}
vector<vector<int>> Solution86::reconstructQueue(vector<vector<int>>& people) {
    sort (people.begin(), people.end(), cmp);
    vector<vector<int>> que;
    for (int i = 0; i < people.size(); i++) {
        int position = people[i][1];
        que.insert(que.begin() + position, people[i]);
    }
    return que;

}

Solution86::Solution86(/* args */)
{
}

Solution86::~Solution86()
{
}



// int main(){

//     Solution86 s86;
//     vector<vector<int>> des = {{7,0},{4,4},{7,1},{5,0},{6,1},{5,2}};

//     auto res = s86.reconstructQueue(des);

//     ShowTowVector(res);
//     return 0;
// }


/*
    贪心算法题11：用最小数量的剪引爆气球           未解决
*/

class Solution87
{
private:
    /* data */
public:
    Solution87(/* args */);
    ~Solution87();

    int findMinArrowShots(vector<vector<int>>& points);
};

int Solution87::findMinArrowShots(vector<vector<int>>& points) {

    return 0;
}

Solution87::Solution87(/* args */)
{
}

Solution87::~Solution87()
{
}



// int main(){

//     Solution87 s87;
//     vector<vector<int>> des = {{7,0},{4,4},{7,1},{5,0},{6,1},{5,2}};

//     int res = s87.findMinArrowShots(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题12：无重叠区间

    输入: intervals = [[1,2],[2,3],[3,4],[1,3]]
    输出: 1
    解释: 移除 [1,3] 后，剩下的区间没有重叠。
*/

class Solution88
{
private:
    /* data */
public:
    Solution88(/* args */);
    ~Solution88();

    int eraseOverlapIntervals(vector<vector<int>>& intervals);
};

// 按照区间右边界排序
bool cmp2(const vector<int>& a, const vector<int>& b) {
    return a[1] < b[1];
}
int Solution88::eraseOverlapIntervals(vector<vector<int>>& intervals) {
    if (intervals.size() == 0) return 0;
    sort(intervals.begin(), intervals.end(), cmp2);
    int count = 1; // 记录非交叉区间的个数
    int end = intervals[0][1]; // 记录区间分割点
    for (int i = 1; i < intervals.size(); i++) {
        if (end <= intervals[i][0]) {
            end = intervals[i][1];
            count++;
        }
    }
    return intervals.size() - count;

}

Solution88::Solution88(/* args */)
{
}

Solution88::~Solution88()
{
}


// int main(){

//     Solution88 s88;
//     vector<vector<int>> des = {{1,2},{2,3},{3,4},{1,3}};

//     int res = s88.eraseOverlapIntervals(des);

//     cout << res << endl;
//     return 0;
// }


/*
    贪心算法题13：划分字母区间

*/

class Solution89
{
private:
    /* data */
public:
    Solution89(/* args */);
    ~Solution89();

    vector<int> partitionLabels(string s);
};

vector<int> Solution89::partitionLabels(string s) {
    vector<int> res;
    
    int hash[27] = {0}; // 初始化数组

    for (int i = 0; i < s.size(); i++)  // 找到了每个字符的最远边际
    {
        hash[s[i] - 'a'] = i;
    }
    int right = 0;
    int left = 0;
    for (int i = 0; i < s.size(); i++)
    {
        right = max(hash[s[i] - 'a'], right);
        if (i == right)
        {
            res.push_back(right - left + 1);
            left = i + 1;
        }
        
    }
    
    return res;
}

Solution89::Solution89(/* args */)
{
}

Solution89::~Solution89()
{
}


// int main(){

//     Solution89 s89;
//     string des = "ababcbacadefegdehijhklij";

//     vector<int> res = s89.partitionLabels(des);

//     for (int i = 0; i < res.size(); i++)
//     {
//         cout << res[i] << endl;
//     }
    
//     return 0;
// }



/*
    贪心算法题14：合并区间

*/
class Solution90
{
private:
    /* data */
public:
    Solution90(/* args */);
    ~Solution90();

    vector<vector<int>> merge(vector<vector<int>>& intervals);
};

vector<vector<int>> Solution90::merge(vector<vector<int>>& intervals) {
    vector<vector<int>> result;
    if (intervals.size() == 0) return result;
    // 排序的参数使用了lambda表达式
    sort(intervals.begin(), intervals.end(), [](const vector<int>& a, const vector<int>& b){return a[0] < b[0];});

    result.push_back(intervals[0]);
    for (int i = 1; i < intervals.size(); i++) {
        if (result.back()[1] >= intervals[i][0]) { // 合并区间
            result.back()[1] = max(result.back()[1], intervals[i][1]);
        } else {
            result.push_back(intervals[i]);
        }
    }
    return result;


}

Solution90::Solution90(/* args */)
{
}

Solution90::~Solution90()
{
}



// int main(){

//     Solution90 s90;
//     vector<vector<int>> des = {{1,3},{2,6},{8,10},{15,18}};
//     auto res = s90.merge(des);
//     ShowTowVector(res);
    
//     return 0;
// }



/*
    贪心算法题15：合并区间

*/
class Solution91
{
private:
    /* data */
public:
    Solution91(/* args */);
    ~Solution91();

    int monotoneIncreasingDigits(int n);
};


int Solution91::monotoneIncreasingDigits(int n) {
    string strNum = to_string(n);
    // flag用来标记赋值9从哪里开始
    // 设置为这个默认值，为了防止第二个for循环在flag没有被赋值的情况下执行
    int flag = strNum.size();
    for (int i = strNum.size() - 1; i > 0; i--) {
        if (strNum[i - 1] > strNum[i] ) {
            flag = i;
            strNum[i - 1]--;
        }
    }
    for (int i = flag; i < strNum.size(); i++) {
        strNum[i] = '9';
    }
    return stoi(strNum);
}

Solution91::Solution91(/* args */)
{
}

Solution91::~Solution91()
{
}


// int main(){

//     Solution91 s91;
//     int des = 10;
//     auto res = s91.monotoneIncreasingDigits(des);
//     cout << res << endl;
    
//     return 0;
// }


/*
    贪心算法题16：买卖股票的最佳时机，含手续费
*/

class Solution92
{
private:
    /* data */
public:
    Solution92(/* args */);
    ~Solution92();

    int maxProfit(vector<int>& prices, int fee);
};

int Solution92::maxProfit(vector<int>& prices, int fee) {
    int result = 0;
    int minPrice = prices[0]; // 记录最低价格
    for (int i = 1; i < prices.size(); i++) {
        // 情况二：相当于买入
        if (prices[i] < minPrice) minPrice = prices[i];

        // 情况三：保持原有状态（因为此时买则不便宜，卖则亏本）
        if (prices[i] >= minPrice && prices[i] <= minPrice + fee) {
            continue;
        }

        // 计算利润，可能有多次计算利润，最后一次计算利润才是真正意义的卖出
        if (prices[i] > minPrice + fee) {
            result += prices[i] - minPrice - fee;
            minPrice = prices[i] - fee; // 情况一，这一步很关键
        }
    }
    return result;

}

Solution92::Solution92(/* args */)
{
}

Solution92::~Solution92()
{
}

// int main(){

//     Solution92 s92;
//     vector<int> des = {1, 3, 2, 8, 4, 9};
//     int n = 2;
//     auto res = s92.maxProfit(des, n);
//     cout << res << endl;
    
//     return 0;
// }



/*
    动规是由前一个状态推导出来的，而贪心是局部直接选最优的。

    动态规划算法题1：斐波那契数列
*/


class Solution93
{
private:
    /* data */
public:
    Solution93(/* args */);
    ~Solution93();

    int fib(int n);
};


int Solution93::fib(int n) {

    if (n <= 1) return n;
    
    vector<int> dp(n+1);

    dp[0] = 0;
    dp[1] = 1;
    
    for (int i = 2; i <= n; i++)
    {   
       dp[i] = dp[i-1] + dp[i-2];
       cout << dp[i] << endl;
    }


    return dp[n];
}

Solution93::Solution93(/* args */)
{
}

Solution93::~Solution93()
{
}


// int main(){

//     Solution93 s93;

//     int res = s93.fib(4);

//     cout << res << endl;
//     return 0;
// }




/*
    动态规划算法题2：爬楼梯       这道题的本质就是斐波那契数列  dp[i] = dp[i - 1] + dp[i - 2]   i代表第几层楼梯
*/

class Solution94
{
private:
    /* data */
public:
    Solution94(/* args */);
    ~Solution94();

    int climbStairs(int n);
};


int Solution94::climbStairs(int n) {
    // 1、确定递推公式
    // 2、初始化动归数组
    int dp[n+1];
    dp[1] = 1;
    dp[2] = 2;
    // 3、遍历
    for (int i = 3; i <= n; i++)
    {
        dp[i] =  dp[i - 1] + dp[i - 2]; 
    }
    

    return dp[n];

}

Solution94::Solution94(/* args */)
{
}

Solution94::~Solution94()
{
}


// int main(){
//     Solution94 s94;

//     int res = s94.climbStairs(4);
//     cout << res << endl;
//     return 0;
// }




/*
    动态规划算法题3：使用最小花费爬楼梯
*/

class Solution95
{
private:
    /* data */
public:
    Solution95(/* args */);
    ~Solution95();
    
    int minCostClimbingStairs(vector<int>& cost);
};

Solution95::Solution95(/* args */)
{
}

Solution95::~Solution95()
{
}

int Solution95::minCostClimbingStairs(vector<int>& cost) {

    int res = 0;


    int dp[cost.size() + 1];
    dp[0] = 0;
    dp[1] = 0;

    for (int i = 2; i <= cost.size(); i++)
    {
        dp[i] = min(dp[i - 1] + cost[i - 1], dp[i - 2] + cost[i - 2]);
    }

    return dp[cost.size()];
}

// int main(){
//     Solution95 s95;
//     // vector<int> cost = {10, 15, 20};
//     vector<int> cost = {1,100,1,1,1,100,1,1,100,1};
//     int res = s95.minCostClimbingStairs(cost);
//     cout << res << endl;
//     return 0;
// }



/*
    动态规划算法题4：不同路径
*/

class Solution96
{
private:
    /* data */
public:
    Solution96(/* args */);
    ~Solution96();

    int uniquePaths(int m, int n);
};

int Solution96::uniquePaths(int m, int n) {

    int dp[m][n];  // dp[m][n] 表示从 0， 0 到 dp[m][n] 的路径个数
    for (int i = 0; i < m; i++) dp[i][0] = 1;    
    for (int j = 0; j < n; j++) dp[0][j] = 1;

    for (int i = 1; i < m; i++)
    {
        for (int j = 1; j < n; j++)
        {
            dp[i][j] = dp[i-1][j] + dp[i][j-1];
        }
        
    }
    
    return dp[m-1][n-1];

}

Solution96::Solution96(/* args */)
{
}

Solution96::~Solution96()
{
}




// int main(){
//     Solution96 s96;
//     int m = 3;
//     int n = 7;
//     int res = s96.uniquePaths(m, n);
//     cout << res << endl;
//     return 0;
// }



/*
    动态规划算法题5：不同路径2
*/
class Solution97
{
private:
    /* data */
public:
    Solution97(/* args */);
    ~Solution97();

    int uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid);
};


int Solution97::uniquePathsWithObstacles(vector<vector<int>>& obstacleGrid) {
    int m = obstacleGrid.size();
    int n = obstacleGrid[0].size();
	if (obstacleGrid[m - 1][n - 1] == 1 || obstacleGrid[0][0] == 1) //如果在起点或终点出现了障碍，直接返回0
            return 0;
        vector<vector<int>> dp(m, vector<int>(n, 0));
        for (int i = 0; i < m && obstacleGrid[i][0] == 0; i++) dp[i][0] = 1;
        for (int j = 0; j < n && obstacleGrid[0][j] == 0; j++) dp[0][j] = 1;
        for (int i = 1; i < m; i++) {
            for (int j = 1; j < n; j++) {
                if (obstacleGrid[i][j] == 1) continue;   // 与上一题的唯一区别，遇到障碍物则跳过该路径
                dp[i][j] = dp[i - 1][j] + dp[i][j - 1];
            }
        }
    return dp[m - 1][n - 1];
}

Solution97::Solution97(/* args */)
{
}

Solution97::~Solution97()
{
}

// int main(){
//     Solution97 s97;
//     vector<vector<int>> obstacleGrid = {{0, 0, 0}, {0, 1, 0}, {0, 0, 0}};
//     int res = s97.uniquePathsWithObstacles(obstacleGrid);
//     cout << res << endl;
//     return 0;
// }


/* 
   动态规划算法题6：整数拆分            未解决



   给定一个正整数 n ，将其拆分为 k 个 正整数 的和（ k >= 2 ），并使这些整数的乘积最大化。

返回 你可以获得的最大乘积 。

 

    示例 1:

    输入: n = 2
    输出: 1
    解释: 2 = 1 + 1, 1 × 1 = 1。
    示例 2:

    输入: n = 10
    输出: 36
    解释: 10 = 3 + 3 + 4, 3 × 3 × 4 = 36。


*/

class Solution98
{
private:
    /* data */
public:
    Solution98(/* args */);
    ~Solution98();

    int integerBreak(int n);
};


int Solution98::integerBreak(int n) {
    vector<int> dp(n + 1);
        dp[2] = 1;
        for (int i = 3; i <= n ; i++) {
            for (int j = 1; j <= i / 2; j++) {
                dp[i] = max(dp[i], max((i - j) * j, dp[i - j] * j));
            }
        }
        return dp[n];
}
Solution98::Solution98(/* args */)
{
}

Solution98::~Solution98()
{
}



// int main(){


//     Solution98 s98;
    
//     int res = s98.integerBreak(6);


//     cout << res << endl;

//     return 0;
// }


//---------------------------------------------------------------------------------------------------------------------------
// int main(){

    // vector<int> nums = {0,1,2,2,3,0,4,2};
    // int target = 2;

    // Solution2 s;
    // s.removeElement(nums, target);
    // Print<int> (nums);
    


    // Solution3 s3;
    // vector <int> nums3 = {-7,-3,2,3,11};

    // auto res = s3.sortedSquares2(nums3);
    // Print<int> (res);



    // Solution4 s4;
    // int target = 7;
    // vector <int> nums = {2,3,1,2,4,3};

    // auto res = s4.minSubArrayLen(target, nums);
    // cout << "result========================" << endl;
    // cout << res << endl;


    // Solution5 s5;
    // int n = 3;
    // auto res = s5.generateMatrix(n);

    // for (auto i : res)
    // {
    //     for (auto j : i)
    //     {
    //         cout << j << endl;
    //     }
        
    // }


    // #include "Timer.h"

    // {
    // Timer timer;

    // int value = 0;
    // for (int i = 0; i < 10000; i++)
    // {   
    //     value ++;
    // }
    
    // std::cout << value << endl;

    // }

    // ListNode *head = new ListNode(1);
    // int arr[7] = {2, 6, 3, 4, 5, 7};
    // int count = 6;


    // ListNode *temp = head;
    // for (int i = 0; i < count; i++)
    // {   
    //      while (true)
    //     {   
    //         if (temp->next == NULL)
    //         {
    //             temp->next = new ListNode(arr[i]);
    //             break;
    //         }else{
    //             temp = temp->next;
    //         }
    //     }
        
    // }
    // ListNode *temp3 = head;
    // while (temp3 != NULL)
    // {
    //     std:: cout << temp3->val << endl;
    //     temp3 = temp3->next;
        

    // }
    
    // std::cout << "--------------------------------" << endl;
    // Solution6 s6;
    // s6.removeElements(head, 6);

    // ListNode *temp2 = head;
    // while (temp2 != NULL)
    // {
    //     std:: cout << temp2->val << endl;
    //     temp2 = temp2->next;
        

    // }
    
    // delete temp2;


    // MyLinkedList* obj = new MyLinkedList();

    // std::cout << "----------- 1 -------------\n";
    // printLinkedList(obj->getData());

    // int val = 1;
    // obj->addAtHead(val);

    // int val2 = 3;
    // obj->addAtTail(val2);

    // int index2 = 1;
    // int val3 = 2;
    // obj->addAtIndex(index2,val3);
    // std::cout << "------------ 2 ------------\n";
    // printLinkedList(obj->getData());

    // int index = 1;
    // int param_1 = obj->get(index);
    // std::cout << param_1 << endl;

    // obj->deleteAtIndex(1);
    // std::cout << "------------- 3 -----------\n";
    // printLinkedList(obj->getData());
    
    // int param_2 = obj->get(1);
    // std::cout << param_2 << endl;




    // Solution7 s7;

    // printLinkedList(s7.getDate());

    // ListNode* res = s7.reverseList(s7.getDate());

    // printLinkedList(res);



    // Solution8 s8;
    // printLinkedList(s8.setDate());
    // ListNode* res = s8.swapPairs(s8.setDate());
    // printLinkedList(res);



    // Solution9 s9;
    // printLinkedList(s9.getDate());
    // int n = 2;
    // ListNode* res = s9.removeNthFromEnd(s9.getDate(), n);
    // printLinkedList(s9.getDate());



    // Solution10 s10;
    // printPairLinkedList(s10.getData());
    // ListNode* res = s10.getIntersectionNode(s10.getData().first, s10.getData().second);
    // printLinkedList(res);



    // 链表里虚拟头节点  可以大大减少不必要的麻烦
    // Solution11 s11;
    // ListNode* res;
    // res = s11.detectCycle(s11.getData());
    // std::cout << endl;
    // std::cout << res->val << endl;
    


    // Solution12 s12;
    // string s = "anagram";
    // string t = "nagaram";
    // bool res = s12.isAnagram(s, t);
    // std::cout << res << endl;


    // Solution13 s13;
    // vector<int> num1 = {4, 9, 5};
    // vector<int> num2 = {9, 4, 9, 8, 4};
    // auto res = s13.intersection(num1, num2);

    // for (auto i = res.begin(); i != res.end(); i++)
    // {
    //     std::cout << *i << endl;
    // }
    


    // Solution14 s14;
    // int des = 7;
    // bool res = s14.isHappy(des);
    // cout << res << endl;



    // Solution15 s15;
    // vector<int> v1 = {1, 2};
    // vector<int> v2 = {-2, -1};
    // vector<int> v3 = {-1, 2};
    // vector<int> v4 = {0, 2};

    // int res = s15.fourSumCount(v1, v2, v3, v4);
    // cout << res << endl;



    // Solution16 s16;
    // string ransomNote = "bg";
    // string magazine = "efjbdfbdgfjhhaiigfhbaejahgfbbgbjagbddfgdiaigdadhcfcj";
    // bool  res = s16.canConstruct(ransomNote, magazine);
    // cout << res << endl; // 1



    // Solution17 s17;
    // // vector<int> des = {-1,0,1,2,-1,-4};
    // vector<int> des = {-1,0,1,2,-1,-4};
    // vector<vector<int>> res = s17.threeSum2(des);
    // for(auto out : res){

    //     for(auto  in: out){

    //         cout << in << " ";
    //     }
    //     cout << endl;
    // }



    // Solution18 s18;
    // // vector<int> des = {1, 0, -1, 0, -2, 2};
    // vector<int> des = {1000000000,1000000000,1000000000,1000000000};
    // int target = 0;
    // vector<vector<int>> res = s18.fourSum(des, target);
    // for(auto out : res){

    //     for(auto  in: out){

    //         cout << in << " ";
    //     }
    //     cout << endl;
    // }



    // Solution19 s19;
    // vector<char> des = {'h','e','l','l','o'};
    // s19.reverseString(des);



    // Solution20 s20;
    // string des = "krmyfshbspcgtesxnnljhfursyissjnsocgdhgfxubewllxzqhpasguvlrxtkgatzfybprfmmfithphckksnvjkcvnsqgsgosfxc";
    // // string des = "abcd";
    // int target = 20;
    // string res;
    // res = s20.reverseStr(des, target);
    // cout << res << endl;



    // Solution21 s21;
    // string des = "We are happy.";
    // string res = s21.replaceSpace(des);
    // cout << res << endl;



    // Solution22 s22;
    // string des = "  hello world  ";
    // string res = s22.reverseWords(des);
    // cout << res << endl;



    // Solution23 s23;
    // string des = "lrloseumgh";
    // int n = 6;
    // string res = s23.reverseLeftWords(des, n);
    // cout << res << endl;



    // Solution24 s24;
    // string des1 = "aabaabaafa";
    // string des2 = "aabaaf";

    // int res = s24.strStr(des1, des2);
    // cout << res << endl;



    // Solution25 s25;
    // string des = "abababad";
    // bool res = s25.repeatedSubstringPattern1(des);
    // bool res2 = s25.repeatedSubstringPattern2(des);
    // cout << res << endl; 
    // cout << res2 << endl; 



    // Solution27 s27;
    // string des = "We are happy.";
    // string res = s27.replaceSpace(des);
    // cout << res << endl;



    // Solution29* obj = new Solution29();
    // obj->push(x);
    // int param_2 = obj->pop();
    // int param_3 = obj->peek();
    // bool param_4 = obj->empty();
    
    // cout << param_2 << endl;
    // cout << param_3 << endl;
    // cout << param_4 << endl;



    // Solution30* obj = new Solution30();
    // obj->push(3);
    // int param_2 = obj->pop();
    // int param_3 = obj->top();
    // bool param_4 = obj->empty();
    // cout << param_2 << endl;
    // cout << param_3 << endl;
    // cout << param_4 << endl;



    // Solution31 s31;
    // string des = "()[]{}";
    // bool res = s31.isValid(des);
    // cout << res << endl;
    // Solution32 s32;
    // string des = "abbaca";
    // string res = s32.removeDuplicates(des);
    // cout << res << endl;



    // Solution33 s33;
    // vector<string> des = {"4","13","5","/","+"};
    // int res = s33.evalRPN(des);
    // cout << res << endl;



    // Solution34 s34;
    // vector<int> des = {1,3,-1,-3,5,3,6,7};
    // // vector<int> des = {1,-1};
    // // vector<int> des = {1,3,1,2,0,5};
    // int k = 3;
    // auto res = s34.maxSlidingWindow(des, k);
    
    // for(auto i: res){
    //     cout << i << endl;
    // }



    // Solution35 s35;
    // vector<int> des = {1,1,1,2,2,3};
    // int k = 2;
    // auto res = s35.topKFrequent(des, k);
    // for(auto i: res){
    //     cout << i << endl;
    // }


    // Solution53 s53;
    // Solution39 s39;
    // auto res = s53.mergeTrees(s53.root1, s53.root2);



    // // 层序遍历二叉树
    // auto res2 = s39.levelOrder(res);
    // ShowTowVector(res2);


    // return 0;
// }


// demo03.cpp : 此文件包含 "main" 函数。程序执行将在此处开始并结束。
//

#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#include <optional>

/*
    代码随想录之-动态规划
*/


/*
    动态规划题7：不同的二叉搜索树


*/

class Solution99
{
public:
	Solution99()
	{
	}
	int numTrees(int n);
	~Solution99()
	{
	}

private:

};

int Solution99::numTrees(int n)
{
	std::vector <int> dp(n + 1);
	dp[0] = 1;
	for (int i = 1; i <= n;i++)
	{
		for (int j = 1; j <= i; j++)
		{
			dp[i] += dp[j - 1] * dp[i - j];
		}
	}

	return dp[n];
}
/*
	动态规划：0/1背包问题                
	
	对于面试的话，其实掌握01背包，和完全背包，就够用了，最多可以再来一个多重背包

	递推公式：
	当前承重量的背包最大容纳价值 = 
	max(腾出新物品空位后的背包承重量最大价值 + 新物品的价值，不加入新物品的最大价值)
	即 与 该元素    “上方 或者 左方+该加入后价值”  相比较大小
*/

// 经典背包问题
class Solution100
{
public:
	Solution100();
	~Solution100();

	int getMaxValue(std::vector<int>& products, std::vector<int>& values, int V);
private:

};

Solution100::Solution100()
{
}

Solution100::~Solution100()
{
}

int Solution100::getMaxValue(std::vector<int>& products, std::vector<int>& values, int V)
{
	int maxValue = 0;

	// dp[i][j] 二维数组表示    行为物体重量，列为背包容量   先遍历物体重量，后遍历背包重量
	// 初始化
	std::vector < std::vector<int>> dp(products.size(), std::vector<int>(V + 1, 0));
	for (int i = 1; i < V + 1 ; i++)
	{
		if (products[0] <= i) {
			dp[0][i] = values[0];
		}
	}

	for (int i = 0; i < dp.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			std::cout << dp[i][j] << " ";
		}
		std::cout  << std::endl;
	}
	std::cout << "---------------------" << std::endl;
	// 开始遍历
	for (int i = 1; i < products.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			if (products[i] > j) {
				dp[i][j] = dp[i - 1][j];
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i - 1][j - products[i]] + values[i]);
			}
		}
	}
	
	for (int i = 0; i < dp.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			std::cout << dp[i][j] << " ";
		}
		std::cout << std::endl;
	}
	return 0;
}

/*
	动态规划题8：分割等和子集

	给你一个 只包含正整数 的 非空 数组 nums 。
	请你判断是否可以将这个数组分割成两个子集，使得两个子集的元素和相等。
*/

class Solution101
{
public:
	Solution101();
	~Solution101();
	bool canPartition(std::vector<int>& nums);
private:

};

Solution101::Solution101()
{
}

Solution101::~Solution101()
{
}

/*
	思路：将其分为两个子集的话，两个子集的数值相等，平均分,个数不限
	注意：此题个数不限
	行 为从小到大排列的集合元素值，
	列 背包容量递增序列，
	背包容量为 nums.sum / 2 
*/
bool Solution101::canPartition(std::vector<int>& nums)
{
	std::sort(nums.begin(), nums.end());

	// 计算背包容量
	int V = 0;
	for (int i = 0; i < nums.size(); i++)
	{
		V += nums[i];
	}

	if (V % 2 == 1)
	{
		return false;
	}
	V /= 2;
	
	std::vector < std::vector<int>> dp(nums.size(), std::vector<int>(V + 1, 0));
	
	
	// 初始化  
	for (int i = 1; i < V + 1; i++)
	{
		if (nums[0] <= i)
		{
			dp[0][i] = nums[0];
		}
	}
	//背包要放入的商品（集合里的元素）重量为 元素的数值，价值也为元素的数值,当价值刚好等于容量，则完成分割
	// 所以最终的找到的值应该是最后一列等于容量的那个值，其中分割的元素就是那一列对应的行
	// 遍历
	for (int i = 1; i < nums.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			if (nums[i] > j )
			{
				dp[i][j] = dp[i - 1][j];
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i - 1][j - nums[i]] + nums[i]);
				if (dp[i][j] == V)
				{	
					for (int i = 0; i < dp.size(); i++)
					{
						for (int j = 0; j < dp[i].size(); j++) {
							std::cout << dp[i][j] << " ";
						}
						std::cout << std::endl;
					}
					return true;
				}
			}
		}
	}
	
	for (int i = 0; i < dp.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			std::cout << dp[i][j] << " ";
		}
		std::cout << std::endl;
	}

	return false;
}

/*
	动态规划题9：最后一块石头的重量2
*/

class Solution102
{
public:
	Solution102()
	{
	}

	~Solution102()
	{
	}
	int lastStoneWeightII(std::vector<int>& stones);

private:

};

/*
	本题其实就是 "尽量" 让石头分成重量相同的两堆，相撞之后剩下的石头最小，这样就化解成01背包问题了。
 
	想到这一点，那么此题就和上题一个思路了。
*/
int Solution102::lastStoneWeightII(std::vector<int>& stones) {

	//std::sort(stones.begin(), stones.end(), [](int a, int b) { return a < b;});
	//std::sort(stones.begin(), stones.end());   // 不用排序
	// 容量
	int V = 0;

	int sum = 0;
	for (int v : stones) {
		V += v;
	}
	sum = V;
	double S = ((double) V) / 2;
	
	V /= 2;

	// 构造dp数组
	std::vector<std::vector<int>> dp(stones.size(), std::vector<int>(V + 1, 0));

	// 初始化
	for (int i = 0; i < V + 1; i++)
	{
		if (stones[0] <= i) {
			dp[0][i] = stones[0];
		}
	}

	// 遍历
	for (int i = 1; i < stones.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			if (stones[i] > j)
			{
				dp[i][j] = dp[i - 1][j];
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i - 1][j - stones[i]] + stones[i]);
			}
		}
	}
	
	for (int i = 0; i < dp.size(); i++)
	{
		for (int j = 0; j < dp[i].size(); j++) {
			std::cout << dp[i][j] << " ";
		}
		std::cout << std::endl;
	}

	return sum - dp[stones.size() - 1][V] - dp[stones.size() - 1][V];  // 注意这里  
}


/*
	动态规划题10：目标和
*/
class Solution103
{
public:
	Solution103()
	{
	}

	~Solution103()
	{
	}

	int findTargetSumWays(std::vector<int>& nums, int target);
	int findTargetSumWays2(std::vector<int>& nums, int target);
	void backtracking(std::vector<int>& nums, int target, std::vector<std::vector<int>>& res, std::vector<int>& temp, int index, int sum);

private:

};

/*
	思路：
	
	两个方法：
	1、回溯
	2、动态规划
*/


void Solution103::backtracking(std::vector<int>& nums, int target, std::vector<std::vector<int>>& res, std::vector<int>& temp, int index, int sum) {


}

// 1、回溯       未实现
int Solution103::findTargetSumWays(std::vector<int>& nums, int target) {
	int result = 0;
	return result;
}

// 2、动态规划
int Solution103::findTargetSumWays2(std::vector<int>& nums, int target) {
	//1、计算出容量
	int sum = 0;
	for (int i = 0; i < nums.size(); i++)
	{
		sum += nums[i];
	}
	// 2、排除极端情况
	if ((sum + target) % 2 != 0 || sum < abs(target))
	{
		return 0;
	}
	// 3、初始化背包容量
	int bagpack = (sum + target) / 2;

	// 4、使用一维数组构建dp
	std::vector<int> dp(bagpack + 1, 0);
	
	//5、初始化dp
	dp[0] = 1;

	//6、遍历dp
	for (int i = 0; i < nums.size(); i++)
	{
		for (int j = bagpack; j >= nums[i]; j--) {
			dp[j] += dp[j - nums[i]];
		}
	}
	
	//7、得出结果
	return dp[bagpack];
}


/*
	动态规划题11：一和零
*/

class Solution104
{
public:
	Solution104()
	{
	}

	~Solution104()
	{
	}

	int findMaxForm(std::vector<std::string>& strs, int m, int n);
private:

};

int Solution104::findMaxForm(std::vector<std::string>& strs, int m, int n) {

	// 1、计算容量    m , n  两个背包

	// 2、构建dp数组
	std::vector<std::vector<int>> dp(m + 1, std::vector<int>(n + 1, 0));

	for (std::string str : strs) {

		int zeronum = 0;
		int onenum = 0;
		for (int i = 0; i < str.size(); i++)
		{
			if (str[i] == '0') {
				zeronum++;
			}
			else
			{
				onenum++;
			}
		}


		for (int i = m; i >= zeronum; i--)
		{
			for (int j = n; j >=  onenum; j--) {
				dp[i][j] = std::max(dp[i][j], dp[i - zeronum][j - onenum] + 1);
			}
		}

	}
	return dp[m][n];

}

/*
	动态规划题12：零钱兑换2

*/
class Solution105
{
public:
	Solution105()
	{
	}

	~Solution105()
	{
	}

	int change(int amount, std::vector<int>& coins);

	int change2(int amount, std::vector<int>& coins);

	void backtracking(std::vector<std::vector<int>>& res, std::vector<int>& temp, int sum, int index, int target
		, std::vector<int>& nums);
private:

};

/*
	思路：这道题就是组合问题，可以使用回溯做，也可以使用动态规划去做     不过这道题使用回溯算法会超时
*/
void Solution105::backtracking(std::vector<std::vector<int>>& res, std::vector<int>& temp, 
	int sum, int index, int target, std::vector<int> &nums) {
	if (sum == target)
	{
		res.push_back(temp);

		for (int i = 0; i < temp.size(); i++)
		{
			std::cout << temp[i] << " ";
		}
		std::cout << std::endl;

		return;
	}

	for (int i = index; i < nums.size(); i++)
	{	
		// 剪枝   若要加入剪枝，则需要先排序
		if (sum + nums[i] > target)
		{
			break;
		}
		sum += nums[i];
		temp.push_back(nums[i]);
		backtracking(res, temp, sum, i, target, nums);
		sum -= nums[i];
		temp.pop_back();
	}
}

int Solution105::change2(int amount, std::vector<int>& coins) {
	std::vector<std::vector<int>> res;
	std::vector<int> temp;
	std::sort(coins.begin(), coins.end());
	backtracking(res, temp, 0, 0, amount, coins);

	return res.size();
}

//1、背包容量：amount     遍历数组 nums
// 这道题不同与01背包问题，物品可以无限制选取， 即完全背包问题
int Solution105::change(int amount, std::vector<int>& coins) {
	
	std::vector<int>dp (amount + 1, 0);
	dp[0] = 1;

	for (int i = 0; i < coins.size(); i++)
	{
		for (int j = coins[i]; j <= amount; j++) {
			dp[j] += dp[j - coins[i]];
		}
	}

	return dp[amount];
}

/*
	动态规划题13：组合总和4       排列问题
*/
class Solution106
{
public:
	Solution106()
	{
	}

	~Solution106()
	{
	}

	int combinationSum4(std::vector<int>& nums, int target);
private:

};

int Solution106::combinationSum4(std::vector<int>& nums, int target) {
	std::vector<int> dp(target + 1, 0);
	dp[0] = 1;
	for (int j = 0; j <= target; j++)
	{
		for (int i = 0; i < nums.size(); i++) {
			if (j - nums[i] >= 0 && dp[i] < INT_MAX - dp[j - nums[i]]) dp[j] += dp[j - nums[i]];
		}
	}

	return dp[target];
}


/*
	动态规划题14：爬楼梯进阶版
*/
class Solution107
{
public:
	Solution107()
	{
	}

	~Solution107()
	{
	}

	int climbStairs(int n);
private:

};
// 进阶版可以看成排列问题，和上一题一样   nums.size = 2;    1  2
int Solution107::climbStairs(int n) {
	std::vector<int> dp(n + 1, 0);
	dp[0] = 1;
	std::vector<int> nums = { 1, 2 };

	for (int i = 0; i <= n; i++)
	{
		for (int j = 0; j < nums.size(); j++) {
			if (i - nums[j] >= 0 && dp[i] < INT_MAX - dp[i - nums[j]])
			{
				dp[i] += dp[i - nums[j]];
			}
		}
	}
	
	return dp[n];
}

#include <algorithm>
/*
	动态规划题15：零钱兑换
*/

class Solution108
{
public:
	Solution108()
	{
	}

	~Solution108()
	{
	}

	int coinChange(std::vector<int>& coins, int amount);
private:

};


// 和组合问题的区别在于 选取的硬币“个数最少，达到目标值”
//dp[j]：凑足总额为j所需钱币的最少个数为dp[j]
//本题钱币数量可以无限使用，那么是完全背包。所以遍历的内循环是正序
int Solution108::coinChange(std::vector<int>& coins, int amount) {

	std::vector<int> dp(amount + 1, INT_MAX);
	dp[0] = 0;
	for (int i = 1; i <= amount; i++)
	{
		for (int j = 0; j < coins.size(); j++) {
			if (i - coins[j] >= 0 && dp[i - coins[j]] != INT_MAX)
			{
				dp[i] = std::min(dp[i - coins[j]] + 1, dp[i]);
				std::cout << dp[i] << std::endl;
			}
		} 
	}
	if (dp[amount] == INT_MAX) return -1;
	return dp[amount];
}

/*
	动态规划题16：完全平方数
*/
class Solution109
{
public:
	Solution109()
	{
	}

	~Solution109()
	{
	}
	
	int numSquares(int n);
private:

};

/*
	给你一个整数 n ，返回 和为 n 的完全平方数的最少数量 。
	完全平方数 是一个整数，其值等于另一个整数的平方；换句话说，其值等于一个整数自乘的积。
	例如，1、4、9 和 16 都是完全平方数，而 3 和 11 不是。

	输入：n = 12
	输出：3
	解释：12 = 4 + 4 + 4
*/
// 完全背包问题 背包容量为12
int Solution109::numSquares(int n) {

	std::vector<int> dp(n + 1, INT_MAX);
	dp[0] = 0; // 无意义，因为题目要求 n >= 1
	for (int i = 1; i <=n; i++) // 遍历背包
	{
		for (int j = 1; j * j <= i; j++) {  // 遍历物品
			dp[i] = std::min(dp[i - j * j] + 1, dp[i]);
		}
	}

	return dp[n];
}


/*
	动态规划题17：单词拆分
*/

class Solution110
{
public:
	Solution110()
	{
	}

	~Solution110()
	{
	}

	bool wordBreak(std::string s, std::vector<std::string>& wordDict);
private:

};

/*
	将字典里的子串当成物品，并且可以重复利用
	将目标字符串当成背包
*/
#include<unordered_set>
bool Solution110::wordBreak(std::string s, std::vector<std::string>& wordDict) {
	std::vector<bool> dp(s.size() + 1, false);
	std::unordered_set<std::string> wordSet(wordDict.begin(), wordDict.end());
	dp[0] = true;

	for (int i = 1; i <= s.size(); i++)
	{
		for (int j = 0; j < i; j++) {
			std::string word = s.substr(j, i - j);
			if (wordSet.find(word) != wordSet.end() && dp[j])
			{
				dp[i] = true;
			}
		}
	}

	return dp[s.size()];
}

/*
	动态规划题18：打家劫舍
*/
class Solution111
{
public:
	Solution111()
	{
	}

	~Solution111()
	{
	}

	int rob(std::vector<int>& nums);
private:

};

int Solution111::rob(std::vector<int>& nums) {
	// 确定dp数组下标即dp[i]的含义  
	// i 代表打劫第几家，dp[i] 代表打劫 到第i家时获取的资金
	if (nums.size() == 0)
	{
		return 0;
	}
	if (nums.size() == 1)
	{
		return nums[0];
	}

	std::vector<int> dp(nums.size());
	dp[0] = nums[0];
	dp[1] = std::max(nums[0], nums[1]);

	for (int i = 2; i < nums.size(); i++)
	{
		dp[i] = std::max(dp[i - 2] + nums[i], dp[i - 1]);
	}

	return dp[nums.size() - 1];
}

/*
	动态规划题19：打家劫舍2
*/

class Solution112
{
public:
	Solution112()
	{
	}

	~Solution112()
	{
	}

	int rob(std::vector<int>& nums);

	int robRange(const std::vector<int>& nums, int start, int end);
private:

};


// 这道题与上一道题的区别是 该题是环状   首尾两家相连
// 多了两个逻辑
int Solution112::robRange(const std::vector<int>& nums, int start, int end) {
	if (end == start) return nums[start];
	std::vector<int> dp(nums.size());
	dp[start] = nums[start];
	dp[start + 1] = std::max(nums[start], nums[start + 1]);

	for (int i = start + 2; i <= end; i++)
	{
		dp[i] = std::max(dp[i - 2] + nums[i], dp[i - 1]);
	}

	return dp[end];
}

int Solution112::rob(std::vector<int>& nums) {

	if (nums.size() == 0)
	{
		return 0;
	}
	if (nums.size() == 1)
	{
		return nums[0];
	}

	int resultFornt = robRange(nums, 0, nums.size() - 2);
	int resultRear = robRange(nums, 1, nums.size() - 1);

	return std::max(resultFornt, resultRear);
}

/*
	动态规划题20：打家劫舍3
*/

struct TreeNode2 {
	int val;
	TreeNode2* left;
	TreeNode2* right;
	TreeNode2() : val(0), left(nullptr), right(nullptr) {}
	TreeNode2(int x) : val(x), left(nullptr), right(nullptr) {}
	TreeNode2(int x, TreeNode2* left, TreeNode2* right) : val(x), left(left), right(right) {}
};

class Solution113
{
public:
	Solution113()
	{
	}

	~Solution113()
	{
	}

	int rob(TreeNode2* root);

	std::vector<int> robTree(TreeNode2 *cur);
private:

};

// 本题考察 树形dp     递归三部曲 + 动规五部曲
// 1、确定递归参数及返回值类型
std::vector<int> Solution113::robTree(TreeNode2* cur) {
	// 2、递归终止条件
	if (cur == NULL) return std::vector<int>{0, 0};    // dp数组就体现在返回的vector中
	// 3、开始递归
	std::vector<int> left = robTree(cur->left);
	std::vector<int> right = robTree(cur->right);

	// 后序遍历处理节点
	// 情况一：不偷                     （不偷 0  偷 1）
	int val1 = std::max(left[0], left[1]) + std::max(right[0], right[1]);     // 这里为什么要后序遍历   因为偷与不偷 依赖子节点的值
																						// 需要先拿到子节点的值，才能比较偷与不偷
	// 情况二： 偷
	int val2 = cur->val + left[0] + right[0];

	return { val1, val2 };
}

int Solution113::rob(TreeNode2*root) {

	std::vector<int> result = robTree(root);
	return std::max(result[0], result[1]);
}

/*
	动态规划题21：买卖股票的最佳时机
*/
class Solution114
{
public:
	Solution114()
	{
	}

	~Solution114()
	{
	}

	int maxProfit(std::vector<int>& prices);
	int maxProfit2(std::vector<int>& prices);
private:

};
// 本提可以使用贪心，也可以使用动态规划
//1、贪心   时间复杂度 n
int Solution114::maxProfit2(std::vector<int>& prices) {
	int result = 0;
	int low = INT_MAX;

	for (int i = 0; i < prices.size(); i++)
	{
		low = std::max(low, prices[i]);  // 一直指向最小值
		result = std::max(result, prices[i] - low); // 一直指向最大值
	}

	return result;
}
//2、动态规划   动规五部曲
int Solution114::maxProfit(std::vector<int>& prices) {

	// 1、确定dp及其下标含义
	// dp[i][0] 表示第 i 天持有股票所得最多现金     dp[i][1] 表示第 i 不持有股票所得最多现金
	std::vector<std::vector<int>> dp(prices.size(), std::vector<int>(2));
	// 2、确定递推公式    dp[i][0] 分为第 i 天之前就买入 还是当天买入    dp[i][1]  分为第 i 天之前就卖出 还是当天卖出
	// dp[i][0] = fmax(dp[i - 1][0], -prices[i])     dp[i][1] = fmax(dp[i - 1][1], dp[i - 1][0] + prices[i])
	// 3、初始化dp    根据递推公式初始化 dp[0][0]   dp[0][1]
	dp[0][0] = -prices[0];
	dp[0][1] = 0;
	// 4、确定遍历顺序   i 状态依赖于 i - 1  ， 从前往后遍历
	for (int i = 1; i < prices.size(); i++)
	{
		dp[i][0] = std::max(dp[i - 1][0], -prices[i]);
		dp[i][1] = std::max(dp[i - 1][1], dp[i - 1][0] + prices[i]);
	}
	// 5、举例推导出返回值
	return dp[prices.size() - 1][1];
}

/*
	动态规划题22：买卖股票的最佳时机2
*/
class Solution115
{
public:
	Solution115()
	{
	}

	~Solution115()
	{
	}

	int maxProfit(std::vector<int>& prices);

private:

};
// 这道题可以用贪心求解，也可以使用动态规划求解                  注意！！！此题可以在某天既不买入又不卖出
int Solution115::maxProfit(std::vector<int>& prices) {
	// 1、确定dp及其下标含义
	// dp[i][0] 表示第 i 天持有股票最多现金    dp[i][1] 表示第 i 天不持有股票最多现金
	std::vector<std::vector<int>> dp(prices.size(), std::vector<int>(2));
	// 2、确定递推公式
	// dp[i][0]  第 i - 1 天不持有股票 - prices[i]     dp[i][1]  第 i - 1 天持有 + prices[i]
	/*dp[i][0] = fmax(dp[i - 1][0], dp[i - 1][1] - prices[i]);
	dp[i][1] = fmax(dp[i - 1][1], dp[i - 1][0] + prices[i]);*/
	// 3、初始化dp                           
	dp[0][0] = -prices[0];
	dp[0][1] = 0;
	// 4、确定遍历顺序   顺序遍历
	for (int i = 1; i < prices.size(); i++)
	{
		dp[i][0] = std::max(dp[i - 1][0], dp[i - 1][1] - prices[i]);
		dp[i][1] = std::max(dp[i - 1][1], dp[i - 1][0] + prices[i]);
	}

	// 5、举例确定返回值

	return dp[prices.size() - 1][1];
}


/*
	动态规划题23：买卖股票的最佳时机含冷冻期
*/

class Solution116
{
public:
	Solution116()
	{
	}

	~Solution116()
	{
	}

	int maxProfit(std::vector<int>& prices);
private:

};

// 利用可变参数，实现求最大值
template<typename T>
T maxele(T a)
{
	return a;
}

template<typename T, typename... Args>
T maxele(T a, Args... arg)
{
	return std::max(a, maxele(arg...));
}


int Solution116::maxProfit(std::vector<int>& prices) {

	int n = prices.size();
	if (n == 0) return 0;
	std::vector<std::vector<int>> dp(n, std::vector<int>(4, 0));
	dp[0][0] -= prices[0]; // 持股票
	for (int i = 1; i < n; i++) {
		dp[i][0] = maxele(dp[i - 1][0], dp[i - 1][3] - prices[i], dp[i - 1][1] - prices[i]);
		dp[i][1] = maxele(dp[i - 1][1], dp[i - 1][3]);
		dp[i][2] = dp[i - 1][0] + prices[i];
		dp[i][3] = dp[i - 1][2];
	}
	return maxele(dp[n - 1][3], dp[n - 1][1], dp[n - 1][2]);
}

/*
	动态规划题24：买卖股票的最佳时机含手续费
*/
class Solution117
{
public:
	Solution117()
	{
	}

	~Solution117()
	{
	}

	int maxProfit(std::vector<int>& prices, int fee);
private:

};
//本题和动态规划：买卖股票的最佳时机2的区别就是这里需要多一个减去手续费的操作。
int Solution117::maxProfit(std::vector<int>& prices, int fee) {
	// 1、确定dp及其下标含义
	// dp[i][0] 表示第 i 天持有股票最多现金    dp[i][1] 表示第 i 天不持有股票最多现金
	std::vector<std::vector<int>> dp(prices.size(), std::vector<int>(2));
	// 2、确定递推公式
	// dp[i][0]  第 i - 1 天不持有股票 - prices[i]     dp[i][1]  第 i - 1 天持有 + prices[i]
	/*dp[i][0] = fmax(dp[i - 1][0], dp[i - 1][1] - prices[i]);
	dp[i][1] = fmax(dp[i - 1][1], dp[i - 1][0] + prices[i]);*/
	// 3、初始化dp                           
	dp[0][0] = -prices[0];
	dp[0][1] = 0;
	// 4、确定遍历顺序   顺序遍历
	for (int i = 1; i < prices.size(); i++)
	{
		dp[i][0] = std::max(dp[i - 1][0], dp[i - 1][1] - prices[i]);
		dp[i][1] = std::max(dp[i - 1][1], dp[i - 1][0] + prices[i] - fee);
	}
	// 5、举例确定返回值
	return dp[prices.size() - 1][1];
}

/*
	动态规划题25：最长递增子序列  （最长不连续递增序列）
*/
class Solution118
{
public:
	Solution118()
	{
	}

	~Solution118()
	{
	}

	int lengthOfLIS(std::vector<int>& nums);
private:

};

int Solution118::lengthOfLIS(std::vector<int>& nums) {
	std::vector<int> dp(nums.size(), 1);
	int result = 0;

	for (int i = 1; i < nums.size(); i++)
	{
		for (int j = 0; j < i; j++) {
			if (nums[i] > nums[j])
			{
				dp[i] = std::max(dp[i], dp[j] + 1);
			}
		}
		if (result < dp[i])
		{
			result = dp[i];
		}
	}
	return result;
}

/*
	动态规划题26：最长递增子序列  （最长连续递增序列）
*/
class Solution119
{
public:
	Solution119()
	{
	}

	~Solution119()
	{
	}

	int findLengthOfLCIS(std::vector<int>& nums);
private:

};
// 与上一题不同的是，该题是最长“连续”递增子序列
int Solution119::findLengthOfLCIS(std::vector<int>& nums) {
	if (nums.size() == 1) return 1;
	std::vector<int> dp(nums.size(), 1);
	int result = 0;

	for (int i = 1; i < nums.size(); i++)
	{
		for (int j = 0; j < i; j++) {
			if ((nums[i] > nums[j]) && (j + 1 == i))
			{
				dp[i] = std::max(dp[i], dp[j] + 1);
			}

		}
		if (result < dp[i])
		{
			result = dp[i];
		}
	}
	return result;
}

/*
	动态规划题27：最长重复子数组
*/
class Solution120
{
public:
	Solution120()
	{
	}

	~Solution120()
	{
	}

	int findLength(std::vector<int>& nums1, std::vector<int>& nums2);

private:

};
// 注意：这里的最长重复子数组，必须是连续的情况
int Solution120::findLength(std::vector<int>& nums1, std::vector<int>& nums2) {

	std::vector<std::vector<int>> dp(nums1.size() + 1, std::vector<int>(nums2.size() + 1, 0));
	int result = 0;

	for (int i = 1; i <= nums1.size(); i++)
	{
		for (int j = 1; j <= nums2.size(); j++) {
			if (nums1[i - 1] == nums2[j - 1])
			{
				dp[i][j] = dp[i - 1][j - 1] + 1;
			}
			if (result < dp[i][j])
			{
				result = dp[i][j];
			}
		}
	}
	return result;
}

/*
	动态规划题28：最长公共子序列
*/
class Solution121
{
public:
	Solution121()
	{
	}

	~Solution121()
	{
	}

	int longestCommonSubsequence(std::string text1, std::string text2);
private:

};
// 注意：这里的最长公共子序列，可以不连续的情况，这和上题的区别就在这里
int Solution121::longestCommonSubsequence(std::string text1, std::string text2) {
	std::vector<std::vector<int>> dp(text1.size() + 1, std::vector<int>(text2.size() + 1, 0));

	int result = 0;
	for (int i = 1; i <= text1.size(); i++)
	{
		for (int j = 1; j <= text2.size(); j++) {
			// 分为两种情况：当前元素相等，当前元素不等
			// 当前元素相等时：dp[i][j] = dp[i - 1][j - 1] + 1    当前元素不等时，dp[i][j] = dp[i - 1][j - 1]
			if (text1[i - 1] == text2[j - 1])
			{
				dp[i][j] = dp[i - 1][j - 1] + 1;
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i][j - 1]);
			}
			if (result < dp[i][j])
			{
				result = dp[i][j];
			}
		}
	}
	return result;
}

/*
	动态规划题29：不相交的线
*/
class Solution122
{
public:
	Solution122()
	{
	}

	~Solution122()
	{
	}

	int maxUncrossedLines(std::vector<int>& nums1, std::vector<int>& nums2);
private:

};

int Solution122::maxUncrossedLines(std::vector<int>& nums1, std::vector<int>& nums2) {
	std::vector<std::vector<int>> dp(nums1.size() + 1, std::vector<int>(nums2.size() + 1, 0));

	int result = 0;
	for (int i = 1; i <= nums1.size(); i++)
	{
		for (int j = 1; j <= nums2.size(); j++) {
			// 分为两种情况：当前元素相等，当前元素不等
			// 当前元素相等时：dp[i][j] = dp[i - 1][j - 1] + 1    当前元素不等时，dp[i][j] = dp[i - 1][j - 1]
			if (nums1[i - 1] == nums2[j - 1])
			{
				dp[i][j] = dp[i - 1][j - 1] + 1;
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i][j - 1]);
			}
			if (result < dp[i][j])
			{
				result = dp[i][j];
			}
		}
	}
	return result;
}

/*
	动态规划题30：最大子数组和
*/
class Solution123
{
public:
	Solution123()
	{
	}

	~Solution123()
	{
	}

	int maxSubArray(std::vector<int>& nums);
private:

};
// 注意：连续子数组  可以使用贪心  也可以使用动归
int Solution123::maxSubArray(std::vector<int>& nums) {
	if (nums.size() == 0)
	{
		return 0;
	}
	std::vector<int> dp(nums.size());
	dp[0] = nums[0];
	int result = nums[0];
	for (int i = 1; i < nums.size(); i++)
	{
		dp[i] = std::max(dp[i - 1] + nums[i], nums[i]);
		if (result < dp[i])
		{
			result = dp[i];
		}
	}
	return result;
}

/*
	动态规划题31：判断子序列
*/
class Solution124
{
public:
	Solution124()
	{
	}

	~Solution124()
	{
	}

	bool isSubsequence(std::string s, std::string t);
private:

};

bool Solution124::isSubsequence(std::string s, std::string t) {
	std::vector<std::vector<int>> dp(s.size() + 1, std::vector<int>(t.size() + 1, 0));

	int result = 0;
	for (int i = 1; i <= s.size(); i++)
	{
		for (int j = 1; j <= t.size(); j++) {
			// 分为两种情况：当前元素相等，当前元素不等
			// 当前元素相等时：dp[i][j] = dp[i - 1][j - 1] + 1    当前元素不等时，dp[i][j] = dp[i - 1][j - 1]
			if (s[i - 1] == t[j - 1])
			{
				dp[i][j] = dp[i - 1][j - 1] + 1;
			}
			else {
				dp[i][j] = std::max(dp[i - 1][j], dp[i][j - 1]);
			}
			if (result < dp[i][j])
			{
				result = dp[i][j];
			}
		}
	}
	return result == s.size()?true:false;
}
/*
	动态规划题32：回文子串
*/

class Solution125
{
public:
	Solution125()
	{
	}

	~Solution125()
	{
	}

	int countSubstrings(std::string s);
private:

};

// 注意：具有不同开始位置或结束位置的子串，即使是由相同的字符组成，也会被视作不同的子串。
int Solution125::countSubstrings(std::string s) {
	std::vector<std::vector<bool>> dp(s.size(), std::vector<bool>(s.size(), false));
	int result = 0;
	for (int i = s.size() - 1; i >= 0; i--) {  // 注意遍历顺序
		for (int j = i; j < s.size(); j++) {
			if (s[i] == s[j]) {
				if (j - i <= 1) { // 情况一 和 情况二
					result++;
					dp[i][j] = true;
				}
				else if (dp[i + 1][j - 1]) { // 情况三
					result++;
					dp[i][j] = true;
				}
			}
		}
	}
	return result;
}

/*
	动态规划题33：最长回文子序列
*/
class Solution126
{
public:
	Solution126()
	{
	}

	~Solution126()
	{
	}

	int longestPalindromeSubseq(std::string s);
private:

};

// 注意：回文子串是要连续的，回文子序列可不是连续的！
int Solution126::longestPalindromeSubseq(std::string s) {
	std::vector<std::vector<int>> dp(s.size(), std::vector<int>(s.size(), 0));
	for (int i = 0; i < s.size(); i++) dp[i][i] = 1;
	for (int i = s.size() - 1; i >= 0; i--) {
		for (int j = i + 1; j < s.size(); j++) {
			if (s[i] == s[j]) {
				dp[i][j] = dp[i + 1][j - 1] + 2;
			}
			else {
				dp[i][j] = std::max(dp[i + 1][j], dp[i][j - 1]);
			}
		}
	}
	return dp[0][s.size() - 1];
}
int main()
{	
	Solution126 s126;
	std::string s = "bbbab";
	int res = s126.longestPalindromeSubseq(s);
	std::cout << res << std::endl;

	/*Solution125 s125;
	std::string s = "abc";
	int res = s125.countSubstrings(s);
	std::cout << res << std::endl;*/

	/*Solution124 s124;
	std::string s = "abc";
	std::string t = "ahbgdc";
	bool res = s124.isSubsequence(s, t);
	std::cout << res << std::endl;*/

	/*Solution123 s123;
	std::vector<int> nums = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
	int res = s123.maxSubArray(nums);
	std::cout << res << std::endl;*/

	/*Solution122 s122;
	std::vector<int> nums1 = {2, 5, 1, 2, 5};
	std::vector<int> nums2 = {10, 5, 2, 1, 5, 2};
	int res = s122.maxUncrossedLines(nums1, nums2);
	std::cout << res << std::endl;*/

	/*Solution121 s121;
	std::string text1 = "abcde";
	std::string text2 = "ace";
	int res = s121.longestCommonSubsequence(text1, text2);
	std::cout << res << std::endl;*/


	/*Solution120 s120;
	std::vector<int> nums = {1, 2, 3, 2, 1};
	std::vector<int> nums2 = {3, 2, 1, 4, 7};
	int res = s120.findLength(nums, nums2);
	std::cout << res << std::endl;*/


	//Solution119 s119;
	////std::vector<int> nums = {1, 3, 5, 4, 7};
	//std::vector<int> nums = {2, 2, 2, 2, 2};
	//int res = s119.findLengthOfLCIS(nums);
	//std::cout << res << std::endl;

	/*Solution118 s118;
	std::vector<int> nums = {10,9,2,5,3,7,101,18};
	int res = s118.lengthOfLIS(nums);
	std::cout << res << std::endl;*/

	/*Solution117 s117;
	std::vector<int> prices = {1, 3, 2, 8, 4, 9};
	int fee = 2;
	int res = s117.maxProfit(prices, fee);
	std::cout << res << std::endl;*/

	//Solution116 s116;
	//std::vector<int> prices{ 1, 2, 3, 0, 2};
	////std::vector<int> prices{1};
	//int res = s116.maxProfit(prices);
	//std::cout << res << std::endl;


	/*Solution115 s115;
	std::vector<int> prices{ 7, 1, 5, 3, 1, 4};
	int res = s115.maxProfit(prices);
	std::cout << res << std::endl;*/


	/*Solution114 s114;
	std::vector<int> prices = {7, 1, 5, 3, 6, 4};
	int res = s114.maxProfit(prices);
	std::cout << res << std::endl;*/

	/*Solution113 s113;
	TreeNode* root = new TreeNode(3);
	root->left = new TreeNode(2);
	root->left->right = new TreeNode(3);
	root->right = new TreeNode(3);
	root->right->right = new TreeNode(1);
	int res = s113.rob(root);
	std::cout << res << std::endl;*/


	/*Solution112 s112;
	std::vector<int> nums = {1, 2, 3, 1};
	int res = s112.rob(nums);
	std::cout << res << std::endl;*/

	/*Solution111 s111;
	std::vector<int> nums = {1, 2, 3, 1};
	int res = s111.rob(nums);
	std::cout << res << std::endl;*/

	/*Solution110 s110;
	std::string s = "leetcode";
	std::vector<std::string> wordDict;
	wordDict.push_back("leet");
	wordDict.push_back("code");
	bool res = s110.wordBreak(s, wordDict);
	std::cout << res << std::endl;*/


	/*Solution109 s109;
	int res = s109.numSquares(12);
	std::cout << res << std::endl;*/

	/*Solution108 s108;

	std::vector<int> des = {1, 2, 5};
	int amount = 11;

	int res = s108.coinChange(des, amount);

	std::cout << res << std::endl;*/

	/*Solution107 s107;

	int res = s107.climbStairs(2);

	std::cout << res << std::endl;*/

	/*Solution106 s106;

	std::vector<int> des = {1, 2, 3};

	int target = 4;

	int res= s106.combinationSum4(des, target);
	std::cout << res << std::endl;*/

	/*Solution105 s105;
	
	std::vector<int> des = {1, 2, 5};
	int target = 5;
	int res = s105.change(target, des);
	std::cout << res << std::endl;*/

	/*Solution104 s104;
	std::vector<std::string> des = { "10", "0001", "111001", "1", "0" };
	int res = s104.findMaxForm(des, 5, 3);
	std::cout << res << std::endl;*/

	/*Solution103 s103;

	std::vector<int> nums = {1, 1, 1, 1, 1};
	int target = 3;*/
	/*int res = s103.findTargetSumWays(nums, target);

	std::cout << "-----------------------" << std::endl;
	std::cout << res << std::endl;*/

	/*int res2 = s103.findTargetSumWays2(nums, target);
	std::cout << res2 << std::endl;*/

	/*Solution99 s99;
	int res = s99.numTrees(3);
	std::cout << res << std::endl;*/

	/*Solution100 s100;
	std::vector<int> p{1, 3, 4};
	std::vector<int> v{15, 20, 30};
	int res = s100.getMaxValue(p, v, 4);*/
	//std::cout << res << std::endl;

	/*Solution101 s101;
	std::vector<int> nums = {1, 2, 3, 5};
	bool res = s101.canPartition(nums);
	std::cout << res << std::endl;*/

	//Solution102 s102;
	////std::vector<int> stones = { 2, 7, 4, 1, 8, 1 };
	//std::vector<int> stones = { 31, 26, 33, 21, 40 };
	//int res = s102.lastStoneWeightII(stones);
	//std::cout << res << std::endl;
}
