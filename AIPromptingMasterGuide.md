# 🤖 AI Prompting Master Guide for EcoBridge Contributors

> **For Contributors Using AI Tools:** This guide will help you work effectively with AI coding assistants (GitHub Copilot, ChatGPT, Claude, etc.) while maintaining code quality and project standards.

---

## 🎯 Core Principles

### 1. **AI is a Tool, Not a Replacement**
- AI should **assist** your coding, not **replace** your thinking
- Always understand the code before using it
- Review, test, and refine AI-generated code

### 2. **Specificity is Key**
- Vague prompts = vague results
- Detailed context = accurate code
- Include file paths, variable names, and exact requirements

### 3. **Iterative Refinement**
- Start broad, then narrow down
- Ask follow-up questions
- Build on previous responses

---

## 📝 Prompting Strategies

### Strategy 1: **Context-Rich Prompts**

❌ **Bad Prompt:**
```
"Add a button to the app"
```

✅ **Good Prompt:**
```
"Add a minimal, rounded button to the mobile Flutter app (home_screen.dart) 
that triggers mDNS discovery. The button should:
- Match our black/white minimalist theme
- Be placed below the center icon
- Have a subtle white border (opacity 0.05)
- Show a loading indicator when pressed
- Use the existing _buildMinimalAction() style as reference"
```

**Why it works:** Provides file location, design constraints, behavior requirements, and a reference point.

---

### Strategy 2: **Provide File Context**

Always give AI the current state of your file:

```
"I'm working on desktop/src/app/page.tsx. Here's the current code:
[paste relevant code section]

I need to add a WebSocket connection that:
1. Connects on component mount
2. Handles reconnection on disconnect
3. Displays connection status in the top-right corner
4. Uses our existing color scheme (white/black with opacity)"
```

---

### Strategy 3: **Reference Existing Patterns**

Point AI to similar code in the project:

```
"Looking at how _buildMinimalAction() creates buttons in home_screen.dart,
create a similar function called _buildStatusCard() that displays:
- An icon at the top
- A status text below
- A subtle glow effect on active state
Follow the same styling conventions (opacity values, border radius, spacing)"
```

---

### Strategy 4: **Incremental Development**

Break complex tasks into steps:

```
Step 1: "Create a basic mDNS discovery service class in Dart"
Step 2: "Add error handling to the discovery service"
Step 3: "Integrate the service with the HomeScreen widget"
Step 4: "Add UI feedback for discovered devices"
```

---

### Strategy 5: **Constraint-Based Prompts**

Define what NOT to do:

```
"Add clipboard sync functionality, but:
- DON'T use external libraries (use built-in clipboard APIs)
- DON'T add any colorful gradients (keep black/white theme)
- DON'T create new files (add to existing services/clipboard.dart)
- DON'T use deprecated APIs (check Flutter 3.x compatibility)"
```

---

## 🛠️ Task-Specific Prompting Templates

### For New Features

```
"I'm implementing [FEATURE NAME] for EcoBridge.

Project Context:
- Mobile: Flutter 3.x with minimalist black/white UI
- Desktop: Electron + Next.js + Tailwind 3.4
- Style: No gradients, subtle glows, clean lines

Current State:
[Describe what exists]

Goal:
[Specific feature requirement]

Constraints:
- Must work on Android API 36
- Must match existing code style
- Must be tested before submission

Please provide:
1. Code implementation
2. Where to place it
3. Any dependencies to add
4. How to test it"
```

---

### For Bug Fixes

```
"I'm getting this error in [FILE NAME]:

[Error message]

Here's the relevant code:
[Code snippet]

Environment:
- Flutter version: 3.38.2
- Android SDK: 36
- Gradle: 8.6.1

What I've tried:
[Previous attempts]

Please explain:
1. What's causing this error
2. How to fix it
3. Why this solution works"
```

---

### For Code Review

