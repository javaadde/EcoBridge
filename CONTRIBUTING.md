# Contributing to EcoBridge

First off, thank you for considering contributing to EcoBridge! 🎉

## Code of Conduct

Be respectful, inclusive, and constructive. We're all here to learn and build something amazing together.

## How Can I Contribute?

### Reporting Bugs

- Use the issue tracker
- Describe the bug clearly with steps to reproduce
- Include screenshots/videos if possible
- Mention your OS and versions

### Suggesting Features

- Check if the feature is already requested
- Clearly describe the feature and its use case
- Explain why it would benefit users

### Pull Requests

1. **Fork the repo** and create a branch from `main`
2. **Write clean code** following existing patterns
3. **Test thoroughly** - describe your testing in the PR
4. **Document changes** if needed
5. **Submit the PR** with a clear description

## Development Setup

### Mobile (Flutter)
```bash
cd mobile
flutter pub get
flutter run
```

### Desktop (Electron + Next.js)
```bash
cd desktop
npm install
npm run dev
```

## Design Guidelines

- **Minimal & Modern**: Clean, uncluttered interfaces
- **Glassmorphism**: Use subtle blur effects and transparency
- **No AI-ish Designs**: Avoid excessive gradients, over-rounded corners, or unnecessary cards
- **Accessibility**: Ensure readable contrasts and keyboard navigation

## Coding Standards

### Flutter (Mobile)
- Use `const` constructors where possible
- Follow Dart style guide
- Keep widgets small and focused
- Use meaningful names

### TypeScript (Desktop)
- Use TypeScript types properly
- Follow ESLint rules
- Keep components functional
- Use Tailwind for styling (v3.4)

## Testing Your Changes

- Test on multiple screen sizes
- Verify both light and dark modes work
- Check for console errors
- Test edge cases

## AI Usage Policy

✅ **Acceptable:**
- Using AI for boilerplate code
- Getting suggestions for approaches
- Debugging assistance

❌ **Not Acceptable:**
- Copy-pasting raw AI output without understanding
- "Prompt and push" contributions
- Unverified, untested code

**Every PR must include:**
- Description of what changed
- How you tested it
- Screenshots/videos for UI changes

## Questions?

Feel free to open an issue labeled `question` or reach out to maintainers.

---

Happy coding! 🚀
