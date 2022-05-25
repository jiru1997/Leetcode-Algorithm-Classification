### 算法1
##### (差分)  O(n)
#### 时间复杂度

#### C++ 代码
```
class Solution {
public:
    bool carPooling(vector<vector<int>>& trips, int capacity) {
        vector<int> p(1001);
        for(int i = 0; i < trips.size(); i ++)
        {
            p[trips[i][1]] += trips[i][0];
            p[trips[i][2]] -= trips[i][0];
        }

        int sum = 0;
        for(int i = 0; i < 1001; i ++)
        {
            sum += p[i];
            if(sum > capacity) return false;
        }
        return true;
    }
};

```

----------