```
"Review this code for the [FEATURE] implementation:

[Paste code]

Check for:
1. Code quality & readability
2. Performance issues
3. Security concerns (we use AES-256, TLS 1.3)
4. Consistency with project style (minimalist, no fake statuses)
5. Edge cases I might have missed"
```

---

### For Refactoring

```
"This code works but needs refactoring:

[Current code]

Goals:
- Improve readability
- Reduce duplication
- Maintain same functionality
- Keep the same visual design

Constraints:
- Don't change public API
- Keep existing variable names
- Preserve comments"
```

---

## 🎨 Design-Specific Prompts

### UI/UX Prompts

```
"Design a [COMPONENT] for EcoBridge that:

Design Language:
- Minimalist aura theme
- Pure black (#000000) background
- White elements with low opacity (0.05-0.1 for borders, 0.6-0.9 for text)
- Rounded corners (24px for cards, 20px for pills)
- No gradients, no over-rounded shapes
- Subtle shadows and glows only

Inspiration:
- Apple's Dynamic Island
- Frosted glass effects
- Space between elements

Avoid:
- Colorful gradients
- Over-layered cards
- AI-generated aesthetic clichés"
```

---

## 🔍 Debugging Prompts

### When Stuck

```
"I'm stuck on [PROBLEM]. Here's what I know:

What's working:
[List working parts]

What's not working:
[Specific issue]

What I've tried:
1. [Attempt 1]
2. [Attempt 2]

Error logs:
[Paste relevant logs]

Can you:
1. Identify the root cause
2. Suggest 2-3 different approaches
3. Explain trade-offs of each approach"
```

---

## ⚠️ Common Pitfalls to Avoid

### ❌ Pitfall 1: "Prompt and Push"
**Bad:** Copy AI code directly → Push to GitHub  
**Good:** Copy → Understand → Test → Refine → Push

### ❌ Pitfall 2: Over-Engineering
**Bad:** "Create a robust, scalable, enterprise-grade solution..."  
**Good:** "Create a simple, working implementation that can be extended later"

### ❌ Pitfall 3: Ignoring Context
**Bad:** Asking for code without mentioning it's for mobile/desktop  
**Good:** Always specify platform, file location, and design constraints

### ❌ Pitfall 4: Accepting First Answer
**Bad:** Taking the first solution without questioning  
**Good:** Ask "Are there simpler ways?" or "What are the trade-offs?"

### ❌ Pitfall 5: Vague Testing Requests
**Bad:** "Test this code"  
**Good:** "Write unit tests for the mDNS discovery service covering: success case, timeout, invalid response, and network error"

---

## 📊 Prompt Quality Checklist

Before submitting a prompt, check:

- [ ] Did I provide the file name/path?
- [ ] Did I include relevant existing code?
- [ ] Did I specify the platform (mobile/desktop)?
- [ ] Did I mention design constraints?
- [ ] Did I define success criteria?
- [ ] Did I list what NOT to do?
- [ ] Did I ask for explanation, not just code?

---

## 🚀 Advanced Techniques

### Technique 1: **Role-Playing**
```
"Act as a senior Flutter developer reviewing code for a minimalist Android app.
You value clean code, performance, and user experience over complex abstractions."
```

### Technique 2: **Constraint Stacking**
```
"Implement X feature with these constraints:
- Under 50 lines of code
- No external dependencies
- Must work offline
- Must be reversible (undo feature)
- Must not block UI thread"
```

### Technique 3: **Comparative Analysis**
```
"Compare these two approaches for implementing clipboard sync:
Approach A: [Method 1]
Approach B: [Method 2]

Evaluate based on:
- Performance
- Battery impact
- Security
- Code maintainability
- User experience"
```

### Technique 4: **Error Prediction**
```
"Before implementing WebRTC video streaming, what are the top 5 errors
developers typically encounter? How can I prevent each one?"
```

---

## 🎓 Learning from AI

