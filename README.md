# Fallen Tribes - Task Checklist

## Immediate TODO (Current Drag System)

### Phase 1: Core Drag System Polish ✅
- [x] Test current gold/blue hologram drag system thoroughly
- [x] Verify hologram material switching (gold → blue on release)
- [x] Ensure line drawing works correctly between ship and hologram
- [x] Test that only one hologram exists at a time
- [x] Verify ship stays in original position during drag
- [x] Remove cube from scene

### Phase 2: UI Button System
- [x] Create "Move" button component
  - [x] Spawn button when ship is selected
  - [x] Position button relative to ship's world position
  - [x] World-to-screen coordinate transformation
  - [x] Raycasting for button clicks
- [x] Create "Coast" button component
  - [x] Spawn button when hologram exists
  - [x] Position button relative to ship
  - [x] Clicking removes hologram
- [x] Button hover states
- [x] Button styling (matching HTML prototype) (TODO: later)

### Phase 3: Outline System ✅
- [x] Research Bevy 0.17 outline rendering approaches
  - [x] Option A: Post-processing outline shader
  - [x] Option B: Duplicate mesh with inverted normals + scaled
  - [x] Option C: Third-party Bevy outline plugin
- [x] Implement blue outline on hover
- [x] Implement darker blue outline on selection (persists)
- [x] Ensure outlines work with OBJ models loaded via bevy_obj

### Phase 4: Multi-Ship Selection & Estimated Move System ✅
- [x] Add second ship to test multi-ship selection
- [x] Create EstimatedMove struct (position + rotation)
- [x] Track estimated_move per ship in ShipController
- [x] Click ship → select it (darker outline)
- [x] Click elsewhere → deselect ship (via observers)
- [x] Multiple ships: only one selected at a time
- [x] Each ship tracks own hologram/estimated move independently
- [x] Visual feedback for selected vs unselected state
- [x] BONUS: Direct click-and-drag on ships (no Move button needed!)
- [x] BONUS: Mesh-accurate picking and hover detection with observers

### Phase 5: Refactor Drag to Use Move Button
- [x] Remove drag-from-ship behavior
- [x] Implement drag-from-Move-button behavior
- [x] Spawn gold hologram when dragging from Move button
- [x] Hologram follows cursor during drag
- [x] Hologram turns blue on release
- [X] Line still draws from ship to hologram

---

## Future TODO (Based on HTML Prototype Features)

### Turn-Based Movement System
- [ ] Implement turn state machine
  - [ ] Planning phase (click targets, see preview)
  - [ ] Execution phase (animate movement)
  - [ ] End turn button functionality
- [ ] Movement validation
  - [ ] Reachability calculation grid
  - [ ] Green dots for reachable positions
  - [ ] Red dots for unreachable positions
- [ ] Path preview with Bezier curves
- [ ] Display velocity vectors during planning

### Physics Simulation
- [ ] Newtonian physics integration
  - [ ] Initial velocity (vx, vy)
  - [ ] Acceleration/deceleration
  - [ ] Max speed constraints
- [ ] Coupled flight mode
  - [ ] Main thruster acceleration
  - [ ] Automatic deceleration
  - [ ] Turn rate limits (°/s)
- [ ] Decoupled flight mode
  - [ ] Independent thruster control (forward, backward, left, right)
  - [ ] Target rotation control
  - [ ] Maneuvering thrusters
- [ ] Gravity wells
  - [ ] Gravitational bodies with mass/radius
  - [ ] Influence radius visualization
  - [ ] Gravity acceleration calculations
  - [ ] Bezier path modifications from gravity

### Movement Animation
- [ ] Animate ship movement along planned path
  - [ ] Bezier curve interpolation
  - [ ] Rotation animation
  - [ ] Velocity changes over time
- [ ] Ship state updates after movement
  - [ ] Update position
  - [ ] Update velocity
  - [ ] Update heading
- [ ] Movement history tracking
- [ ] Replay system for past moves

### UI & Controls
- [ ] Camera pan controls
  - [ ] Mouse right-click drag
  - [ ] Touch hold to pan
- [ ] Camera zoom controls
  - [ ] Mouse wheel zoom
  - [ ] Pinch to zoom (touch)
  - [ ] Zoom centered on mouse position
- [ ] Control panels
  - [ ] Left sidebar: flight mode & physics parameters
  - [ ] Right sidebar: help & legend
  - [ ] Collapsible sidebars
  - [ ] Bottom button bar (Coast, End Turn, Replay)
- [ ] Status display
  - [ ] Current zoom level
  - [ ] Reachability status
  - [ ] Turn state

### Strategic Depth
- [ ] Reachability calculations
  - [ ] Grid-based reachability analysis
  - [ ] Path validation
  - [ ] Time-limited movement
- [ ] Movement cost visualization
  - [ ] Speed magnitude display
  - [ ] Segment time labels
  - [ ] Thrust indicators (decoupled mode)
- [ ] Multiple ship coordination
  - [ ] Select different ships
  - [ ] Individual movement planning
  - [ ] Turn order management

### Visual Polish
- [ ] Ship rendering
  - [ ] Blue ship (current position, with glow)
  - [ ] Gold ship (dragging preview)
  - [ ] Orange ship (destination preview)
  - [ ] Ghost ships along path
- [ ] Path visualization
  - [ ] Smooth Bezier curves
  - [ ] Fading opacity along path
  - [ ] Velocity vector arrows
  - [ ] Segment markers with time labels
- [ ] Grid rendering
  - [ ] Dynamic grid density
  - [ ] Reachability overlay
  - [ ] Coordinate system
- [ ] Gravity well visualization
  - [ ] Colored influence radius rings
  - [ ] Acceleration labels
  - [ ] Gradient field visualization

### Advanced Features
- [ ] Collision detection
  - [ ] Ship-to-ship collisions
  - [ ] Ship-to-gravity-well collisions
- [ ] Obstacles/terrain
- [ ] Fog of war
- [ ] Multiple teams/factions
- [ ] Combat system
- [ ] Resource management

---

## Technical Debt & Optimization
- [ ] Performance profiling
- [ ] Asset loading optimization
- [ ] Shader compilation caching
- [ ] Entity pooling for holograms
- [ ] Efficient reachability grid calculation
- [ ] LOD system for distant ships

---

## Documentation
- [ ] Update README.md with current progress
- [ ] Document ship state machine
- [ ] Document physics simulation parameters
- [ ] Add code comments for complex systems
- [ ] Create user guide for controls
