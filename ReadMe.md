| **Stage**        | **Where?**    | **Template**                  | **Time Cost**    |
| ---------------- | ------------- | ----------------------------- | ---------------- |
| **During Video** | `00_Inbox`    | None (Bullet points)          | Fast             |
| **After Video**  | `20_Concepts` | `T - Concept` / `T - Snippet` | Med              |
| **While Coding** | `T - Bug`     | `T - Bug`                     | Slow (Deep Work) |
Here is the operational algorithm to run your new "Second Brain." This loop turns passive video watching into active documentation.

### The Loop: Input $\rightarrow$ Process $\rightarrow$ Connect

0. Preparation:

Open your 00_Inbox folder and create a file named Daily Scratchpad. This is your messy desk.

**1. The Input Phase (During Video)**

- **State:** Passive / Listening.
    
- **Action:** Do **NOT** use templates yet.
    
- **Task:** As you watch, dump raw bullet points into `Daily Scratchpad`.
    
    - _Example:_ "useEffect runs after render." "Dependency array controls when it runs." "Empty array = run once."
        
- **Constraint:** If the video shows code, **pause**. Type it into your IDE (VS Code) to test it. Do not type code into Obsidian yet.
    

**2. The Processing Phase (Post-Video)**

- **State:** Active / Synthesizing.
    
- **Action:** Look at your messy scratchpad. Identify distinct items.
    
- **Algorithm:** Apply this decision tree to every bullet point:
    

> IF it is a new theory (e.g., "Virtual DOM"):
> 
> $\rightarrow$ Create new file in 20_Concepts named [[Virtual DOM]].
> 
> $\rightarrow$ Insert T - Concept.
> 
> $\rightarrow$ Fill "ELI5" and "Analogy" sections.
> 
> ELSE IF it is a syntax pattern (e.g., "How to map a list"):
> 
> $\rightarrow$ Create new file in 20_Concepts named [[React List Mapping]].
> 
> $\rightarrow$ Insert T - Snippet.
> 
> $\rightarrow$ Paste the minimal code block.
> 
> ELSE IF you made a mistake while coding:
> 
> $\rightarrow$ Create new file in 10_Learning/Session_Logs named [[Error - Infinite Loop]].
> 
> $\rightarrow$ Insert T - Bug.
> 
> $\rightarrow$ Document the fix.

**3. The Cleanup Phase (The "Link" Step)**

- **State:** Architecting.
    
- **Action:** Delete the raw bullet points from `Daily Scratchpad` once they have been moved to their own files.
    
- **Task:** Go into your new notes and add **Links**:
    
    - In `[[React List Mapping]]`, add: _"Requires unique keys. See [[Virtual DOM]] for why."_
        
    - _Why?_ This creates the "knowledge graph" that makes Obsidian powerful.
        

**4. The Retrieval Phase (While Coding)**

- **Scenario:** You are building a project and forget how to do something.
    
- **Action:**
    
    1. Press `Ctrl + O` (Quick Open).
        
    2. Type keywords (e.g., "Map").
        
    3. Open `[[React List Mapping]]`.
        
    4. Copy the syntax.
        
    5. **Update:** If the note was confusing, rewrite it _now_. This is "Refactoring" your brain.
        

---

### Summary Checklist

|**Stage**|**Where?**|**Template**|**Time Cost**|
|---|---|---|---|
|**During Video**|`00_Inbox`|None (Bullet points)|Fast|
|**After Video**|`20_Concepts`|`T - Concept` / `T - Snippet`|Med|
|**While Coding**|`T - Bug`|`T - Bug`|Slow (Deep Work)|

### A Concrete Example (The "useState" Workflow)

1. **Watch:** You learn `useState`. You scribble: _"It adds state to functional components. Uses array destructuring."_
    
2. **Create:** You make a file `[[useState Hook]]`.
    
3. **Template:** You insert `T - Snippet` (because it's mostly syntax).
    
4. **Fill:**
    
    - _Use Case:_ "When I need a variable to change and update the screen."
        
    - _Syntax:_ `const [value, setValue] = useState(initial);`
        
5. **Link:** You add `[[React Hooks]]` as a tag/link.
    
6. **Archive:** You delete the scribble from your scratchpad.
    

Next Step:

Open Obsidian right now. Create the 00_Inbox folder and your Daily Scratchpad. Paste this line at the top of the scratchpad to start your first session:

# React Session 1: [Topic Name]