### Use AI to Learn, Not Just to Code

**Good Questions:**
- "Explain how mDNS works in simple terms"
- "Why is AES-256 chosen over other encryption methods?"
- "What's the difference between WebSocket and WebRTC?"
- "How does Flutter's widget tree work internally?"

**Teaching Prompt:**
```
"Explain [CONCEPT] to me as if I'm familiar with programming but new to [TECHNOLOGY].
Use analogies and real-world examples from the EcoBridge project context."
```

---

## 🤝 Collaboration Prompts

### For Team Discussions

```
"I'm working on [FEATURE] and need to coordinate with the [OTHER TEAM/PERSON]
working on [RELATED FEATURE].

My implementation:
[Brief description]

Their implementation (as I understand it):
[Brief description]

What's the best way to:
1. Define the interface between our modules
2. Avoid conflicts
3. Test the integration"
```

---

## 📖 Resources & References

### When to Ask AI
- ✅ Syntax questions
- ✅ Best practices
- ✅ Code explanations
- ✅ Error debugging
- ✅ Refactoring suggestions

### When NOT to Ask AI
- ❌ Architecture decisions (ask maintainers)
- ❌ Security-critical implementations (review required)
- ❌ Design philosophy (read CONTRIBUTING.md)
- ❌ What to work on next (check issues)

---

## 🎯 Example: Full Feature Implementation Prompt

```
"I'm implementing the mDNS device discovery feature for EcoBridge mobile app.

### Context
- File: mobile/lib/services/discovery_service.dart (new file)
- Platform: Flutter 3.x, Android API 36
- Related: Will be called from home_screen.dart

### Current State
- UI is ready with a discover button
- No discovery logic exists yet
- Need to scan for desktop app on local network

### Requirements
1. Create a DiscoveryService class
2. Use multicast_dns package (or similar)
3. Broadcast service name: "_ecobridge._tcp"
4. Scan for 10 seconds, then timeout
5. Return list of discovered devices (IP + port)
6. Handle no devices found gracefully
7. Emit discovery events via Stream

### Design Constraints
- Must request network permissions (handle Android 13+)
- Should work on both WiFi and hotspot
- Must not block UI thread
- Should retry on failure (max 3 attempts)

### Testing
- How to test without desktop app running?
- How to simulate network errors?

### Deliverable
Please provide:
1. Full DiscoveryService class implementation
2. Permission handling code
3. Integration example for home_screen.dart
4. Error handling strategy
5. Testing recommendations

Use our project code style: clear variable names, comprehensive comments,
minimal dependencies.
```

---

## ✅ Success Metrics

You're using AI effectively when:

1. ✅ You understand every line of AI-generated code
2. ✅ You can explain the code to someone else
3. ✅ You catch and fix AI mistakes
4. ✅ You adapt AI suggestions to fit project standards
5. ✅ You use AI to learn, not just to copy-paste

---

## 🙋 FAQ

**Q: How much AI-generated code is acceptable?**  
A: Any amount, as long as you understand it, test it, and it meets quality standards.

**Q: Should I mention I used AI in my PR?**  
A: Optional, but focus on explaining what the code does and how you tested it.

**Q: What if AI gives me deprecated code?**  
A: Always verify with official docs. Ask AI: "Is this code using the latest Flutter 3.x APIs?"

**Q: Can I use AI for commit messages?**  
A: Yes, but review and personalize them. AI often misses context.

---

## 📝 Final Checklist

Before submitting AI-assisted code:

- [ ] I understand what every line does
- [ ] I tested it thoroughly
- [ ] It matches project code style
- [ ] It has no security vulnerabilities
- [ ] It handles errors gracefully
- [ ] It has comments where needed
- [ ] I can defend my implementation choices

---

**Remember:** AI is your **copilot**, not your **autopilot**. You're the developer. You make the decisions. AI just helps you execute them faster.

Happy coding! 🚀
