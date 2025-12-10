# Phase 4: Combat System

**Timeline:** Q3  
**Status:** 10% Complete  
**Priority:** Critical

## Overview

Build comprehensive combat assistance including target tracking, cooldown management, damage analysis, and semi-automated combat rotations.

## Objectives

- ✅ Load combat powers database
- ⏳ Build combat state tracker
- ⏳ Implement cooldown manager
- ⏳ Create queue system
- ⏳ Build combat analytics

---

## Features

### 4.1 Combat State Tracker 🆕
**Status:** 0% Complete  
**Priority:** Critical

- [ ] Combat detection
- [ ] Target tracking
- [ ] Position tracking
- [ ] Combat events
- [ ] State persistence

**Combat States:**
- Idle
- In Combat
- Fleeing
- Resting
- Dead/Knocked Out
- Stunned/Paralyzed

**Data Structure:**
```lua
Combat = {
    active = false,
    target = "",
    targets = {}, -- multiple targets
    position = "fighting",
    health_percent = 100,
    mana_percent = 100,
    moves_percent = 100,
    conditions = {},
    in_party = false,
    tank = ""
}
```

**Tasks:**
- [ ] Detect combat start/end
- [ ] Parse target changes
- [ ] Track position changes
- [ ] Monitor health/mana/moves
- [ ] Detect status conditions
- [ ] Update combat container in real-time

---

### 4.2 Target Manager 🆕
**Status:** 0% Complete  
**Priority:** Critical

- [ ] Target selection
- [ ] Target tracking
- [ ] Multi-target support
- [ ] Target priorities
- [ ] Target macros

