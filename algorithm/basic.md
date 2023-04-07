# 基础算法

## 1. 快速排序算法
直接调库
```shell
sort(v.begin(), v.end())
```

手写快速排序 

## 2. 快速选择算法

直接调库

```C++
n_element(v.begin(), v + rank, v.end(), [&](int a, int b) {
    return v[a] < v[b];
})
```

手写快速选择算法

```c++
bool cmp(int a, int b) {
    if (v[a] != v[b]) return v[a] < v[b];
    return a < b;
}
int quick_select(int l, int r, int k) {
    if (l == r) return w[l];
    int mid = v[(l+r)>>1], i = l - 1, j = r + 1;
    while (i < j) {
        do i++; while(cmp(v[i], mid));
        do j--; while(cmp(mid, v[j]));
        if (i < j)  swap(v[i], v[j]);
    }
    if (k <= j) return quick_select(l, j, k);
    else return quick_select(j+1, r, k);
}
```





