# Prototype Design Guide

## Overview

This guide provides patterns and best practices for creating prototypes with Pencil MCP.

## Design Token Setup

### Color System

```javascript
// Primary colors
"primary-50": "#EFF6FF"
"primary-100": "#DBEAFE"
"primary-500": "#3B82F6"
"primary-600": "#2563EB"
"primary-700": "#1D4ED8"

// Neutral colors
"neutral-50": "#F9FAFB"
"neutral-100": "#F3F4F6"
"neutral-200": "#E5E7EB"
"neutral-300": "#D1D5DB"
"neutral-400": "#9CA3AF"
"neutral-500": "#6B7280"
"neutral-600": "#4B5563"
"neutral-700": "#374151"
"neutral-800": "#1F2937"
"neutral-900": "#111827"

// Semantic colors
"success": "#10B981"
"warning": "#F59E0B"
"error": "#EF4444"
"info": "#3B82F6"
```

### Typography

```javascript
// Font family
"font-heading": "Inter, system-ui, sans-serif"
"font-body": "Inter, system-ui, sans-serif"
"font-mono": "JetBrains Mono, monospace"

// Font sizes
"text-xs": "12px"
"text-sm": "14px"
"text-base": "16px"
"text-lg": "18px"
"text-xl": "20px"
"text-2xl": "24px"
"text-3xl": "30px"
"text-4xl": "36px"
"text-5xl": "48px"

// Line heights
"leading-tight": "1.25"
"leading-normal": "1.5"
"leading-relaxed": "1.75"
```

### Spacing

```javascript
// Base unit: 4px
"space-1": "4px"
"space-2": "8px"
"space-3": "12px"
"space-4": "16px"
"space-5": "20px"
"space-6": "24px"
"space-8": "32px"
"space-10": "40px"
"space-12": "48px"
"space-16": "64px"
"space-20": "80px"
```

### Border Radius

```javascript
"radius-sm": "4px"
"radius": "8px"
"radius-lg": "12px"
"radius-xl": "16px"
"radius-2xl": "24px"
"radius-full": "9999px"
```

## Common Components

### Button

```javascript
// Primary button
button=I(parent, {
  type: "frame",
  width: "auto", // or specific width
  height: 40,
  padding: [0, 16],
  fill: "#3B82F6",
  cornerRadius: [8],
  layout: "horizontal",
  alignItems: "center",
  justifyContent: "center"
})
buttonText=I(button, {
  type: "text",
  content: "Button",
  fill: "#FFFFFF",
  fontSize: 14,
  fontWeight: "medium"
})

// Secondary button
secondaryButton=I(parent, {
  type: "frame",
  width: "auto",
  height: 40,
  padding: [0, 16],
  fill: "#FFFFFF",
  stroke: "#D1D5DB",
  strokeWidth: 1,
  cornerRadius: [8]
})
```

### Input Field

```javascript
// Input group (label + input)
inputGroup=I(parent, {
  type: "frame",
  layout: "vertical",
  gap: 8
})
label=I(inputGroup, {
  type: "text",
  content: "Label",
  fontSize: 14,
  fontWeight: "medium",
  fill: "#374151"
})
input=I(inputGroup, {
  type: "frame",
  width: "fill_container",
  height: 40,
  padding: [0, 12],
  fill: "#FFFFFF",
  stroke: "#D1D5DB",
  strokeWidth: 1,
  cornerRadius: [8]
})
placeholder=I(input, {
  type: "text",
  content: "Placeholder",
  fontSize: 14,
  fill: "#9CA3AF"
})

// Error state
errorInput=U(input, {
  stroke: "#EF4444"
})
errorText=I(inputGroup, {
  type: "text",
  content: "Error message",
  fontSize: 12,
  fill: "#EF4444"
})
```

### Card

```javascript
card=I(parent, {
  type: "frame",
  width: "fill_container",
  padding: 24,
  fill: "#FFFFFF",
  cornerRadius: [12],
  stroke: "#E5E7EB",
  strokeWidth: 1
})
cardTitle=I(card, {
  type: "text",
  content: "Card Title",
  fontSize: 18,
  fontWeight: "semibold"
})
cardContent=I(card, {
  type: "text",
  content: "Card content...",
  fontSize: 14,
  fill: "#6B7280"
})
```

### Navigation

```javascript
// Top navigation
navbar=I(screen, {
  type: "frame",
  width: "fill_container",
  height: 64,
  padding: [0, 32],
  fill: "#FFFFFF",
  stroke: "#E5E7EB",
  strokeWidth: 1,
  layout: "horizontal",
  alignItems: "center",
  justifyContent: "space-between"
})
logo=I(navbar, {
  type: "text",
  content: "Logo",
  fontSize: 20,
  fontWeight: "bold"
})
navLinks=I(navbar, {
  type: "frame",
  layout: "horizontal",
  gap: 32
})

// Sidebar navigation
sidebar=I(screen, {
  type: "frame",
  width: 240,
  height: "fill_container",
  padding: 16,
  fill: "#1F2937",
  layout: "vertical"
})
navItem=I(sidebar, {
  type: "frame",
  width: "fill_container",
  height: 40,
  padding: [0, 12],
  fill: "#374151",
  cornerRadius: [8],
  layout: "horizontal",
  alignItems: "center",
  gap: 12
})
navIcon=I(navItem, {
  type: "text",
  content: "📊",
  fontSize: 16
})
navText=I(navItem, {
  type: "text",
  content: "Dashboard",
  fontSize: 14,
  fill: "#FFFFFF"
})
```

## Page Layouts

### Landing Page Structure

```
┌─────────────────────────────────────┐
│            Navigation               │
├─────────────────────────────────────┤
│                                     │
│           Hero Section              │
│    [Title] [Description] [CTA]      │
│                                     │
├─────────────────────────────────────┤
│                                     │
│         Features Section            │
│   [Feature 1] [Feature 2] [Feat 3]  │
│                                     │
├─────────────────────────────────────┤
│                                     │
│         Social Proof                │
│    [Testimonials / Logos]           │
│                                     │
├─────────────────────────────────────┤
│            Footer                   │
└─────────────────────────────────────┘
```

### Dashboard Layout

```
┌────────┬────────────────────────────┐
│        │         Header             │
│  Side  ├────────────────────────────┤
│  Bar   │                            │
│        │       Main Content         │
│  Nav   │    [Cards / Charts]        │
│        │                            │
│        │                            │
└────────┴────────────────────────────┘
```

### Form Page Layout

```
┌─────────────────────────────────────┐
│            Navigation               │
├─────────────────────────────────────┤
│                                     │
│     ┌─────────────────────┐        │
│     │    Form Header      │        │
│     ├─────────────────────┤        │
│     │                     │        │
│     │   Form Fields       │        │
│     │                     │        │
│     │   [Input]           │        │
│     │   [Input]           │        │
│     │   [Button]          │        │
│     │                     │        │
│     └─────────────────────┘        │
│                                     │
└─────────────────────────────────────┘
```

## Tips & Best Practices

1. **Use consistent spacing** - Stick to 8px grid
2. **Limit color palette** - Use defined tokens
3. **Test readability** - Ensure sufficient contrast
4. **Think interaction** - Show hover/focus states
5. **Add annotations** - Explain complex interactions
6. **Use real content** - Avoid "lorem ipsum" when possible
7. **Consider accessibility** - WCAG compliance
8. **Document decisions** - Add notes for rationale
