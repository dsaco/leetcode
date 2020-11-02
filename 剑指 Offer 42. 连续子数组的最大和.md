[连续子数组的最大和(简单)](https://leetcode-cn.com/problems/lian-xu-zi-shu-zu-de-zui-da-he-lcof/)

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxSubArray = function (nums) {
	let prev = nums[0];
	let max = prev;
	for (let i = 1; i < nums.length; i++) {
		prev = prev > 0 ? prev + nums[i] : nums[i];
		max = Math.max(max, prev);
	}
	return max;
};
```