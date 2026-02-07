# 1653.-LeetCode---Min-deletions-to-make-string-Balanced-in-C
This solution is written in C and has 25ms runtime
```C
int minimumDeletions(char* s) {
    int n = strlen(s);
    int f[n+1];
    memset(f, 0, sizeof(f));
    int b = 0;
    for (int i = 1; i <= n; ++i){
        if(s[i - 1] == 'b') {
            f[i] = f[i - 1];
            ++b;
        } else {
            f[i] = fmin(f[i - 1] + 1, b);
        }
    }
    return f[n];
}
```
