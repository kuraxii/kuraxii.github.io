---
title: "C++: strategy pettern"
date: "2025-03-24"
summary: "."
description: ""
toc: false
readTime: true
autonumber: true
math: true
tags: ["cpp", "design pettern"]
showTags: true
---

# Introduce

In computer programming, the strategy pettern(also known as the policy pettern) is a behavioral software design pettern that enables selecting an algorithm at runtimes. Instead of implementing a signal algorithm directly, code recevices runtime instruction as to which in a family of algorithm to use.


# code 

```cpp
// 使用策略模式提炼相同方法
// 可以很方便的增加策略
struct Reducer {
    virtual int init() = 0;
    virtual int calc(int a, int b) = 0;
    virtual ~Reducer() = default;
};

struct SumReducer : Reducer {
    int init() override { return 0; }
    int calc(int a, int b) override { return a + b; };
};

struct ProductReducer : Reducer {
    int init() override { return 1; }
    int calc(int a, int b) override { return a * b; };
};

struct MinReducer : Reducer {
    int init() override { return numeric_limits<int>::max(); }
    int calc(int a, int b) override { return min(a, b); }
};

struct MaxReducer : Reducer {
    int init() override { return numeric_limits<int>::min(); }
    int calc(int a, int b) override { return max(a, b); }
};

int calc(vector<int> v, Reducer* func) {
    int res = func->init();
    for (auto i : v) {
        res = func->calc(res, i);
    }
    return res;
}
```