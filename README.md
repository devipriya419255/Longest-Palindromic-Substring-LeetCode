# ↔️ LeetCode 5: Longest Palindromic Substring (C++)

An efficient implementation to find the longest contiguous sequence in a string that reads the same forwards and backwards.

## 📖 Problem Description
Given a string `s`, return the longest palindromic substring in `s`.

### Example
- **Input:** `s = "babad"`
- **Output:** `"bab"`
- **Note:** `"aba"` is also a valid answer.

## 🛠️ Technical Approach
This solution utilizes the **Expand Around Center** strategy:
1. **Centers:** A palindrome can be centered at a character (odd length, e.g., "aba") or between two characters (even length, e.g., "abba").
2. **Expansion:** For every index `i` in the string, we treat it as a center and expand outwards as long as the characters on both sides match.
3. **Tracking:** We maintain a `start` index and `maxLen` to keep track of the best palindrome found so far.
4. **Helper Function:** The `expand` method handles the boundary checks and length updates for both odd and even cases.

## 📊 Complexity Analysis
- **Time Complexity:** $O(n^2)$ — Where $n$ is the length of the string. We expand around $2n-1$ possible centers.
- **Space Complexity:** $O(1)$ — Only a few integer variables are used to store indices; no extra data structures are required.

## 💡 Key Edge Cases Handled
- Single character strings (returns the character itself).
- Strings with no palindromes longer than 1 (returns the first character).
- Strings where the entire input is a palindrome.
- Even vs. Odd length palindromes.
