[数组中重复的数字(简单)](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var findRepeatNumber = function (nums) {
	const set = new Set();
	for (let v of nums) {
		if (set.has(v)) {
			return v;
		} else {
			set.add(v);
		}
	}
};

```