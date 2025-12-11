# Metric Card Animation Component

An animated metric card component built with Tailwind CSS, featuring smooth entrance animations and interactive states.

## Design Reference

Based on the Figma design: [Performance Tiles Experiment](https://www.figma.com/design/bjIC6WdM9wBchYLE2Ol2p0/Performance-tiels-experiment?node-id=118-5831)

## Features

### Entrance Animations

The metric card includes several coordinated entrance animations:

| Element | Animation | Delay | Duration |
|---------|-----------|-------|----------|
| Header row | Fade in + slide up | 0ms | 600ms |
| Main metric number | Scale pop + count up | 200ms | 800ms |
| Progress bar | Width fill | 300ms | 1200ms |
| Growth badge | Pop + rotate | 400ms | 500ms |
| Message | Fade in + slide up | 500ms | 600ms |
| Percentage | Slide in from right | 600ms | 500ms |

### Animation Types

1. **fade-in-up** - Elements fade in while sliding up from below
2. **count-up** - Number scales from small to normal size with a bounce
3. **progress-fill** - Progress bar fills from 0 to target width
4. **badge-pop** - Badge pops in with a slight rotation for emphasis
5. **shimmer** - Subtle shimmer effect on the progress bar
6. **slide-in-right** - Element slides in from the right

### Interactive States

- **Hover lift** - Card lifts slightly with enhanced shadow on hover
- **Link hover** - CTA link color darkens on hover
- **Loading state** - Pulse animation variant for loading data

## Usage

### Basic Implementation

```html
<div class="metric-card bg-white rounded-xl shadow-sm border border-gray-200 p-6 hover-lift">
    <!-- Header -->
    <div class="flex items-center justify-between mb-6 animate-on-load animate-fade-in-up">
        <h3 class="text-lg font-semibold text-gray-900">Emails sent</h3>
        <a href="#" class="text-brand-blue-500 font-medium">Send emails</a>
    </div>
    
    <!-- Metric -->
    <div class="flex items-baseline gap-2 animate-on-load animate-count-up delay-200">
        <span class="text-5xl font-bold text-brand-blue-500 number-counter" data-target="3">0</span>
        <span class="text-xl text-gray-400">/ 5 emails</span>
    </div>
    
    <!-- Progress Bar -->
    <div class="h-2.5 bg-gray-200 rounded-full overflow-hidden">
        <div class="progress-bar h-full bg-brand-blue-500 rounded-full animate-progress-fill"
             style="--progress-width: 60%">
        </div>
    </div>
</div>
```

### Customizing Progress

Set the `--progress-width` CSS variable to change the progress bar fill:

```html
<div class="progress-bar" style="--progress-width: 75%"></div>
```

### Customizing the Counter

Set the `data-target` attribute to change the target number:

```html
<span class="number-counter" data-target="10">0</span>
```

## Tailwind Configuration

The component extends Tailwind with custom animations:

```javascript
tailwind.config = {
    theme: {
        extend: {
            keyframes: {
                'fade-in-up': { /* ... */ },
                'count-up': { /* ... */ },
                'progress-fill': { /* ... */ },
                'badge-pop': { /* ... */ },
                'shimmer': { /* ... */ }
            },
            animation: {
                'fade-in-up': 'fade-in-up 0.6s ease-out forwards',
                'count-up': 'count-up 0.8s ease-out forwards',
                'progress-fill': 'progress-fill 1.2s ease-out forwards',
                'badge-pop': 'badge-pop 0.5s ease-out forwards',
                'shimmer': 'shimmer 2s linear infinite'
            }
        }
    }
}
```

## Color Tokens

| Token | Value | Usage |
|-------|-------|-------|
| `brand-blue-500` | #007CFF | Primary blue, metric number, progress bar |
| `brand-blue-600` | #0063CC | Hover state for blue elements |
| `success-green-50` | #ECFDF5 | Growth badge background |
| `success-green-600` | #059669 | Growth badge text/icon |

## Browser Support

- Chrome 88+
- Firefox 78+
- Safari 14+
- Edge 88+

## Files

- `index.html` - Main component with all animations and variants

## Preview

Open `index.html` in a browser to see the animations in action. Click the "Replay Animations" button to restart all entrance animations.

---

**Created:** December 5, 2025  
**Component:** Metric Card with Animations  
**Framework:** Tailwind CSS

