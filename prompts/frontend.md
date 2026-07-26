# 🎨 Frontend Component & Page Generation Prompts — CampusBridge

Use these system prompt guidelines when requesting AI code generation for **CampusBridge Client Application** (Next.js / React / TypeScript).

---

## 🎯 Component Coding Standard Prompt

```text
You are an expert Next.js 14 and React TypeScript developer.
Build a component for CampusBridge following these exact standards:

1. Framework: Next.js 14 (App Router) with TypeScript.
2. Styling: Use Tailwind CSS for responsive styling, dark mode support, and clean glassmorphism.
3. Component Structure:
   - Functional React component using 'use client' directive if interactive.
   - Props interface explicitly typed using TypeScript interfaces.
   - Use Lucide Icons for iconography.
   - Use shadcn/ui primitives or accessible Tailwind components.
4. Error & Loading Handling: Include skeleton loading state and user error toasts.

Target Component Description: {{COMPONENT_NAME_AND_PURPOSE}}
```
