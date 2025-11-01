# Accurate Spears - Documentation Index

**DISCLAIMER: This is a partial documentation, you will receive a complete documentation of the plugin, its features and API on purchase.**
**Contact: @athulsib on discord for purchase**

Welcome to the comprehensive documentation for **Accurate Spears**! This is your central hub for all plugin information, from quick-start guides to deep technical references.

---

## 🚀 Quick Start

**New Server Owners?** → Start with the **[Plugin Page](./PLUGIN_PAGE.md)** - Complete installation and setup guide designed for server administrators.

**Looking for specific mechanics?** → Use the index below to jump to detailed sections.

---

## 📚 Documentation Index

### 🌟 Essential Guides

- **[Plugin Page for Server Owners](./PLUGIN_PAGE.md)** ⭐ **START HERE**
  - Complete installation guide
  - All features explained for server administrators
  - Configuration examples
  - Player guides
  - FAQ and troubleshooting
  - Perfect for sharing with server owners

- **[Spear Types, Stats & Crafting](./SpearTypes.md)**
  - All 7 spear variants (Wood → Netherite)
  - Complete statistics table
  - Crafting recipes
  - Material requirements

- **[Combat Mechanics](./Combat.md)**
  - Core spear fighting system
  - Reach and collision detection
  - Multi-entity hit system
  - Velocity tracking
  - Anti-exploit protections
  - Performance optimizations

- **[Attacks: Jab, Thrust, Charge](./Attacks.md)**
  - Detailed attack type mechanics
  - Charge attack stages (Engaged/Tired/Disengaged)
  - Velocity-based damage system
  - Multi-entity hits
  - Attack comparison table

### 📖 Detailed References

- **[Commands & Permissions](./Commands.md)**
  - Complete command reference
  - Permission node explanations
  - Tab completion guide
  - Troubleshooting tips

- **[Durability, Repair, and Enchanting](./Durability.md)**
  - How wear and repair work
  - Enchantment system
  - Durability consumption rates

- **[Velocity-Based Damage](./VelocityDamage.md)**
  - In-depth velocity calculation formulas
  - Charge multiplier system
  - Copper spear speed requirements
  - Relative velocity mechanics

- **[Resource Pack & Animations](./ResourcePack.md)**
  - File layouts and structure
  - CustomModelData system
  - Model/animation mapping
  - Texture and pack authoring guide

- **[API & Events](./API.md)**
  - SpearKillEvent integration
  - Developer API reference
  - Event hooks and examples
  - Plugin integration guide

- **[Technical Differences & Implementation](./TechnicalDiffs.md)**
  - Plugin-specific implementations
  - Vanilla parity details
  - Technical workarounds
  - Performance considerations

---

## 🌟 Who Should Use This?

### 👥 Server Owners & Administrators
**Start here**: [Plugin Page](./PLUGIN_PAGE.md)

You'll find:
- Step-by-step installation
- Configuration guides
- Player instructions
- FAQ and troubleshooting
- Permission setup examples

### 🎮 Players
**Relevant sections**:
- [Spear Types](./SpearTypes.md) - What spears exist and how to craft them
- [Attacks](./Attacks.md) - How to use each attack type
- [Combat Mechanics](./Combat.md) - Understanding reach and hit detection
- [Commands](./Commands.md) - Available commands

### 🎨 Resource Pack Artists
**Relevant sections**:
- [Resource Pack & Animations](./ResourcePack.md) - Complete pack structure guide
- [Spear Types](./SpearTypes.md) - Model requirements per tier

### 👨‍💻 Developers & Plugin Authors
**Relevant sections**:
- [API & Events](./API.md) - Integration guide and event hooks
- [Technical Differences](./TechnicalDiffs.md) - Implementation details
- [Combat Mechanics](./Combat.md) - System architecture
- [Velocity Damage](./VelocityDamage.md) - Damage calculation formulas

---

## 🔍 Quick Reference

### Attack Types
| Type | Activation | Damage | Reach | Durability |
|------|------------|--------|-------|------------|
| **Jab** | Left-click | Base + enchants | 2-4.5 blocks | 1 |
| **Thrust** | Right-click (tap) | Base × 1.2 | 4.5 blocks | 2 |
| **Charge** | Right-click (hold) | Velocity-based | 2-4.5 blocks | 3 |

### Charge Stages
- **Engaged** (Stage 1): 100% damage, full knockback, dismounts
- **Tired** (Stage 2): 70% damage/knockback, no dismount
- **Disengaged** (Stage 3): 30% damage, no knockback/dismount

### Spear Tiers
Wooden → Stone → Copper → Iron → Golden → Diamond → Netherite

---

## 📝 Recent Updates

