### 算法1
##### (二分)  O(nlogn)
#### 时间复杂度

#### C++ 代码
```
class Solution {
public:
    int findInMountainArray(int target, MountainArray &mountainArr) {
        int n = mountainArr.length();
        int l = 0, r = n - 1;
        while(l < r)
        {
            int mid = l + r >> 1;
            if(mountainArr.get(mid) > mountainArr.get(mid + 1)) r = mid;
            else l = mid + 1;
        }

        int peak = r;

        l = 0, r = peak;

        while(l < r)
        {
            int mid = l + r >> 1;
            if(mountainArr.get(mid) >= target) r = mid;
            else l = mid + 1;
        }

        if(mountainArr.get(r) == target) return r;

        l = peak + 1, r = n - 1;

        while(l < r)
        {
            int mid = l + r >> 1;
            if(mountainArr.get(mid) <= target) r = mid;
            else l = mid + 1;
        }

        if(mountainArr.get(r) == target) return r;

        return -1;

    }
};

```

----------

