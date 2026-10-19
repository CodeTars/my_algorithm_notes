# STL（Standard Template Libary)

## lower_bound 与 upper_bound

[大概的源码](https://blog.csdn.net/qq1337715208/article/details/81072709?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_default&utm_relevant_index=1)

```c++
#include <algorithm>
#include <functional>

//在单调递增的 [first, last) 区域内查找首个大于等于val的元素
ForwardIterator lower_bound(ForwardIterator first, ForwardIterator last, const T& val, less<int>());
//在单调递增的 [first, last) 区域内查找首个大于val的元素
ForwardIterator upper_bound(ForwardIterator first, ForwardIterator last, const T& val, less<int>());

//在单调递减的 [first, last) 区域内查找首个小于等于val的元素
ForwardIterator lower_bound(ForwardIterator first, ForwardIterator last, const T& val, greater<int>());
//在单调递减的 [first, last) 区域内查找首个小于val的元素
ForwardIterator upper_bound(ForwardIterator first, ForwardIterator last, const T& val, greater<int>());
```

通过lower_bound维护一个定长的单调递减数组

**!!!**复杂度很大，年少轻狂不懂事写的。。。。

```c++
#include <vector>
#include <algorithm>
#include <functional>

void func(vector<int>& a, int n, int N)
{
	for (int i = 1, x; i <= n; i++) {
        scanf("%d", &x);
        a.insert(lower_bound(a.begin(), a.end(), x, greater<int>()), x);
        if (a.size() > N) {
            a.pop_back();
        }
    }
}
```

