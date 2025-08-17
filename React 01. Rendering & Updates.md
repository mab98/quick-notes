# React Rendering & Updates

## What Triggers Re-renders
- State changes  
- Prop changes
- Context updates  

---

## Update Phases (after a state change)
1. **Render** → React re-runs the affected components.  
2. **Reconciliation** → React compares the new Virtual DOM (VDOM) with the previous one using its diffing algorithm.  
3. **Commit** → React updates the real DOM with only the minimal necessary changes.  

**Analogy:**  
1. Update the blueprint  
2. Highlight differences  
3. Rebuild using minimal resources  

---

## React’s Internal Process
### 1. Render Phase
- React re-executes all components in the affected branch.  
- Includes calculations, function creations, and side effects.  
- Produces a new VDOM.  

### 2. Reconciliation Phase
- React diffs the old VDOM with the new one.  
- Identifies the exact changes needed.  

### 3. Commit Phase
- React applies only those minimal changes to the real DOM.  

---

## Important Notes
- When a **parent state changes**, the parent and all its children re-render.  
- Re-rendering does **not** mean immediate DOM updates. Instead, a new section of the VDOM is created first.  
- During reconciliation, React checks only the affected old vs. new VDOM section.  
- If the parent’s changed state isn’t passed to children, the diffing algorithm finds no changes in them, and React only commits updates to the parent in the DOM.  
