### 2024.5.30 x的平方根 https://leetcode.cn/problems/sqrtx/description/
---

### JS


---

### Java
```java
// 这个要注意int类型边界，最好用long
class Solution {
    public int mySqrt(int x) {
        for (long i = 0; i <= x; i++) {
            long m = i*i;
            long mm = (i+1)*(i+1);
            if (m <= x && mm > x) {
                return (int)i;
            }
        }
        return 0;
    }
}
```