**Features:**
- Store current target
- Track target HP if visible
- List all targets in combat
- Set target priority
- Quick-switch targets
- Target history
- Assist target (focus tank's target)

**Tasks:**
- [ ] Parse target from combat messages
- [ ] Store target information
- [ ] Create target switching commands
- [ ] Build target priority system
- [ ] Add target macros (nearest, wounded, etc.)
- [ ] Display target in combat container

---

### 4.3 Cooldown Manager ✅
**Status:** 20% Complete  
**Priority:** Critical

- [x] Powers database with cooldowns
- [ ] Active cooldown tracking
- [ ] Visual indicators
- [ ] Cooldown alerts
- [ ] Cooldown predictions

**Power Categories:**
- At-will (no cooldown)
- Short cooldown (1-3 rounds)
- Medium cooldown (5-10 rounds)
- Long cooldown (30+ rounds)
- Daily/Limited use

**Data Structure:**
```lua
Cooldowns = {
    ["power_name"] = {
        duration = 10, -- seconds
        started = timestamp,
        remaining = 5,
        ready = false
    }
}
```

**Tasks:**
- [ ] Track power usage
- [ ] Calculate cooldown timers
- [ ] Show visual countdown
- [ ] Alert when ready
- [ ] Predict when ready
- [ ] Display in Powers container
- [ ] Add cooldown reduction tracking

---

### 4.4 Combat Queue System 🆕
**Status:** 0% Complete  
**Priority:** High

- [ ] Command queue
- [ ] Priority system
- [ ] Queue execution
- [ ] Queue management
- [ ] Smart delays

**Features:**
- Queue multiple commands
- Set command priorities
- Execute in order
- Pause/resume queue
- Clear queue
- Insert urgent commands
- Handle combat lag

**Use Cases:**
- Pre-combat buff sequence
- Combat rotation
- Flee sequence
- Rescue sequence
- Healing priority

**Tasks:**
- [ ] Build queue data structure
- [ ] Implement priority queue
- [ ] Add execution engine
- [ ] Handle command timing
- [ ] Create queue commands
- [ ] Add visual queue display
- [ ] Save/load queue presets

---

### 4.5 Combat Rotations 🆕
**Status:** 0% Complete  
**Priority:** High

- [ ] Rotation builder
- [ ] Rotation execution
- [ ] Conditional logic
- [ ] Class-specific rotations
- [ ] Rotation templates

**Rotation Components:**
```lua
Rotation = {
    name = "DPS Rotation",
    class = "Warrior",
    conditions = {},
    sequence = {
        { power = "bs", condition = "target_hp > 50" },
        { power = "ds", condition = "my_hp < 50" },
        { power = "ra", condition = "cooldown_ready" }
    }
}
```

**Conditions:**
- HP thresholds (self/target)
- Mana/moves available
- Cooldowns ready
- Buffs/debuffs present
- Number of targets
- Combat round

**Tasks:**
- [ ] Create rotation editor
- [ ] Build condition parser
- [ ] Implement execution engine
- [ ] Add class templates
- [ ] Save/share rotations
- [ ] Test and optimize
- [ ] Add rotation statistics

---

### 4.6 Damage Meter 🆕
**Status:** 0% Complete  
**Priority:** High

- [ ] Damage tracking
- [ ] DPS calculation
- [ ] Damage breakdown
- [ ] Healing tracking
- [ ] Combat reports

**Metrics to Track:**
- Total damage dealt
- Damage per second (DPS)
- Damage per power
- Critical hits
- Damage taken
- Healing received
- Healing done
- Group statistics

**Features:**
- Real-time damage meter
- Breakdown by power type
- Show crits and misses
- Compare with group
- Session statistics
- Export reports
- Historical data

**Tasks:**
- [ ] Parse combat messages
- [ ] Calculate damage totals
- [ ] Track DPS over time
- [ ] Show visual meter
- [ ] Add detailed breakdowns
- [ ] Build reporting system
- [ ] Store combat logs

---

### 4.7 Combat Analytics 🆕
**Status:** 0% Complete  
**Priority:** Medium

- [ ] Combat statistics
- [ ] Performance metrics
- [ ] Optimization suggestions
- [ ] Historical trends
- [ ] Comparison tools

**Analytics:**
- Average DPS
- Power usage frequency
- Cooldown efficiency
- Damage distribution
- Combat duration
- Deaths/hour
- XP/hour
- Resource usage (mana/moves)

**Visualizations:**
- Damage charts
- Power usage graphs
- Performance over time
- Comparison charts

**Tasks:**
- [ ] Collect combat data
- [ ] Calculate metrics
- [ ] Generate reports
- [ ] Create visualizations
- [ ] Add export features
- [ ] Build comparison tools

---

### 4.8 Tank Assistant 🆕
**Status:** 0% Complete  
**Priority:** Medium

- [ ] Threat tracking
- [ ] Rescue alerts
- [ ] Positioning
- [ ] Defensive cooldowns
- [ ] Group protection

**Features:**
- Track who has aggro
- Alert when party member in danger
- Auto-rescue macros
- Defensive rotation
- Taunt management
- Position optimization

**Tasks:**
- [ ] Parse aggro messages
- [ ] Track threat levels
- [ ] Create rescue triggers
- [ ] Build defensive rotation
- [ ] Add taunt queue
- [ ] Monitor party health

---

### 4.9 Healer Assistant 🆕
**Status:** 0% Complete  
**Priority:** Medium

- [ ] Party health tracking
- [ ] Healing priorities
- [ ] Mana management
- [ ] Buff monitoring
- [ ] Resurrection tracking

**Features:**
- Track all party members' health
- Prioritize healing targets
- Manage mana efficiently
- Monitor important buffs
- Queue resurrections
- Dispel debuffs

**Tasks:**
- [ ] Track party health
- [ ] Create healing queue
- [ ] Build priority system
- [ ] Add mana calculator
- [ ] Monitor buff durations
- [ ] Create healing macros

---

### 4.10 Combat Alerts 🆕
**Status:** 0% Complete  
**Priority:** Medium

- [ ] Health warnings
- [ ] Mana warnings
- [ ] Cooldown alerts
- [ ] Status effect alerts
- [ ] Environmental alerts

**Alert Types:**
- Low HP/Mana/Moves
- Buff expiring
- Debuff applied
- Power ready
- Target changed
- Flee recommended
- Group member in danger
- Death alert

**Alert Methods:**
- Visual (screen flash)
- Audio (sound)
- Text (highlighted message)
- GUI update
- All of the above

**Tasks:**
- [ ] Build alert system
- [ ] Add configurable thresholds
- [ ] Create sound effects
- [ ] Add visual indicators
- [ ] Allow user customization
- [ ] Test alert timing

---

### 4.11 Combat Macros 🆕
**Status:** 0% Complete  
**Priority:** Medium

- [ ] Macro builder
- [ ] Conditional macros
- [ ] Combo attacks
- [ ] Emergency actions
- [ ] Group coordination

**Macro Types:**
- Simple (one command)
- Sequence (multiple commands)
- Conditional (if-then logic)
- Smart (adapt to situation)

**Examples:**
```lua
-- Simple rescue macro
macro["rescue"] = "rescue <tank>"

-- Conditional heal
macro["smart_heal"] = function()
    if myHP < 30 then
        send("quaff healing")
    elseif partyHP < 50 then
        send("cast 'heal' <lowest_party>")
    end
end

-- Combat opener
macro["opener"] = {
    "bash", 
    "bs",
    "ua"
}
```

**Tasks:**
- [ ] Create macro engine
- [ ] Build macro editor
- [ ] Add conditional logic
- [ ] Save/load macros
- [ ] Share macros
- [ ] Test thoroughly

---

### 4.12 Combat Logger 🆕
**Status:** 0% Complete  
**Priority:** Low

- [ ] Combat event logging
- [ ] Log filtering
- [ ] Log search
- [ ] Log export
- [ ] Log analysis

**What to Log:**
- Combat start/end
- Damage dealt/taken
- Powers used
- Heals received/given
- Deaths
- Loot received
- XP gained

**Tasks:**
- [ ] Create logging system
- [ ] Add log filters
- [ ] Build search function
- [ ] Export to file
- [ ] Analyze logs
- [ ] Create replay function

---

## Dependencies

- ⏳ Phase 3: Character Management (Stats, Powers)
- ⏳ Phase 2: GUI (Combat Container)
- ✅ Phase 1: Foundation (Database)

## Deliverables

1. ⏳ Combat state tracker
2. ⏳ Target manager
3. ⏳ Cooldown manager
4. ⏳ Combat queue system
5. ⏳ Damage meter
6. ⏳ Combat analytics
7. ⏳ Combat macros
8. ⏳ User documentation

## Success Criteria

- [ ] Combat state tracked accurately
- [ ] Cooldowns displayed correctly
- [ ] Queue executes smoothly
- [ ] Damage meter is accurate
- [ ] Analytics provide insights
- [ ] No performance lag in combat
- [ ] Macros work reliably
- [ ] Users report improved combat efficiency

## Technical Notes

### Performance Considerations
- Combat generates lots of messages
- Parse efficiently
- Update displays throttled
- Use event batching
- Cache calculations

### Accuracy Challenges
- MUD output varies
- Missing messages
- Combat lag
- Multiple targets
- Need robust parsing

### Safety Features
- Emergency stop
- Override controls
- Manual intervention
- Pause automation
- Clear queue quickly

## Risks & Mitigations

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| Parsing errors in combat | High | Medium | Robust patterns, testing |
| Automation death loops | Critical | Low | Safety checks, manual override |
| Performance lag | High | Medium | Optimization, throttling |
| Cooldown desyncs | Medium | Medium | Periodic resync, validation |

## Next Phase

Once combat system is functional, proceed to **Phase 5: Map & Navigation**

---

**Last Updated:** 2024-12-10  
**Owner:** Combat Team
