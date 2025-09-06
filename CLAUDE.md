## Repository Management
- Forked "stackblitz-labs/bolt.diy" to "https://github.com/El-Technology/Ellogy_Coder"
- Created a branch "master" at "https://github.com/El-Technology/Ellogy_Coder"
- Customized branch look and feel to fit personal needs
- Goal: Keep fork updated with source repo's new developments while preserving custom design changes

## Manual Branding Changes for Sync-and-Rebrand Script
The following changes should be applied automatically after each upstream sync:

### Color Theme Migration (Purple → Ellogy Blue)
Replace ALL purple color references with Ellogy blue variants:
```bash
# Purple Tailwind classes to blue equivalents
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-50/blue-50/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-100/blue-100/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-200/blue-200/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-300/blue-300/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-400/blue-400/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-500/blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-600/blue-600/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-700/blue-700/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-800/blue-800/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-900/blue-900/g'

# Ring purple classes
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/ring-purple-500/ring-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/ring-purple-600/ring-blue-600/g'

# Background purple classes  
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/bg-purple-500/bg-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/bg-purple-600/bg-blue-600/g'

# Text purple classes
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/text-purple-500/text-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/text-purple-600/text-blue-600/g'

# Border purple classes
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/border-purple-500/border-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/border-purple-700/border-blue-700/g'

# Hover purple classes
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/hover:to-purple-700/hover:to-blue-700/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/hover:border-purple-/hover:border-blue-/g'
```

### Core Theme Variables (app/styles/variables.scss)
```scss
:root {
  --bolt-elements-textPrimary: #1a5eec;
  --bolt-elements-button-primary-background: #1a5eec;
  --bolt-elements-button-primary-backgroundHover: #1648d1;
  --bolt-elements-item-contentAccent: #1a5eec;
  --bolt-elements-item-contentAccentHover: #1648d1;
  --bolt-elements-sidebar-dropdownShadow: 0 4px 20px rgba(26, 94, 236, 0.15);
}

:root[data-theme='dark'] {
  --bolt-elements-textPrimary-dark: #829afa;
  --bolt-elements-button-primary-background-dark: #1a5eec;
  --bolt-elements-button-primary-backgroundHover-dark: #1648d1;
  --bolt-elements-item-contentAccent-dark: #1a5eec;
  --bolt-elements-item-contentAccentHover-dark: #1648d1;
  --bolt-elements-sidebar-dropdownShadow-dark: 0 4px 20px rgba(26, 94, 236, 0.2);
}
```

### Gradient Colors (app/styles/index.scss)
```scss
:root {
  --gradient-opacity: 0.8;
  --primary-color: rgba(26, 94, 236, var(--gradient-opacity));
  --secondary-color: rgba(20, 72, 201, var(--gradient-opacity));
  --accent-color: rgba(130, 154, 250, var(--gradient-opacity));
  --cm-cursor-backgroundColor: var(--bolt-elements-editor-cursorColor, var(--bolt-elements-textSecondary));
  --toastify-color-progress-dark: #1a5eec;
}
```

### UNO CSS Accent Colors (uno.config.ts)
```typescript
accent: {
  50: '#F0F4FF',
  100: '#E0EBFF',
  200: '#C7D8FE',
  300: '#A4BCFD',
  400: '#829AFA',
  500: '#1a5eec',
  600: '#1648d1',
  700: '#1548C9',
  800: '#1437A6',
  900: '#102983',
  950: '#0D1E5F'
}
```

### Logo and Branding (app/components/header/Header.tsx)
```jsx
<img src="/ellogy-logo.svg" alt="Ellogy Coder logo" className="w-[41px] h-[40px] inline-block" />
```

### Page Title and Meta (app/routes/_index.tsx)
```jsx
{ title: 'Ellogy Coder' }
{ name: 'description', content: 'Talk with Ellogy Coder, your AI coding assistant' }
```

### Favicon Files
Ensure these files are present in public/:
- favicon.ico
- apple-touch-icon.png  
- icon-192.png
- icon-512.png
- ellogy-logo.svg

### Hardcoded Purple Hex Colors
Replace any remaining hardcoded purple colors:
- #8A5FFF → #1a5eec
- #B69EFF → #829afa  
- #bb86fc → #1a5eec
- #6D28D9 → #1a5eec (device frame toggle buttons)
- #F5EEFF → #E0EBFF (device dropdown hover background)

### Component-Specific Changes
- UI Checkbox: `data-[state=checked]:bg-blue-500 dark:data-[state=checked]:bg-blue-500`
- All switch/toggle components: Replace purple backgrounds with blue equivalents

## Automation Script Template
Create `sync-and-rebrand.sh` to automate upstream synchronization while preserving branding:

```bash
#!/bin/bash

# Ellogy Coder - Sync and Rebrand Script
# Repository: https://github.com/El-Technology/Ellogy_Coder (master branch)
# Syncs with upstream stackblitz-labs/bolt.diy while preserving Ellogy branding

echo "🔄 Starting sync and rebrand process..."

# 1. Backup current master branch
git checkout master
git branch backup-master-$(date +%Y%m%d-%H%M%S) -f

# 2. Sync with upstream
git remote add upstream https://github.com/stackblitz-labs/bolt.diy.git || true
git fetch upstream
git merge upstream/main

# 3. Apply Ellogy branding changes
echo "🎨 Applying Ellogy branding..."

# Color replacements
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-50/blue-50/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-100/blue-100/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-200/blue-200/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-300/blue-300/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-400/blue-400/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-500/blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-600/blue-600/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-700/blue-700/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-800/blue-800/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/purple-900/blue-900/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/ring-purple-500/ring-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/ring-purple-600/ring-blue-600/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/bg-purple-500/bg-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/bg-purple-600/bg-blue-600/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/text-purple-500/text-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/text-purple-600/text-blue-600/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/border-purple-500/border-blue-500/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/border-purple-700/border-blue-700/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/hover:to-purple-700/hover:to-blue-700/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" | xargs sed -i '' 's/hover:border-purple-/hover:border-blue-/g'

# Hex color replacements
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" -o -name "*.scss" -o -name "*.css" | xargs sed -i '' 's/#8A5FFF/#1a5eec/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" -o -name "*.scss" -o -name "*.css" | xargs sed -i '' 's/#B69EFF/#829afa/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" -o -name "*.scss" -o -name "*.css" | xargs sed -i '' 's/#bb86fc/#1a5eec/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" -o -name "*.scss" -o -name "*.css" | xargs sed -i '' 's/#6D28D9/#1a5eec/g'
find . -name "*.tsx" -o -name "*.ts" -o -name "*.jsx" -o -name "*.js" -o -name "*.scss" -o -name "*.css" | xargs sed -i '' 's/#F5EEFF/#E0EBFF/g'

echo "✅ Branding applied successfully!"
echo "🔍 Run 'git status' to review changes"
```