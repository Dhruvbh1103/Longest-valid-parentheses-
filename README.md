# Longest-valid-parentheses-
# Longest Valid Parentheses

Given a string containing only `'('` and `')'`, return the length of the longest valid (well-formed) parentheses substring.

## Examples

| Input      | Output | Explanation                       |
|------------|--------|-----------------------------------|
| `"(()"`    | 2      | Longest valid substring is `"()"` |
| `")()())"` | 4      | Longest valid substring is `"()()"` |
| `""`       | 0      | Empty string                      |

## Approach

Stack of indices:

1. Start with `-1` on the stack as a base marker.
2. On `'('`, push its index.
3. On `')'`, pop the top.
   - If the stack is now empty, push the current index as the new base.
   - Otherwise, the current valid length is `i - stack[-1]`. Update the best length.
4. Return the best length.

## Complexity

- **Time:** O(n), single pass
- **Space:** O(n), stack in the worst case

## Run

```bash
python solution.py
```

## Constraints

- `0 <= s.length <= 3 * 10^4`
- `s[i]` is `'('` or `')'`
