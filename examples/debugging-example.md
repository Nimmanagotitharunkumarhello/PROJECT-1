# Example 2: Debugging Code Demo

## How to Use Debug Agent

### Query:
```
"I'm getting ValueError: y_pred must have shape (n_samples,)
Error at line 45: accuracy = accuracy_score(y_true, y_pred)
My code: y_pred = model.predict(X_test)[:100]"
```

### Expected Response:

The Debug Agent will provide:

1. **Root Cause Analysis**
   - Identifies exactly what's wrong
   - Explains why it's happening
   - Shows the problematic code

2. **Corrected Code**
   - Shows the fixed version
   - Highlights the changes
   - Explains the fix

3. **Testing Recommendations**
   - How to verify the fix works
   - Assertions to add
   - Best practices to prevent similar errors

4. **Learning Resources**
   - Why this error happens
   - How to avoid it in future
   - Related concepts

### What You'll Learn:

- How to diagnose error messages
- Understanding Python/ML errors
- Debugging strategies
- Code validation techniques

### Time Required:
- Understanding error: 5 minutes
- Implementing fix: 5 minutes
- Testing: 10 minutes

---

## Code Example

```python
# Test the debug agent
error_code = """
y_pred = model.predict(X_test)[:100]
accuracy = accuracy_score(y_true, y_pred)
"""

query = f"My code is throwing ValueError. Here's the error: {error_code}"
response = test_agent(query)
print(response)
```

### Output Format:

```
🔵 ROUTING: Query routed to DebugAgent
✅ AGENT: Debug Agent activated

🔴 ERROR IDENTIFIED: ValueError

📝 ERROR MESSAGE:
   "y_pred must have shape (n_samples,)"
   at line 45: accuracy = accuracy_score(y_true, y_pred)

🔍 ROOT CAUSE ANALYSIS:
   Your prediction array has been sliced to [:100]
   - y_true has 10,000 samples
   - y_pred has only 100 samples
   - Shape mismatch causes error

❌ PROBLEMATIC CODE:
   y_pred = model.predict(X_test)[:100]
   accuracy = accuracy_score(y_true, y_pred)

✅ CORRECTED CODE:
   y_pred = model.predict(X_test)
   accuracy = accuracy_score(y_true, y_pred)

💡 EXPLANATION:
   Remove the slicing [:100] to get predictions for all samples,
   matching the shape of y_true.

🧪 TESTING RECOMMENDATIONS:
   1. Add shape assertions before accuracy calculation:
      assert len(y_pred) == len(y_true), "Shape mismatch!"
   
   2. Print shapes for debugging:
      print(f"y_true: {y_true.shape}, y_pred: {y_pred.shape}")
   
   3. Use try-except for error handling:
      try:
          accuracy = accuracy_score(y_true, y_pred)
      except ValueError as e:
          print(f"Error: {e}")

📚 LEARNING RESOURCES:
   - Always verify array shapes before metric calculations
   - Use assertions to catch shape mismatches early
   - Common sklearn error: shape mismatch between y_true and y_pred
```

---

## Common Error Types

### Type 1: Shape Mismatch
```
Error: ValueError: y_pred must have shape (n_samples,)
Fix: Ensure y_true and y_pred have same length
```

### Type 2: Import Missing
```
Error: ModuleNotFoundError: No module named 'xgboost'
Fix: pip install xgboost
```

### Type 3: Type Error
```
Error: TypeError: unsupported operand type(s)
Fix: Convert data to correct type
```

### Type 4: Attribute Error
```
Error: AttributeError: 'NoneType' object has no attribute
Fix: Check if object is None before using it
```

---

## Best Practices

1. **Always print shapes** before operations
2. **Use assertions** for validation
3. **Add try-except** for critical code
4. **Log errors** with context
5. **Read error messages** carefully

---

## Troubleshooting

**Problem**: Agent doesn't understand my error
**Solution**: Provide the complete error message and code

**Problem**: Fix doesn't work
**Solution**: Copy-paste the exact corrected code from agent

**Problem**: Same error keeps happening
**Solution**: Ask agent to explain the root cause more deeply

---

**Need more help?** Ask the Debug Agent for additional examples!
