![Screenshot 2024-12-06 222516](https://github.com/user-attachments/assets/2732f5a8-31a8-456f-b62b-d60751ee9276)
```
#include <iostream>
#include <string>
using namespace std;

string smallest_palindrome(string s) {
    int left = 0;
    int right = s.length() - 1;

    while (left <= right) {
        if (s[left] == s[right] && s[left] == '?') {
            s[left] = s[right] = 'a';
        } else if (s[left] == '?') {
            s[left] = s[right];
        } else if (s[right] == '?') {
            s[right] = s[left];
        } else if (s[left] != s[right]) {
            return "-1";
        }
        left++;
        right--;
    }

    return s;
}

int main() {
    string s;
    cin >> s;

    string result = smallest_palindrome(s);
    cout << result << endl;

    return 0;
}
```
