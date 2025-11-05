# react-scenario-based-question

## 🧭 Table of Contents

1. [Your React app suddenly becomes slow after adding new features. How do you find and fix the issue?](#1-your-react-app-suddenly-becomes-slow-after-adding-new-features-how-do-you-find-and-fix-the-issue)
2. [How do you prevent a login page being accessible after the user is logged in?](#2-how-do-you-prevent-a-login-page-being-accessible-after-the-user-is-logged-in)
3. [How do you handle API errors gracefully in the UI?](#3-how-do-you-handle-api-errors-gracefully-in-the-ui)
4. [A component is fetching the same data multiple times unnecessarily. How do you fix it?](#4-a-component-is-fetching-the-same-data-multiple-times-unnecessarily-how-do-you-fix-it)
5. [How do you optimize bundle size in a large React app?](#5-how-do-you-optimize-bundle-size-in-a-large-react-app)

---

## 1. Your React app suddenly becomes slow after adding new features. How do you find and fix the issue?

**Diagnosis Steps:**
- Use React DevTools Profiler to identify slow components.
- Check for unnecessary re-renders (`React.memo`, `useMemo`, `useCallback`).
- Inspect large state trees or props causing re-renders.
- Review heavy computations inside render functions.

**Fix Strategies:**
- Use **code-splitting** and **lazy loading**.
- Optimize expensive operations with **memoization**.
- Move expensive logic outside render cycle.
- Limit re-rendering using **shouldComponentUpdate** or **memo**.

---

## 2. How do you prevent a login page being accessible after the user is logged in?

**Approach:**
- Use protected routes with React Router.
- Example:

```jsx
<Route
  path="/login"
  element={!isAuthenticated ? <Login /> : <Navigate to="/" />}
/>
