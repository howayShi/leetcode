## Tips1： 
```
C++中的：
for(char c:s) //遍历s字符串
相当于C语言的：
for( int i = 0; i < s.length(); i++)
{ 
	[i]....	
}
```
## Tips2：

`top（）是取出栈顶元素，不会删掉栈里边的元素。
 pop（）是删除栈顶元素，完成出栈操作。`


## 答案
```
class Solution {
public:
    bool isValid(string s) {
        int n=s.size();
        if(n==0){return true;}//空列表
        stack<int> st; //建立栈
        for(char c:s) //c++遍历字符串的方式
        {
            if(c == '(' || c == '[' || c == '{') //左括号，去判断右边有没有符合的右括号
            { 
                st.push(c); //PUSH入栈，POP出栈
            }
            else
            {
                if(st.size() == 0)
                {
                    return false;
                }
                else
                {
                    int temp = st.top();//获取栈顶指针
                    st.pop();//出栈
                    if(c == ')')
                    {
                        if(temp != '(')
                            return false;
                    }
                    else if(c == ']')
                    {
                        if(temp != '[')
                            return false;
                    }
                    else if(c == '}')
                    {
                        if(temp != '{')
                            return false;
                    }
                }
            }
        }
        if(st.size() == 0)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
};
```