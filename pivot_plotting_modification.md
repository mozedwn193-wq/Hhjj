# Pivot Plotting Modification Guide

## **What to Change in Your Original Script**

### **Find This Code in Your Original Script:**

```pinescript
// Look for this pattern in your SFP logic
if is_new_htf_bar_SFP
    // ... other SFP logic ...
    
    if checkForPivot(sfp_history_highs, pivot_idx_h, leftBars_SFP, rightBars_SFP, true)
        // Pivot plotting happens here
        drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_high, pivot_idx_h), array.get(sfp_history_highs, pivot_idx_h), phColor_SMT)
    
    if checkForPivot(sfp_history_lows, pivot_idx_h, leftBars_SFP, rightBars_SFP, false)
        // Pivot plotting happens here
        drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_low, pivot_idx_h), array.get(sfp_history_lows, pivot_idx_h), plColor_SMT)
```

### **Change It To This:**

```pinescript
// Remove the if is_new_htf_bar_SFP condition from plotting only
if is_new_htf_bar_SFP
    // ... other SFP logic ...
    
    // Keep all other logic inside the if condition
    // But move the plotting outside

// Move plotting outside the if condition (no waiting for new HTF bar)
if checkForPivot(sfp_history_highs, pivot_idx_h, leftBars_SFP, rightBars_SFP, true)
    // Pivot plotting happens immediately when detected
    drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_high, pivot_idx_h), array.get(sfp_history_highs, pivot_idx_h), phColor_SMT)

if checkForPivot(sfp_history_lows, pivot_idx_h, leftBars_SFP, rightBars_SFP, false)
    // Pivot plotting happens immediately when detected
    drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_low, pivot_idx_h), array.get(sfp_history_lows, pivot_idx_h), plColor_SMT)
```

## **What This Change Does:**

### **Before (waits for new HTF bar):**
```pinescript
if is_new_htf_bar_SFP  // Only when new HTF bar starts
    if checkForPivot(...)
        drawPivotCross(...)  // Plot only when new HTF bar starts
```

### **After (no waiting for new HTF bar):**
```pinescript
if is_new_htf_bar_SFP
    // ... other logic stays inside ...

// Plotting moved outside - no waiting for new HTF bar
if checkForPivot(...)
    drawPivotCross(...)  // Plot immediately when detected
```

## **Result:**

- ✅ **Keep all SMT SFP script logic exactly the same**
- ✅ **Keep all pivot detection logic exactly the same**
- ✅ **Only remove the waiting for new HTF bar from plotting**
- ✅ **Pivot plots appear immediately when detected (during the move)**
- ✅ **No waiting for new HTF bar**

## **Important Notes:**

1. **Keep all other logic inside the `if is_new_htf_bar_SFP` condition**
2. **Only move the `drawPivotCross` calls outside**
3. **Don't change any other part of the script**
4. **This makes pivots appear immediately like multi-timeframe intrabar**

## **Example of Complete Change:**

### **Original Code:**
```pinescript
if is_new_htf_bar_SFP
    // Session tracking
    sfp_session_high := high
    sfp_session_low := low
    
    // History collection
    array.push(sfp_history_highs, sfp_session_high[1])
    array.push(sfp_history_lows, sfp_session_low[1])
    
    // Pivot detection and plotting
    int pivot_idx_h = array.size(sfp_history_highs) - 1 - rightBars_SFP
    if checkForPivot(sfp_history_highs, pivot_idx_h, leftBars_SFP, rightBars_SFP, true)
        drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_high, pivot_idx_h), array.get(sfp_history_highs, pivot_idx_h), phColor_SMT)
```

### **Modified Code:**
```pinescript
if is_new_htf_bar_SFP
    // Session tracking
    sfp_session_high := high
    sfp_session_low := low
    
    // History collection
    array.push(sfp_history_highs, sfp_session_high[1])
    array.push(sfp_history_lows, sfp_session_low[1])

// Pivot detection and plotting (moved outside - no waiting)
int pivot_idx_h = array.size(sfp_history_highs) - 1 - rightBars_SFP
if checkForPivot(sfp_history_highs, pivot_idx_h, leftBars_SFP, rightBars_SFP, true)
    drawPivotCross(sfp_PivotLabels, array.get(sfp_history_times_high, pivot_idx_h), array.get(sfp_history_highs, pivot_idx_h), phColor_SMT)
```

**This is the exact change you need to make!**