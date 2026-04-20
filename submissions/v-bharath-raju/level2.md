# Level 2 - QA & Security Report

## Setup
- Installed Node.js and dependencies
- Built the project successfully
- Ran test client and verified all tools

## Testing Approach
Tested the LPI sandbox with various edge cases including:
- Invalid inputs
- Empty and whitespace inputs
- Long queries
- Special characters and emoji
- Injection-style inputs

## Test Results

### Invalid Input
Input: !!!!!!!
Result: No crash, handled safely

### Long Input
Input: very long string
Result: No crash or slowdown observed

### SQL Injection Attempt
Input: ' OR 1=1 --
Result: Returned normal data, no injection executed

### Script Injection
Input: <script>alert(1)</script>
Result: Treated as plain text, not executed

### Empty Input
Input: ""
Result: Error message returned: 'query' parameter is required

## Observations

### What worked
- System remained stable under all test conditions
- No crashes or major failures observed
- Required parameters were validated properly

### What did not work as expected
- Some invalid inputs were still accepted instead of being rejected
- Whitespace-only input was treated as valid instead of empty
- Some inputs returned results even when values were incorrect

### Error messages observed
- Error: 'query' parameter is required
- Error: 'phase' parameter is required

## Potential Improvements
- Add stricter validation for empty and whitespace inputs
- Validate input values more strictly
- Improve error handling to avoid exposing internal messages
- Limit input size to prevent misuse

## Conclusion
The LPI sandbox is stable and handles most unexpected inputs safely. However, input validation can be improved to ensure stricter handling of edge cases and enhance overall security.