# 📘 Difference Between PDD and Vibe + PDD

## 🔹 1. What is PDD?

**Prompt-Driven Development (PDD)** is a structured coding workflow where you use AI + prompts to:

1. Define micro-spec
2. Write failing tests
3. Implement smallest code to pass
4. Refactor + docs
5. Commit → PR → merge

✅ Strength: Fast, clear, reliable
❌ Weakness: Less exploration (you depend on the first AI output)

---

## 🔹 2. What is Vibe + PDD?

**Vibe + PDD** adds a **creative exploration stage before PDD**:

1. Vibe Spike (AI generates multiple versions)
2. Select best idea
3. Then follow full PDD steps

✅ Strength: Creative + safer (you don’t get stuck with bad AI code)
❌ Weakness: Slower than plain PDD

---

## 🔹 3. Short Example

### Example Problem: Write a `multiply(a, b)` function

### **PDD way**

1. Micro-spec:

   * Input: two integers
   * Output: product integer

2. Test (fail):

```python
def test_multiply():
    assert multiply(4, 5) == 20
```

3. AI writes code:

```python
def multiply(a, b): return a * b
```

4. Tests pass ✅ → merge.
   But if AI had written wrong style (like recursion, or float-based), you’d be stuck unless you notice.

---

### **Vibe + PDD way**

1. **Vibe Spike**: Ask AI for 3 versions (recursive, iterative, memoized).
2. **Select Best**: Pick iterative (simple, fast).
3. **Micro-spec + Tests** (like PDD).
4. **Smallest Code**:

```python
def multiply(a: int, b: int) -> int:
    return a * b
```

5. Refactor → Docs → PR → Merge ✅

This way you tried options first, then locked into the best one.

---

## 🔹 4. Structure Side-by-Side

### **PDD Structure**

1. Micro-spec
2. Write tests (fail)
3. Implement smallest code (green)
4. Refactor (comments, types)
5. Docs (README / ADR)
6. Commit + PR + CI → merge

---

### **Vibe + PDD Structure**

1. Vibe Spike (explore options with AI)
2. Select best idea
3. Micro-spec
4. Write tests (fail)
5. Implement smallest code (green)
6. Refactor (comments, types)
7. Docs (README / ADR)
8. Commit + PR + CI → merge

---

## 🔹 5. Quick Comparison Table

| Feature             | PDD          | Vibe + PDD                |
| ------------------- | ------------ | ------------------------- |
| Exploration         | ❌            | ✅                         |
| Speed (small tasks) | ✅            | ⚠️ slower                 |
| Code Quality        | ✅            | ✅✅ (higher)               |
| Best for            | Simple tasks | Complex / important tasks |

---

👉 **Summary:**

* Use **PDD** when you need **speed**.
* Use **Vibe + PDD** when you need **quality + creativity**.

