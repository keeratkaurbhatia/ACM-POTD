# Intermediate

<img width="1919" height="1029" alt="image" src="https://github.com/user-attachments/assets/4609c3cb-98a0-4eef-aae0-c4b36590af7e" />

```cpp
class MinStack {
private:
    stack<int> st;
    stack<int> minSt;

public:
    MinStack() {}

    void push(int val) {
        st.push(val);
        if (minSt.empty() || val <= minSt.top()) {
            minSt.push(val);
        }
    }

    void pop() {
        if (st.top() == minSt.top()) minSt.pop();
        st.pop();
    }

    int top() {
        return st.top();
    }

    int getMin() {
        return minSt.top();
    }
};

```
