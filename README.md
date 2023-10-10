# leetcode精选100道题---java实现
## 1. 两数之和
- 暴力枚举 ---双重for循环（比较简单 略）
- 哈希
  - 查找考虑哈希表，使用HashMap，key存储数组元素值，value存储元素对应下标
  - 遍历数组元素，每遍历完一个数组元素值，都将该元素和对应下标存入map集合中
  - 两数之和target-当前遍历的元素值=另一个元素值，在map集合中查找该元素值，如果有，则返回下标
  - 无论是否在map中查找到另一个元素值，都将当前元素值和对应下标存入map集合中
- 代码实现
  ~~~ java
  class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] res =new int [2];
        if(nums == null|| nums.length == 0){
            return res;
        }
        Map<Integer,Integer> map=new HashMap();
        for(int i=0;i<nums.length;i++){
            int temp = target - nums[i];
            if(map.containsKey(temp)){
                res[1]=i;
                res[0]=map.get(temp);
            }
            map.put(nums[i],i);
        }
        return res;
    }
  }  
  
