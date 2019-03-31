#### 实现二分查找

二分查找是在排好序的数组中查找指定数字，给定一个 n 个元素有序的（升序）整型数组 nums 和一个目标值 target  ，写一个函数搜索 nums 中的 target，如果目标值存在返回下标，否则返回 -1。

示例 1:

    输入: nums = [-1,0,3,5,9,12], target = 9
    输出: 4
    解释: 9 出现在 nums 中并且下标为 4



java 代码实现

    public int binarySearch(int[] nums, int key) {
        int l = 0, h = nums.length - 1;
        while (l <= h) {
            int m = l + (h - l) / 2;
            if (nums[m] == key) {
                return m;
            } else if (nums[m] > key) {
                h = m - 1;
            } else {
                l = m + 1;
            }
        }
        return -1;
    }

此方法是正常实现。每次都能将查找区间减半，这种折半特性的算法时间复杂度为 O(logN)。