# AGENTS.md

This file contains guidelines for agentic coding agents working in this React course repository.

## Project Overview

This is an **educational React course** focused on teaching React fundamentals through simple, browser-based examples. The project uses CDN-hosted libraries and Babel transpilation - no build tools or complex setup required.

## Build/Lint/Test Commands

**No package.json or build tools configured** - this is a minimal educational setup:

### Running Code
- Open HTML files directly in a web browser
- Use browser developer tools for debugging
- No command-line tools required

### Testing
- Manual testing by opening HTML files in browser
- Visual verification of component behavior
- No automated testing framework configured

## Code Style Guidelines

### File Structure
- All React code lives in `<script type="text/babel">` tags within HTML files
- Use `.html` extension for all files
- Place React container div with class `js-container` in body
- Load CDN scripts in head section

### React Patterns

#### Components
- **Functional components only** - no class components
- **PascalCase naming** for components (`ChatInput`, `ProductDetails`)
- **Props destructuring** in function parameters: `function Component({ prop1, prop2 })`
- **Component composition** over complex inheritance

#### State Management
- Use `React.useState()` hook exclusively
- **Descriptive state names**: `inputText`, `chatMessages`, `count`
- **Setter functions**: `setInputText`, `setChatMessages`, `setCount`
- Initialize state with appropriate default values

#### Event Handling
- **Named functions** for event handlers, not inline arrows
- **Descriptive function names**: `saveInputText`, `sendMessage`, `increaseCount`
- Use proper event parameter: `function handleChange(e)`

#### JSX Patterns
- **Conditional rendering** with `&&` operator for simple conditions
- **Ternary operators** for if-else logic
- **Array.map()** for list rendering with unique `key` props
- Use `crypto.randomUUID()` for generating unique keys
- **Fragment syntax** (`<>...</>`) for multiple root elements

### Import Patterns
```html
<script src="https://unpkg.com/supersimpledev/react.js"></script>
<script src="https://unpkg.com/supersimpledev/react-dom.js"></script>
<script src="https://unpkg.com/supersimpledev/babel.js"></script>
<!-- Additional libraries as needed -->
<script src="https://unpkg.com/supersimpledev/chatbot.js"></script>
```

### Naming Conventions

#### Components
- PascalCase: `ChatInput`, `ChatMessage`, `ProductDetails`

#### Functions & Variables
- camelCase: `saveInputText`, `sendMessage`, `inputText`, `chatMessages`
- Use descriptive verbs for functions: `save`, `send`, `increase`, `reset`

#### CSS Classes
- kebab-case with `js-` prefix: `js-container`
- Use semantic class names

### Code Organization

#### Component Structure
```javascript
function ComponentName({ prop1, prop2 }) {
  const [state, setState] = React.useState(initialValue);
  
  function eventHandler(e) {
    // Handle event
  }
  
  return (
    // JSX content
  );
}
```

#### App Structure
```javascript
function App() {
  const [mainState, setMainState] = React.useState(initialValue);
  
  return (
    <>
      <Component1 prop={mainState} setProp={setMainState} />
      <Component2 prop={mainState} />
    </>
  );
}

const container = document.querySelector('.js-container');
ReactDOM.createRoot(container).render(<App />);
```

### Error Handling
- Keep error handling simple and educational
- Use basic conditional checks
- Focus on clarity over complex error boundaries

### Comments
- Use comments to explain React concepts (as seen in existing code)
- Explain `&&` operator and other React patterns
- Keep comments educational and beginner-friendly

## Best Practices for This Course

1. **Maintain simplicity** - This is educational code, not production
2. **Use functional components** with React hooks only
3. **Follow existing patterns** - don't introduce complex architectures
4. **Keep code readable** - prioritize learning over optimization
5. **Use CDN libraries** from `supersimpledev` domain consistently
6. **Include proper keys** when rendering lists
7. **Use descriptive names** for functions, variables, and components
8. **Test in browser** - ensure code works by opening HTML files

## What to Avoid

- No class components
- No complex state management (Redux, Context API unless specifically taught)
- No build tools or bundlers
- No TypeScript (unless specifically introduced)
- No testing frameworks
- No CSS-in-JS libraries (use plain CSS or inline styles)
- No external package managers

## File Modification Guidelines

When modifying existing files:
1. Preserve the existing HTML structure
2. Maintain the CDN script loading order
3. Follow established component patterns
4. Keep code educational and clear
5. Test changes by opening the HTML file in a browser

## Example Code Structure

```html
<!DOCTYPE html>
<html>
<head>
  <title>Lesson Title</title>
</head>
<body>
  <div class="js-container"></div>
  
  <script src="https://unpkg.com/supersimpledev/react.js"></script>
  <script src="https://unpkg.com/supersimpledev/react-dom.js"></script>
  <script src="https://unpkg.com/supersimpledev/babel.js"></script>
  
  <script type="text/babel">
    // React components and app logic here
  </script>
</body>
</html>
```

This repository prioritizes **learning React fundamentals** over production-ready code. Maintain this educational approach when making any modifications.