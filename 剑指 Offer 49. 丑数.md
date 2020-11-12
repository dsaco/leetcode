[丑数(中等)](https://leetcode-cn.com/problems/chou-shu-lcof/)

```js
/**
 * @param {number} n
 * @return {string[]}
 */
// 暴力 未通过
var simplifiedFractions = function (n) {
	if (n <= 5) {
		return n;
	}
	const dp = new Array(6);
	dp.fill(true);
	let _n = 5;
	for (let i = 6; ; i++) {
		dp[i] = dp[i / 5] || dp[i / 3] || dp[i / 2];
		if (dp[i]) {
			_n++;
		}
		if (n === _n) {
			return i;
		}
	}
};
var simplifiedFractions = function (n) {
	const dp = [1];
	let i2 = (i3 = i5 = 0);
	for (let i = 1; i < n; i++) {
		dp[i] = Math.min(dp[i2] * 2, dp[i3] * 3, dp[i5] * 5);
		if (dp[i] === dp[i2] * 2) {
			i2++;
		}
		if (dp[i] === dp[i3] * 3) {
			i3++;
		}
		if (dp[i] === dp[i5] * 5) {
			i5++;
		}
	}
	return dp[n - 1];
};
```