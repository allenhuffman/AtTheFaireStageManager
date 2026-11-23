This document was created by GitHub A.I. Read with caution...

# AtTheFaire Stage Manager

A sophisticated JavaScript-based scheduling system for managing stage performances at Renaissance Faire events.

## Overview

The AtTheFaire Stage Manager is an interactive web application designed to help event organizers schedule acts across multiple stages while automatically detecting conflicts and managing complex timing constraints. Built in 2010, this application demonstrates advanced scheduling algorithms and interactive web development techniques.

## Features

### Interactive Scheduling Grid
- Visual time-slot grid showing all stages and time periods
- Click-to-place interface for scheduling acts
- Real-time conflict detection and availability highlighting
- Dynamic cell spanning for performances longer than one time slot

### Advanced Conflict Detection
- **Setup/Teardown Time Management**: Accounts for preparation time between shows
- **Break Time Enforcement**: Ensures minimum time between an act's performances
- **Self-Conflict Prevention**: Prevents acts from being scheduled against themselves
- **Multi-Stage Coordination**: Manages scheduling across multiple venue stages

### Flexible Act Management
- Multiple shows per day per act
- Color-coded visual organization
- Configurable duration, setup, and teardown times
- Show pool management (acts have limited shows available)

## Architecture

### Object-Oriented Design
The application uses a hierarchical object structure:

```
Event
├── Day(s)
    ├── Stage(s)
    └── Act(s)
        └── Show(s)
```

### Core Objects

- **`ObjEvent`**: Contains the overall event information
- **`ObjDay`**: Represents a day of the event with stages and acts
- **`ObjStage`**: Individual performance venue with time slots
- **`ObjAct`**: Performance group with multiple shows per day
- **`ObjShow`**: Individual performance instance

### Key Components

#### Stage Management
```javascript
function ObjStage(name) {
  this.timeSlots = [];  // Array of scheduled shows
  this.slotAvailable = slotAvailable;
  this.addToStage = addToStage;
  this.removeFromStage = removeFromStage;
}
```

#### Act Scheduling
```javascript
function ObjAct(name, showsPerDay, color, duration, setupTime, teardownTime, breakTime, conflicts) {
  this.shows = [];  // Pool of available shows to schedule
  this.showsAvailable = showsAvailable;
  this.getShow = getShow;  // Allocates show from pool
}
```

## Configuration

### Time Settings
```javascript
startTime = new Date(2000, 1, 1, 11, 0, 0);  // 11 AM start
endTime = new Date(2000, 1, 1, 18, 0, 0);    // 6 PM end  
slotDuration = 30;  // 30-minute time slots
```

### Sample Stages
- Coliseum Arena
- Gatehouse Stage  
- Minstrel Stage
- Royal Pavilion
- South Meadow
- Theater on the Green
- Tournament Field

### Sample Acts
- Joust Evolution
- Guardians of the Black Forest
- Orckes & Trolles
- Dragon Stories
- Kids With Fire
- And many more Renaissance performers...

## Usage

### Basic Operation
1. **Select an Act**: Click on an act in the right panel to select it
2. **Place on Grid**: Click a highlighted available slot in the time grid
3. **Remove Acts**: Click on scheduled act in grid, then click any act in the list
4. **Deselect**: Click selected item again to deselect

### Visual Feedback
- **Yellow Highlighting**: Shows available time slots for selected act
- **Color Coding**: Each act has its own color for easy identification  
- **Status Messages**: Real-time feedback on actions and conflicts
- **Multi-Slot Spanning**: Long performances automatically span multiple rows

## Advanced Features

### Conflict Resolution
The system prevents scheduling conflicts by checking:
- Previous show's duration + teardown time
- Current show's setup time requirements
- Minimum break time between same act's performances
- Total time slot availability

### Database Abstraction
Includes complete database interface for future persistence:
```javascript
// Act management
dbOpenActs, dbReadActs, dbAddAct, dbDeleteAct, dbUpdateAct

// Stage management  
dbOpenStages, dbReadStages, dbAddStage, dbDeleteStage, dbUpdateStage
```

## Development History

**Version 0.11 (Current)**
- Added ObjEvent and ObjDay framework
- Implemented linkback references between objects
- Enhanced object-oriented architecture

**Previous Versions (0.00-0.10)**
- Initial scheduling logic (0.00)
- Conflict detection system (0.01-0.02)
- Visual enhancements and sorting (0.03-0.04)
- JSLint compliance and code cleanup (0.04-0.09)
- HTML5 database framework preparation (0.10)

## The 2026 rebuild

`stagemanager2026.html` is a single-file rebuild of the scheduler, written in November 2026. Open it in a browser (or serve it from any static host) — data lives in the browser's localStorage. It opens empty: load the v0.11 demo lineup (7 stages, 19 acts) from the button at the top, or add your own days, stages and acts.

It keeps the v0.11 conflict rules (setup/teardown buffers, break time, no act against itself) and adds config screens for days, stages and categories, JSON export/import, batch editing, and three more conflict rules: a per-category cap on how many acts of a type run at once (the 2010 conflicts number, moved to the category), performer groups (acts sharing a group never overlap), and per-act exclusivity with an excepted category (an exclusive joust that still allows childrens acts). Export also shows the data as copyable text when the file download is blocked, and acts can be sorted alphabetically or by category. The version number shows in the header and footer; see `CHANGELOG.md` for the version history.

## Technical Notes

### Code Quality
- **JSLint Compliant**: All warnings resolved for clean, maintainable code
- **JSBeautifier Formatted**: Consistent code formatting throughout
- **Extensive Documentation**: Every function and major change documented

### Browser Compatibility
- Built for 2010-era browsers with modern JavaScript features
- Uses standard DOM manipulation (no external libraries)
- Designed for desktop interaction (pre-mobile-first era)

## Future Enhancements (TODO)

1. **Dynamic HTML Generation**: Replace `document.write` with DOM objects
2. **HTML5 Storage**: Implement local storage for data persistence  
3. **CRUD Interface**: Add screens for creating, editing, and deleting stages/acts
4. **Automatic Scheduling**: AI-powered schedule generation
5. **Export Features**: Generate printable schedules and stage signs
6. **Mobile Support**: Responsive design for tablets and phones
7. **Advanced Time Management**: Minute-level granularity with ObjTime system

## Files

- `stagemanager.html` — the 2010 program, consolidated: v0.11 code with the full routine-only version history (0.00–0.11) in its header.
- `stagemanager2026.html` — the 2026 rebuild (single-file web app; see above).
- `archived/` — the recovered numbered versions of the 2010 program (002, 004–012). Versions 001 and 003 were never found.
- `CHANGELOG.md` — version history of the 2026 app.

## License

Copyright (C) 2010 Allen C. Huffman - Renaissance Faire event management system

---

*This application demonstrates sophisticated event scheduling algorithms and was ahead of its time in terms of interactive web-based venue management.*