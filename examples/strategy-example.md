# Example 3: Competition Strategy Demo

## How to Use Strategy Agent

### Query:
```
"Create a 10-day strategy for a binary classification competition 
with 50,000 samples. I'm an intermediate practitioner with 2 hours 
per day available. I want to reach top 10%."
```

### Expected Response:

The Strategy Agent will provide:

1. **Day-by-Day Roadmap**
   - Specific tasks for each day
   - Time allocation
   - Milestones and checkpoints

2. **Priority Ranking**
   - What to focus on first
   - High-impact vs. low-impact tasks
   - Resource allocation

3. **Success Metrics**
   - Accuracy targets for each day
   - Leaderboard position goals
   - Performance benchmarks

4. **Risk Mitigation**
   - Potential bottlenecks
   - Contingency plans
   - Time management tips

### What You'll Learn:

- How to plan competitions effectively
- Time management for ML projects
- Prioritization strategies
- Risk assessment and mitigation

### Time Required:
- Planning: 30 minutes
- Execution: 10 days
- Refinement: Continuous

---

## Code Example

```python
# Test the strategy agent
query = """Create a 10-day strategy for binary classification 
competition with 50k samples. I'm intermediate with 2 hours/day."""

response = test_agent(query)
print(response)
```

### Output Format:

```
🔵 ROUTING: Query routed to StrategyAgent
✅ AGENT: Strategy Agent activated

📅 10-DAY COMPETITION ROADMAP
   Binary Classification Competition
   Dataset: 50,000 samples
   Skill Level: Intermediate
   Time Available: 2 hours/day

DAY 1-2: EXPLORATION & BASELINE (4 hours)
├─ Task 1: Exploratory Data Analysis (1 hour)
│  └─ Outcome: Understand data distribution, missing values, class imbalance
│
├─ Task 2: Feature Analysis (0.5 hour)
│  └─ Identify important features, correlations, data types
│
├─ Task 3: Build Baseline Models (1.5 hours)
│  └─ Try: Logistic Regression, Random Forest, XGBoost
│  └─ Benchmark: Target ~0.85 accuracy
│
└─ Checkpoint: Document findings, select top 2 models

DAY 3-5: FEATURE ENGINEERING (6 hours)
├─ Task 1: Create Polynomial Features (1 hour)
│  └─ Focus on top 3-5 most important features
│
├─ Task 2: Feature Interactions (1 hour)
│  └─ Create interaction terms for correlated features
│
├─ Task 3: Dimensionality Reduction (1 hour)
│  └─ Try PCA or feature selection
│
├─ Task 4: Test on Baseline Models (1 hour)
│  └─ Validate improvements
│
└─ Checkpoint: Accuracy target 0.88+

DAY 6-8: MODEL OPTIMIZATION (6 hours)
├─ Task 1: Hyperparameter Tuning XGBoost (2 hours)
│  └─ Focus: learning_rate, max_depth, subsample
│
├─ Task 2: Hyperparameter Tuning LightGBM (2 hours)
│  └─ Focus: num_leaves, min_data_in_leaf, learning_rate
│
├─ Task 3: Cross-Validation Analysis (1 hour)
│  └─ Implement k-fold CV for reliability
│
└─ Checkpoint: Accuracy target 0.90+

DAY 9-10: ENSEMBLE & SUBMISSION (4 hours)
├─ Task 1: Build Stacking Ensemble (2 hours)
│  └─ Meta-learner: Logistic Regression
│  └─ Base models: XGBoost + LightGBM + Random Forest
│
├─ Task 2: Final Tuning (1 hour)
│  └─ Fine-tune ensemble weights
│
├─ Task 3: Final Submission (0.5 hour)
│  └─ Generate predictions and submit
│
└─ Checkpoint: Final accuracy 0.92+, Top 10% target

⚠️ RISK ASSESSMENT:
├─ Risk 1: Overfitting (Probability: High)
│  └─ Mitigation: Use stratified k-fold cross-validation
│
├─ Risk 2: Feature Explosion (Probability: Medium)
│  └─ Mitigation: Track feature importance, remove low-impact features
│
├─ Risk 3: Time Running Out (Probability: Medium)
│  └─ Mitigation: Submit Day 8, iterate Days 9-10
│
└─ Risk 4: Plateauing Accuracy (Probability: High)
   └─ Mitigation: Ensemble methods, try new features

📊 SUCCESS METRICS:
├─ Day 2: Baseline established (~0.85)
├─ Day 5: Features validated (~0.88)
├─ Day 8: Models optimized (~0.90)
├─ Day 10: Final submission (~0.92)
└─ Leaderboard: Target Top 10%

💡 OPTIMIZATION TIPS:
1. Focus on high-impact tasks first
2. Use cross-validation from the start
3. Ensemble early and often
4. Document all experiments
5. Save all models for ensemble
6. Monitor leaderboard regularly
7. Don't over-optimize training data

🎯 ALTERNATIVE PLANS:
If stuck at 0.88:
  → Skip feature engineering
  → Focus on ensemble methods
  → Try different base models

If stuck at 0.90:
  → Try advanced ensembling (voting, stacking)
  → Experiment with data preprocessing
  → Consider external data/features
```

---

## Weekly Planning Template

### Week 1 (Days 1-5)
- **Focus**: Foundation building
- **Goal**: 0.88 accuracy baseline
- **Key Tasks**: EDA, Baseline, Features

### Week 2 (Days 6-10)
- **Focus**: Optimization
- **Goal**: 0.92+ accuracy
- **Key Tasks**: Tuning, Ensemble, Submit

---

## Checkpoint Checklist

- [ ] Day 2: Baseline model created
- [ ] Day 5: 3+ new features created
- [ ] Day 8: 0.90 accuracy achieved
- [ ] Day 10: Final submission ready

---

## Time Management Tips

1. **Block your time**: 2 hours/day consistently
2. **Track progress**: Document what worked
3. **Stay focused**: Follow the plan
4. **Adjust if needed**: Be flexible with contingencies
5. **Save early**: Backup your code and models

---

## Common Challenges

**Challenge 1**: Stuck at same accuracy
**Solution**: Try ensemble methods or new features

**Challenge 2**: Running out of time
**Solution**: Focus on high-impact tasks, skip low-impact ones

**Challenge 3**: Model not improving
**Solution**: Try different algorithms or data preprocessing

**Challenge 4**: Overfitting on training data
**Solution**: Use cross-validation, add regularization

---

**Ready to execute?** Follow the roadmap and update your progress daily!
