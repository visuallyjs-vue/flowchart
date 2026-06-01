### About this Demo

This Vue application demonstrates a **Flowchart** editor built with **VisuallyJS**.

### VisuallyJS Components Used

The demo utilizes several components from the `@visuallyjs/browser-ui-vue` package:

- **DiagramProvider**: Provides the VisuallyJS context specifically for diagramming applications.
- **DiagramComponent**: A high-level component for rendering diagrams, handling nodes and edges.
- **DiagramPaletteComponent**: Provides a palette of shapes that can be dragged onto the diagram.
- **ControlsComponent**: UI controls for the diagram (zoom, undo/redo, etc.).
- **ExportControlsComponent**: Provides controls for exporting the diagram.
- **MiniviewComponent**: Displays a small navigation map of the diagram.

### Component Options

The `DiagramComponent` is configured with a `diagramOptions` object:

- **shapes**: An array of shape sets to make available in the diagram (e.g., `FLOWCHART_SHAPES`, `BASIC_SHAPES`).
- **edges**: Configuration for edge behavior (e.g., `CONNECTOR_TYPE_ORTHOGONAL`, label property mappings).
- **grid**: Configures the background grid.
- **lasso**: Enables the lasso tool for multi-selection.

### CSS Requirement

For the VisuallyJS components to render correctly, the standard VisuallyJS stylesheet must be included in the project. In this demo, it is imported in `src/main.js`:

```javascript
import "@visuallyjs/browser-ui/css/visuallyjs.css"
```
