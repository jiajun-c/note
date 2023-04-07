# dp 

md 怎么又是dp

## 1. 背包问题

### 1.1 01背包

01 背包是最简单的背包形式，其中的每一个物品的选择只有两种方案，选择和不选择，对于这种问题只需要开
一个dp一维数组就能解决

```cpp
for (int i = 0; i < n; i++)
    for (int j = m; j >= v[i]; j--) {
        dp[j] = max(dp[j], dp[j-cost[i]] + value[i]);
    }
```


### 1.2 多重背包问题

对于多重背包的问题，解决方式是拆分为01背包的形式，但是在拆分的处理上，有两种解决方案

1. 进行一个个的拆分

这个应该就不用说了，但凡考这个应该都会卡这个

2. 进行二进制拆分优化
```cpp
for (int i = 0; i < n; i++) {
    int now = 1;
    while (num[i]) {
        if (num[i] < now) {
            now = num[i];
            num[i] = 0;
        }
        v.push(now*cost[i], now*value[i]);
        num[i] -= now;
        now = now<<1;
    }
}
```

3. 进行单调队列优化




