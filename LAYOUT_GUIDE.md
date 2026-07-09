# Publication Layout Guide

This document records the customized publication layout settings for the Beautiful Jekyll academic website.

## Page Width Configuration

### CSS Override for Wider Layout
```css
/* Custom width for this page - much wider to match figure size */
.col-xl-8.offset-xl-2.col-lg-10.offset-lg-1 {
  flex: 0 0 95% !important;
  max-width: 95% !important;
  margin-left: 2.5% !important;
  margin-right: 2.5% !important;
}
```

**Purpose**: Override Beautiful Jekyll's default narrow container to use 95% of viewport width instead of default ~66%.

## Publication Entry Structure

### HTML Layout Pattern
```html
<li style="display: flex; align-items: flex-start; margin-bottom: 20px;">
  <!-- Figure Section -->
  <div style="flex-shrink: 0; margin-right: 20px;">
    <img src="/assets/img/PAPER_FIGURE.png" alt="Paper Overview" 
         style="width: 350px; border: 1px solid #ddd; border-radius: 4px;">
  </div>
  
  <!-- Content Section -->
  <div style="flex: 1;">
    <!-- Title -->
    <div style="margin-bottom: 8px;">
      <strong style="font-size: 18px;">Paper Title</strong>
    </div>
    
    <!-- Authors -->
    <div style="margin-bottom: 8px;">
      <span style="font-size: 16px;">Author List with Co-first Author* Indicators</span>
    </div>
    
    <!-- Conference + Links -->
    <div style="margin-bottom: 8px;">
      <span style="background: #007bff; color: white; padding: 4px 10px; font-size: 16px; 
                   font-weight: bold; border-radius: 3px; margin-right: 8px;">CONFERENCE YEAR</span>
      <a href="URL" style="color: #007bff; text-decoration: none; font-size: 16px;">[Website]</a>
      <a href="URL" style="color: #007bff; text-decoration: none; margin-left: 8px; font-size: 16px;">[Paper]</a>
      <a href="URL" style="color: #007bff; text-decoration: none; margin-left: 8px; font-size: 16px;">[Code]</a>
    </div>
    
    <!-- Description -->
    <div>
      <span style="color: #666; line-height: 1.3; font-size: 14px;">Technical summary and key results.</span>
    </div>
  </div>
</li>
```

## Typography Specifications

### Font Sizes
- **Paper Title**: 18px, bold
- **Authors**: 16px, normal weight
- **Conference Badge**: 16px, bold, white text on blue background
- **Links**: 16px, blue color (#007bff)
- **Description**: 14px, gray color (#666)

### Spacing
- **Vertical spacing**: 8px margin-bottom between each section
- **Horizontal spacing**: 8px margin-left between links
- **Figure margin**: 20px margin-right from figure to text

## Color Scheme
- **Conference Badge Background**: #007bff (Bootstrap blue)
- **Link Color**: #007bff (Bootstrap blue)
- **Description Text**: #666 (medium gray)
- **Figure Border**: #ddd (light gray)

## Layout Features

### Figure Specifications
- **Width**: 350px (large enough for readability)
- **Border**: 1px solid #ddd with 4px border-radius
- **Position**: Left side, aligned with text content top

### Flexbox Configuration
- **Container**: `display: flex; align-items: flex-start`
- **Figure container**: `flex-shrink: 0` (fixed width)
- **Text container**: `flex: 1` (takes remaining space)

### Visual Hierarchy
1. Paper title (largest, bold)
2. Authors (medium size)
3. Conference badge + links (medium, prominent blue styling)
4. Description (smallest, subdued gray)

## Implementation Notes

### CSS Placement
- Custom width CSS should be placed in page YAML front matter style block
- Applied to both `index.html` and `publication.md` for consistency

### Beautiful Jekyll Integration
- Overrides default Bootstrap column classes (.col-xl-8.offset-xl-2.col-lg-10.offset-lg-1)
- Uses !important declarations to ensure override takes effect
- Maintains responsive design principles

### Responsive Behavior
- Layout stacks on small screens (flexbox default behavior)
- Font sizes remain readable across devices
- Figure scales appropriately with container

## Example Implementation

See `index.html` ODESteer paper entry for complete working example of this layout pattern.

## Maintenance

When adding new publications:
1. Follow the exact HTML structure pattern
2. Maintain consistent font sizes and spacing
3. Use same color scheme for visual consistency
4. Ensure figure dimensions are appropriate (350px width recommended)
5. Include all four content sections: title, authors, conference+links, description