### Current Version: v2.0-SNAPSHOT

**Latest Features**:
- ✅ Force cooldown system (shield-like, configurable)
- ✅ PrePlayerAttackEntityEvent integration (prevents jab while charging)
- ✅ Raycast exemptions (2-second protection after hits)
- ✅ Velocity tracking for all entities (players and mobs)
- ✅ Configurable tooltips (vanilla/detailed formats)
- ✅ Attack damage/speed as native item attributes
- ✅ Unstackable spears (unique NBT)
- ✅ Performance optimizations (velocity updates, raycast throttling)
- ✅ Debug mode toggle
- ✅ Boss bar feedback options

**Mechanics**:
- Single hit per charge (no double-hits)
- Cannot lunge while charging
- Cannot jab while charging
- Entity velocity tracking (overcomes getVelocity() limitations)

---

## 🛠️ **Extremely Detailed Configuration System**

**Accurate Spears features one of the most comprehensive configuration systems available.**

### Configuration Categories

#### 🎯 Combat Mechanics
- **Force Cooldown System**: Separate jab/charge cooldowns with base/min/max values, attack speed scaling multipliers
- **Per-Spear Statistics**: Every tier's damage, speed, durability, charge multipliers, activation delays, stage durations
- **Speed Requirements**: Configurable enforcement for copper spear damage/knockback requirements
- **Hit Tracking**: Raycast exemptions, single-hit-per-charge enforcement

#### 🎨 Visual & Audio Effects
- **Per-Attack-Type Configuration**: 
  - Jab Attack, Thrust Attack, Charge Start, Charge Stages 1/2/3, Charge Impact, Charge Release
- **Per-Effect Control**: Particle types, counts, offsets, sound types, volumes, pitches for each effect
- **Global Toggles**: Enable/disable all animations, particles, or sounds
- **Boss Bar Indicators**: Optional charge progress and damage feedback

#### 📝 Display & UI
- **Tooltip Formats**: Vanilla (native attributes) or detailed (full lore)
- **Optional Information**: Toggle display of DPS, durability, enchantability, reach, charge info, attack types
- **Item Attributes**: Native Minecraft attribute display (green text like vanilla weapons)

#### 🎣 Enchantment System
- **Lunge Configuration**: Momentum, exhaustion costs, hunger requirements, environment restrictions, midair bonus
- **Cooldown Settings**: Per-enchantment cooldown configuration

#### 🐛 Debug & Testing
- **Debug Mode**: Verbose logging with velocity calculations, hit tracking, raycast information

### Configuration Examples

**Combat Cooldowns**:
```yaml
cooldown:
    jab:
        base_ticks: 20
        min_ticks: 10
        max_ticks: 30
        scale_with_attack_speed: true
        attack_speed_multiplier: 1.0
```

**Per-Attack Animation**:
```yaml
jab_attack:
    particles:
        sweep_attack: {type: SWEEP_ATTACK, count: 1}
        crit: {type: CRIT, count: 3, offset: 0.3}
    sounds:
        attack_sweep: {type: ENTITY_PLAYER_ATTACK_SWEEP, volume: 1.0, pitch: 1.2}
```

**Per-Spear Stats**:
```yaml
types:
    DIAMOND:
        attack_damage: 4.0
        attack_speed: 0.95
        charge_damage_multiplier: 1.075
        activation_delay: 0.5
        stage1_duration: 3.0
        # ... and more
```

**See [Plugin Page - Configuration](./PLUGIN_PAGE.md#-comprehensive-configuration-system) for complete, detailed configuration guide.**

---

## 💡 Tips for Navigation

- **Looking for installation?** → [Plugin Page](./PLUGIN_PAGE.md)
- **Understanding attack mechanics?** → [Attacks](./Attacks.md)
- **Configuring the plugin?** → [Plugin Page](./PLUGIN_PAGE.md) - Configuration section
- **Integrating with other plugins?** → [API & Events](./API.md)
- **Creating resource packs?** → [Resource Pack](./ResourcePack.md)
- **Understanding technical details?** → [Technical Differences](./TechnicalDiffs.md)

---

## 📞 Support

If you have questions not covered in these docs:
1. Check the [FAQ in Plugin Page](./PLUGIN_PAGE.md#frequently-asked-questions)
2. Review [Troubleshooting sections](./PLUGIN_PAGE.md#troubleshooting)
3. Enable `debug_mode: true` in config for verbose logging
4. Check console for error messages

---

**All documentation is kept up-to-date with the latest plugin version. For the most current information, always refer to the documentation files in this directory.**

---

*Last Updated: v2.0-SNAPSHOT | Minecraft 1.21+ | Paper/Spigot Compatible*
