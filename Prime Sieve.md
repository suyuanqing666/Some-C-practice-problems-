# Problem: Prime Sieve

## Problem Description:

Input n integers (where n≤100) each not exceeding 100000. Store all of them in an array, remove the numbers that are not prime, and output the remaining prime numbers in sequence.

## Code:

```cpp
#include<iostream>
using namespace std;
int main()
{
    int i, n;
    cin >> n;
    for (i = 0; i < n; i++)
    {
        int num;
        cin >> num;
        int j;
        bool isprime = true;
        
        // 处理边界条件
        if (num <= 1) {
            isprime = false;
        } else if (num == 2) {
            isprime = true;
        } else {
            for (j = 2; j * j <= num; j++)  // 优化：检查到 sqrt(num) 即可
            {
                if (num % j == 0)
                {
                    isprime = false;
                    break;  // 发现因子后立即退出循环
                }
            }
        }

        // 输出逻辑移到外部循环
        if (isprime)  // 修复：改为 if (isprime == true) 或直接 if (isprime)
        {
            cout << num << " ";  // 用空格分隔输出
        }
    }
    return 0;
}
```


