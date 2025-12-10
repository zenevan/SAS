# Contributing to TorilLib

Thank you for your interest in contributing to TorilLib! This document provides guidelines and instructions for contributing to the project.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Development Setup](#development-setup)
3. [Code Style](#code-style)
4. [Contribution Workflow](#contribution-workflow)
5. [Testing](#testing)
6. [Documentation](#documentation)
7. [Community](#community)

---

## Getting Started

### Prerequisites

- **Mudlet Client**: Version 4.0 or higher
- **Lua Knowledge**: Basic to intermediate Lua programming
- **TorilMUD Account**: For testing
- **Git**: For version control
- **GitHub Account**: For pull requests

### First Steps

1. Read the [README](../README.md)
2. Review the [ROADMAP](./ROADMAP.md)
3. Join our [Discord](#) or [Forums](#)
4. Check [open issues](link-to-issues)
5. Find a good first issue

---

## Development Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-org/TorilLib.git
cd TorilLib
```

### 2. Install in Mudlet

1. Copy to Mudlet packages directory:
   - Windows: `%APPDATA%/Mudlet/profiles/[profile]/`
   - Mac: `~/Library/Application Support/Mudlet/profiles/[profile]/`
   - Linux: `~/.config/mudlet/profiles/[profile]/`

2. Or install as Mudlet package:
   - Package Manager → Install → Select TorilLib

### 3. Enable Development Mode

```lua
TorilLib.DevMode = true
TorilLib:reload()
```

### 4. Create a Branch

```bash
git checkout -b feature/your-feature-name
```

---

## Code Style

### Lua Style Guide

#### Naming Conventions

```lua
-- Constants: UPPER_SNAKE_CASE
local MAX_HEALTH = 100

-- Global tables: PascalCase
TorilLib = TorilLib or {}

-- Functions: camelCase
function TorilLib:updateHealth() end

-- Local variables: camelCase
local currentHealth = 50

-- Private functions: _prefixed
local function _internalHelper() end
```

#### Formatting

```lua
-- Indentation: 4 spaces (no tabs)
function example()
    if condition then
        doSomething()
    end
end

-- Table definitions
local config = {
    setting1 = true,
    setting2 = "value",
    nested = {
        option = 1
    }
}

-- Function calls
someFunction(arg1, arg2, arg3)

-- Long arguments
someFunction(
    longArgumentName1,
    longArgumentName2,
    longArgumentName3
)
```

#### Comments

```lua
-- Single line comment for simple explanations

--[[
    Multi-line comment for complex explanations
    Describe what the code does and why
--]]

--- Documentation comment for functions
--- @param name string The player name
--- @param level number The player level
--- @return boolean Success status
function TorilLib:setPlayer(name, level)
    -- Implementation
end
```

#### Best Practices

```lua
-- Use local variables when possible
local function fastFunction()
    local x = 10  -- Faster than global
    return x * 2
end

-- Cache frequently accessed values
local strlen = string.len
local function processString(str)
    return strlen(str)  -- Faster than string.len(str)
end

-- Guard clauses for early returns
function validateInput(input)
    if not input then return false end
    if input == "" then return false end
    -- Process valid input
    return true
end

-- Avoid creating tables in loops
local results = {}
for i = 1, 1000 do
    -- Bad: results[i] = {}
    -- Good: Use table.insert or pre-allocate
    results[i] = processSomething(i)
end
```

---

## Contribution Workflow

### 1. Find or Create an Issue

- Browse [existing issues](link-to-issues)
- Look for `good first issue` labels
- Check if issue is unassigned
- Comment to claim the issue

Or create a new issue:
- Describe the feature/bug clearly
- Provide examples
- Wait for approval before starting

### 2. Develop Your Changes

#### Feature Development

1. Create feature branch: `feature/feature-name`
2. Implement the feature
3. Add tests
4. Update documentation
5. Test thoroughly

#### Bug Fixes

1. Create bugfix branch: `bugfix/issue-number`
2. Write test that reproduces bug
3. Fix the bug
4. Verify test passes
5. Test for regressions

### 3. Testing Your Changes

```lua
-- Test in Mudlet
TorilLib:reload()

-- Run test suite (if available)
TorilLib.Tests:runAll()

-- Manual testing
-- 1. Connect to TorilMUD
-- 2. Test your feature
-- 3. Check for errors
-- 4. Verify functionality
```

### 4. Commit Your Changes

```bash
# Stage changes
git add .

# Commit with descriptive message
git commit -m "feat: add cooldown tracking to combat system

- Implemented cooldown timer
- Added visual indicators
- Updated combat UI
- Fixes #123"
```

#### Commit Message Format

```
type(scope): short description

Detailed explanation if needed

Fixes #issue_number
```

**Types:**
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Formatting
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance

**Examples:**
```
feat(combat): add damage meter
fix(map): correct pathfinding through water
docs(readme): update installation instructions
style(gui): reformat container code
refactor(character): simplify stat calculation
test(combat): add cooldown tests
chore(deps): update dependencies
```

### 5. Push and Create Pull Request

```bash
# Push to your fork
git push origin feature/your-feature-name

# Create pull request on GitHub
# - Descriptive title
# - Reference issue number
# - Explain changes
# - List testing done
```

#### Pull Request Template

```markdown
## Description
Brief description of changes

## Related Issue
Fixes #123

## Changes Made
- Added feature X
- Fixed bug Y
- Updated documentation

## Testing Done
- [ ] Manual testing in TorilMUD
- [ ] Unit tests added/passing
- [ ] No regressions found
- [ ] Documentation updated

## Screenshots (if applicable)
![Feature screenshot](url)

## Checklist
- [ ] Code follows style guidelines
- [ ] Comments added where needed
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] No console errors
- [ ] Tested in Mudlet
```

### 6. Code Review Process

1. Maintainer reviews PR
2. Address feedback if requested
3. Make changes in same branch
4. Push updates
5. Re-review
6. Merge when approved

---

## Testing

### Manual Testing Checklist

- [ ] Feature works as intended
- [ ] No Lua errors in console
- [ ] No performance issues
- [ ] Works with existing features
- [ ] Tested edge cases
- [ ] UI displays correctly
- [ ] Settings persist
- [ ] Help text is clear

### Writing Tests (Future)

```lua
-- Example test structure
TorilLib.Tests = TorilLib.Tests or {}

function TorilLib.Tests:testCooldownTracking()
    -- Setup
    local combat = TorilLib.Combat
    combat:reset()
    
    -- Action
    combat:usePower("Shield Bash")
    
    -- Assert
    assert(combat:isOnCooldown("Shield Bash"), 
           "Power should be on cooldown")
    
    -- Cleanup
    combat:reset()
end
```

---

## Documentation

### Code Documentation

```lua
--- Tracks a combat power cooldown
--- @param powerName string Name of the power
--- @param duration number Cooldown duration in seconds
--- @return boolean Success status
function Combat:trackCooldown(powerName, duration)
    -- Implementation
end
```

### User Documentation

When adding features, update:

1. **README.md** - If major feature
2. **Feature docs** - In `/docs/features/`
3. **Help text** - In-game help
4. **Examples** - Usage examples
5. **Changelog** - In CHANGELOG.md

### Documentation Style

- Use clear, simple language
- Provide examples
- Explain "why" not just "how"
- Include screenshots for UI
- Update table of contents
- Link to related docs

---

## Community

### Communication Channels

- **Discord**: Daily discussions, quick help
- **Forums**: Feature discussions, announcements
- **GitHub Issues**: Bug reports, feature requests
- **GitHub Discussions**: General questions, ideas

### Getting Help

- Check documentation first
- Search existing issues
- Ask in Discord for quick questions
- Create GitHub issue for bugs
- Be respectful and patient

### Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Provide constructive feedback
- Assume good intentions
- Focus on ideas, not people
- Help others learn

---

## Development Resources

### Mudlet API
- [Mudlet Manual](https://wiki.mudlet.org/w/Manual:Introduction)
- [Lua API](https://wiki.mudlet.org/w/Manual:Lua_Functions)

### Lua Resources
- [Lua Manual](https://www.lua.org/manual/5.1/)
- [Programming in Lua](https://www.lua.org/pil/)

### Project Resources
- [Architecture Overview](./docs/architecture.md)
- [Database Schema](./docs/database.md)
- [API Reference](./docs/api.md)

---

## Recognition

Contributors are recognized in:
- README.md Contributors section
- Release notes
- Discord contributor role
- Annual contributor showcase

Top contributors may be invited to:
- Maintainer team
- Beta testing
- Feature planning
- Community events

---

## Questions?

- Discord: [Join our server](#)
- Email: maintainers@torillib.com
- Issues: [GitHub Issues](#)

Thank you for contributing to TorilLib! 🎮

---

**Last Updated:** 2024-12-10  
**Maintainers:** [List of maintainers]
