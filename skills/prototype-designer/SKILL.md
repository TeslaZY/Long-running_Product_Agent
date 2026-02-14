# Prototype Designer Skill

## Description

Interactive prototype design skill that generates visual prototypes using Pencil MCP. Creates wireframes, mockups, and interactive prototypes based on PRD specifications.

## When to Use

- Triggered by `/pm:design` command (after PRD generation)
- When visual representation of requirements is needed
- Before development to validate design decisions

## Prerequisites

- Pencil MCP must be available
- PRD should be complete with UI/UX specifications
- Design tokens should be defined

## Process

### Step 1: Prepare Design Context

```
Read Product-PRD.md
Extract:
- Screen inventory
- User flows
- Design tokens
- UI specifications
```

### Step 2: Get Design Guidelines

```javascript
// Get Pencil MCP guidelines
mcp__pencil__get_guidelines({topic: "landing-page"})
// or "design-system" for app design
```

### Step 3: Create Design Tokens

Use Pencil MCP variables for consistent design:

```javascript
mcp__pencil__set_variables({
  variables: {
    "primary-color": "#3B82F6",
    "secondary-color": "#10B981",
    "background": "#FFFFFF",
    "text-primary": "#1F2937",
    "text-secondary": "#6B7280",
    "font-heading": "Inter",
    "font-body": "Inter",
    "spacing-unit": "8",
    "border-radius": "8"
  }
})
```

### Step 4: Create Screens

For each screen in the inventory:

```javascript
// Get editor state
mcp__pencil__get_editor_state({include_schema: true})

// Create screen frame
mcp__pencil__batch_design({
  operations: `
    // Create main screen
    screen=I(document, {
      type: "frame",
      name: "[Screen Name]",
      width: 1440,
      height: 900,
      fill: "#FFFFFF"
    })
    
    // Add header
    header=I(screen, {
      type: "frame",
      name: "Header",
      layout: "horizontal",
      width: "fill_container",
      height: 64,
      padding: [0, 32],
      fill: "#FFFFFF"
    })
    
    // Add logo placeholder
    logo=I(header, {
      type: "text",
      content: "[Product Name]",
      fontSize: 20,
      fontWeight: "bold"
    })
    
    // Add navigation
    nav=I(header, {
      type: "frame",
      layout: "horizontal",
      gap: 24
    })
    
    // Add main content area
    content=I(screen, {
      type: "frame",
      name: "Content",
      layout: "vertical",
      width: "fill_container",
      padding: 32,
      gap: 24
    })
  `
})
```

### Step 5: Add Components

```javascript
// Add form components
mcp__pencil__batch_design({
  operations: `
    // Input field
    inputGroup=I(content, {
      type: "frame",
      layout: "vertical",
      gap: 8
    })
    label=I(inputGroup, {
      type: "text",
      content: "Email",
      fontSize: 14,
      fill: "#374151"
    })
    input=I(inputGroup, {
      type: "frame",
      width: 320,
      height: 40,
      fill: "#FFFFFF",
      stroke: "#D1D5DB",
      strokeWidth: 1,
      cornerRadius: [8]
    })
    
    // Button
    button=I(content, {
      type: "frame",
      width: 320,
      height: 40,
      fill: "#3B82F6",
      cornerRadius: [8]
    })
    buttonText=I(button, {
      type: "text",
      content: "Submit",
      fill: "#FFFFFF",
      fontSize: 14,
      fontWeight: "medium"
    })
  `
})
```

### Step 6: Create Interactive Elements

```javascript
// Define hover states and interactions
mcp__pencil__batch_design({
  operations: `
    // Button with hover state
    buttonHover=U(button, {
      fill: "#2563EB"
    })
  `
})
```

### Step 7: Validate with Screenshots

```javascript
// Get screenshot for review
mcp__pencil__get_screenshot({
  nodeId: screen
})
```

## Screen Patterns

### Landing Page

```javascript
// Hero section
heroSection=I(screen, {
  type: "frame",
  layout: "horizontal",
  padding: 80,
  gap: 48
})
heroText=I(heroSection, {
  type: "frame",
  layout: "vertical",
  width: 560,
  gap: 24
})
heroTitle=I(heroText, {
  type: "text",
  content: "[Headline]",
  fontSize: 48,
  fontWeight: "bold"
})
heroDescription=I(heroText, {
  type: "text",
  content: "[Description]",
  fontSize: 18,
  fill: "#6B7280"
})
ctaButton=I(heroText, {
  type: "frame",
  width: 160,
  height: 48,
  fill: "#3B82F6",
  cornerRadius: [8]
})
```

### Dashboard

```javascript
// Sidebar
sidebar=I(screen, {
  type: "frame",
  width: 240,
  height: "fill_container",
  fill: "#1F2937",
  padding: 16,
  layout: "vertical",
  gap: 8
})

// Main content
mainContent=I(screen, {
  type: "frame",
  layout: "vertical",
  width: "fill_container",
  padding: 24,
  gap: 24
})

// Cards grid
cardGrid=I(mainContent, {
  type: "frame",
  layout: "horizontal",
  gap: 16
})
```

### Form Page

```javascript
// Form container
form=I(content, {
  type: "frame",
  layout: "vertical",
  width: 480,
  padding: 32,
  fill: "#FFFFFF",
  cornerRadius: [12],
  gap: 24
})

// Form header
formHeader=I(form, {
  type: "text",
  content: "[Form Title]",
  fontSize: 24,
  fontWeight: "bold"
})
```

## Best Practices

1. **Start with structure** - Create frames first, then add content
2. **Use design tokens** - Maintain consistency with variables
3. **Validate frequently** - Check screenshots after each section
4. **Think responsive** - Consider different screen sizes
5. **Add annotations** - Use notes for specifications
6. **Create variations** - Show different states (hover, active, error)

## Output

- `.pen` file with all screens
- Screenshots for documentation
- Design token documentation

## Integration with PRD

Each screen should map to:
- User flow step in PRD
- Functional requirements
- UI specifications

See `assets/prototype-guide.md` for detailed patterns.
