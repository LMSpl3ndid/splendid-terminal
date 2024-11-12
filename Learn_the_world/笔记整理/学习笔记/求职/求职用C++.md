求职用c++主要用于笔试部分，相较于本科课程里教授的c++，笔试时我们可以使用STL库中的vector，map等简便数据结构，此处记录一下这些数据结构的调用方法以及基本操作函数

动态数组：vector
队列：queue、dequeue
栈：stack
双向链表：list
集合：set / multiset
散列表：map / multimap

库一览
```
#include<iostream>
#include<string>
#include<algorithm>

#include<vector>


```
迭代器：auto类似数组

当正常数组处理即可！
### 一、动态数组
[c++ vector用法 入门必看 超详细_vector c++ 用法-CSDN博客](https://blog.csdn.net/weixin_52115456/article/details/126024253)
[vector的几种初始化及赋值方式_vector赋值-CSDN博客](https://blog.csdn.net/e891377/article/details/108929556)
#### 1.调用库
```
#include<vector>
```
#### 2.声明or初始化

|                          |            |
| ------------------------ | ---------- |
| vector\<int\>  aa        |            |
| vector\<int\>  aa(n,val) | n个，初始值为val |
|                          |            |
|                          |            |

#### 3.基本操作
\[begin, end)

|                                      |                     |
| ------------------------------------ | ------------------- |
| v.empty()                            |                     |
| v.size()                             |                     |
| v.push_back(val)                     | 尾端添加val             |
| v.pop_back()                         | 删除，无返回              |
| v1==v2                               | 个数与同一位置取值均相等        |
|                                      |                     |
| v.insert(p,n,val)                    | 在p之前插入n个val         |
| v.erase(p)                           | 删除p,返回p+1           |
| v.erase(b,e)                         | 删除b,e之间，返回最后一个后面一个的 |
|                                      |                     |
| sort(v.begin(),v.end())              |                     |
| reverse(v.begin(),v.end())           |                     |
| auto it=max_element(v.begin,v.end()) | 返回最大值迭代器            |
|                                      |                     |
| v.resize(n,t)                        | 分配空间重设为n，初始值为t      |

![[Pasted image 20241101150121.png]]

### 二、队列
### 三、栈
[c++ stack用法 入门必看 超详细-CSDN博客](https://blog.csdn.net/weixin_52115456/article/details/127595817)
![[Pasted image 20241101150049.png]]
### 四、双向链表
### 五、集合
声明：
```c++
unordered_set<int> nums_set(nums1.begin(), nums1.end());
```
查找.find() 
插入.insert()
### 六、散列表
1.map
1.1 初始化
	mapStudent.insert(pair<int, string>(1, "student_one"));
	 mapStudent.insert(map<int, string>::value_type (1, "student_one"));
	 mapStudent[1] = "student_one";


### 七、树
```c++
#include <iostream>

#include<stack>

using namespace std;

struct Treenode{

    Treenode *left=NULL;

    Treenode *right=NULL;

    int data=0;

};

int main() {

    deque<Treenode**> q;//注意初始化，栈内为左右指针的指针

    Treenode *T;

    q.push_back(&T);

    int tmp;

    while(cin>>tmp)

    {

        Treenode **temp=q.front();

        q.pop_front();

        if(tmp!=-1)

        {

            *temp=new Treenode;

            (*temp)->data=tmp;

        q.push_back(&(*temp)->left);

        q.push_back(&(*temp)->right);

        }

    }

  

    deque<Treenode*> p;

    p.push_back(T);

    while(!p.empty())

    {  

        Treenode *temp=p.front();

        p.pop_front();

        cout<<temp->data<<" ";

        if(temp->left!=NULL)

            p.push_back(temp->left);

        if(temp->right!=NULL)

            p.push_back(temp->right);

    }

}
```



# 算法：
1.回溯算法：

![[Pasted image 20240918224958.png]]
    1.1 寻找组合数：