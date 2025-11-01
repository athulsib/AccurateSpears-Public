# Accurate Spears - Complete Plugin Documentation for Server Owners

> **Accurate Spears** is a comprehensive, feature-complete backport of Minecraft 1.21's spear combat system for Paper/Spigot servers. Experience authentic spear mechanics with full velocity-based damage, multi-stage charge attacks, and a complete progression system from Wood to Netherite.

---

## 🎯 Quick Overview

**Accurate Spears** brings the upcoming Minecraft spear combat system to your server today. Every mechanic, from charge attack stages to velocity-based damage, has been carefully implemented to match or exceed the official implementation.

### Key Highlights
- ✅ **7 Tier Progression** - Wood → Stone → Copper → Iron → Golden → Diamond → Netherite
- ✅ **Triple Attack System** - Jab (left-click), Thrust (right-click), Charge (hold right-click)
- ✅ **Velocity-Based Damage** - Charge attacks scale with movement speed
- ✅ **Multi-Stage Charge System** - Engaged (100%) → Tired (70%) → Disengaged (30%)
- ✅ **Lunge Enchantment** - 3-level custom enchantment system
- ✅ **⚙️ Extremely Detailed Configuration** - **One of the most comprehensive config systems available**: Per-attack-type animations, granular cooldowns, per-spear stats, tooltip customization, enchantment settings, and more
- ✅ **Performance Optimized** - Built for high-performance servers
- ✅ **Complete Resource Pack** - Professional animations and models

---

## 📦 Installation

### Requirements
- **Server**: Paper or Spigot 1.21+
- **Players**: Minecraft 1.21+ client
- **Resource Pack**: Required for visual models and animations

### Setup Steps

1. **Install the Plugin**
   - Download `AccurateSpears.jar` from your source
   - Place it in your server's `plugins/` folder
   - Restart your server

2. **Configure Settings**
   - Edit `plugins/AccurateSpears/config.yml`
   - Customize cooldowns, tooltips, animations (see Configuration section)
   - Run `/spear reload` to apply changes

3. **Resource Pack Setup**
   - Download the `AccurateSpearsPack.zip` resource pack
   - Configure your server to automatically prompt players for the pack
   - Or provide download link in `server.properties` (`resource-pack` option)

4. **Verify Installation**
   - Check console for green startup message: `▐ ᴀᴄᴄᴜʀᴀᴛᴇ sᴘᴇᴀʀs`
   - Test crafting: `/spear give wooden`
   - Test commands: `/spear list`

---

## ⚔️ Core Combat Features

### Attack Types

#### 🔸 Jab Attack (Left-Click)
- **Standard melee attack** with 2-4.5 block reach
- Damage = base spear damage + enchantment bonuses
- Applies knockback
- **Force cooldown** prevents spam (configurable)
- Consumes 1 durability
- **Cannot be used while charging**

#### 🔸 Thrust Attack (Right-Click, Single)
- **Extended reach attack** up to 4.5 blocks
- 20% damage boost over jab
- Particle and sound feedback
- Consumes 2 durability
- Can interrupt charge attacks

#### 🔸 Charge Attack (Hold Right-Click)
- **Hold to charge** - release to attack
- **Activation delay** varies by tier (0.4-0.75s)
- **Velocity-based damage** - scales with movement speed
- **Multi-entity hit** - can strike multiple targets (once each per charge)
- **3-stage system**:
  - **Engaged**: 100% damage, full knockback, dismounts riders
  - **Tired**: 70% damage/knockback, no dismount
  - **Disengaged**: 30% damage, no knockback/dismount
- Consumes 3 durability
- **Blocks jabs while active** - prevents interruption

### Advanced Mechanics

#### Velocity-Based Damage System
- Charge attack damage scales with **relative velocity** between attacker and target
- Fast-moving charges deal significantly more damage
- Formula: `damage = charge_multiplier × relative_velocity × base_damage`
- All spears have **speed requirements** (4.6 b/s for damage, 5.1 b/s for knockback) (can be fully configured)

#### Raycast Collision Detection
- **Accurate hit detection** using multi-stage raycasting
- Solid blocks block attacks (walls, stone, etc.)
- Non-solid blocks allow attacks (grass, cobweb, etc.)
- Prevents "wall hacks" and ensures fair combat

#### Multi-Entity System
- Charge attacks can hit **multiple targets** in one swing
- Each entity can only be hit **once per charge**
- Entities hit become **exempt from raycasts** for 2 seconds
- Perfect for crowd control and area damage

#### Force Cooldown System
- **Shield-like cooldown** prevents attack spam
- Configurable per-attack-type (jab/charge)
- Scales with attack speed (optional)
- Players see cooldown meter in HUD

---

## 🗡️ Spear Types & Stats

| Spear Type | Attack Damage | Attack Speed | DPS  | Durability | Enchantability | Charge Multiplier | Activation Delay |
|------------|--------------|--------------|------|------------|----------------|-------------------|------------------|
| **Wooden** | 1.0          | 1.54         | 1.54 | 59         | 15             | 0.7x              | 0.75s            |
| **Stone**  | 2.0          | 1.33         | 2.66 | 131        | 5              | 0.82x             | 0.7s             |
| **Copper** | 2.0          | 1.18         | 2.36 | 190        | 13             | 0.82x             | 0.65s            |
| **Iron**   | 3.0          | 1.05         | 3.15 | 250        | 14             | 0.95x             | 0.6s             |
| **Golden** | 1.0          | 1.05         | 1.05 | 32         | 22             | 0.7x              | 0.7s             |
| **Diamond**| 4.0          | 0.95         | 3.8  | 1561       | 10             | 1.075x            | 0.5s             |
| **Netherite**| 5.0       | 0.87         | 4.35 | 2031       | 15             | 1.2x              | 0.4s             |

### Crafting Recipes
All spears follow the same pattern:
```
[ M ]  ← Material (varies by tier)
[ S ]  ← Stick
[ S ]  ← Stick
```

**Materials:**
- Wooden: Oak Planks
- Stone: Cobblestone
- Copper: Copper Ingot
- Iron: Iron Ingot
- Golden: Gold Ingot
- Diamond: Diamond
- Netherite: Netherite Ingot

---

## ✨ Special Features

### 🎣 Lunge Enchantment
- **Custom 3-level enchantment** exclusive to spears
- Adds horizontal momentum boost on left-click
- **Level I**: Base momentum (configurable)
- **Level II**: +50% momentum
- **Level III**: +100% momentum
- **Midair bonus**: 1.5x multiplier when lunging in air
- Requires hunger (minimum 6 food points)
- Cannot be used while charging
- Adds **enchantment glint** to spears

### 💎 Durability System
- **Realistic wear** - each attack consumes durability
- **Repair system** - use materials to repair (same as crafting)
- **Visual feedback** - durability shown in tooltip (configurable)
- **Break protection** - spears become unusable at 0 durability

### 🎨 Visual & Audio Feedback
- **Multi-stage animations** - different models for charge stages
- **Particle effects** - configurable per attack type
- **Sound effects** - immersive audio feedback
- **Boss bar indicators** - optional charge progress/damage display
- **Resource pack animations** - smooth transitions between states

### ⚙️ Item Attributes
- **Native Minecraft attributes** - attack damage/speed show as item attributes
- **Vanilla-style tooltips** - optional detailed tooltips
- **Configurable display** - choose between minimal and detailed formats
- **Unstackable** - each spear has unique NBT (prevents stacking)

---

## 🔧 **Comprehensive Configuration System** ⭐

> **Accurate Spears features one of the most detailed and granular configuration systems available for a Minecraft combat plugin.** Every single mechanic, visual effect, combat parameter, and display option is fully customizable. The `config.yml` file is extensively documented with inline comments explaining every option, making it easy for server owners to fine-tune the plugin to match their server's exact needs. **With nearly 400 Lines of configuration**
>
> **From per-attack-type animation settings to granular cooldown scaling, per-spear statistics to tooltip customization - you have complete control.**

---

### Why Our Configuration Stands Out

- **📋 Inline Documentation**: Every config option includes comments explaining purpose and usage
- **🎯 Granular Control**: Configure individual particle counts, sound volumes, attack speeds per tier
- **🔄 Hot Reload**: All changes apply without server restart via `/spear reload`
- **📊 Comprehensive Coverage**: Combat, visuals, tooltips, enchantments, timing - everything is configurable
- **⚙️ Production Ready**: Balanced defaults provided, but full customization available

### ⚙️ Configuration Overview

**The plugin's `config.yml` is one of the most detailed and well-documented configuration files available.** Every single option includes inline comments explaining its purpose and usage. The configuration system provides **granular control** over:

**Comprehensive configuration categories:**

- **🎯 Combat Mechanics** - Cooldowns, speed requirements, hit tracking
- **📊 Per-Spear Statistics** - Damage, speed, durability, charge multipliers for each tier
- **🎨 Visual & Audio Effects** - Particle types, counts, offsets, sound types, volumes, pitches
- **📝 Tooltip Customization** - Vanilla vs detailed formats, optional information display
- **⏱️ Attack Timing** - Charge activation delays, stage durations
- **🎣 Enchantment Settings** - Lunge momentum, exhaustion, hunger requirements
- **📊 Feedback Systems** - Boss bars, debug mode, animation toggles

---

### 🎯 Combat Configuration

#### Force Cooldown System
**Granular control over attack cooldowns with multiple scaling options:**

```yaml
cooldown:
    jab:
        base_ticks: 20                    # Base cooldown (1 second)
        min_ticks: 10                     # Minimum (fastest spears)
        max_ticks: 30                     # Maximum (slowest spears)
        scale_with_attack_speed: true     # Enable attack speed scaling
        attack_speed_multiplier: 1.0      # Scaling intensity
    
    charge:
        base_ticks: 20                    # Independent charge cooldown
        min_ticks: 10
        max_ticks: 30
        scale_with_attack_speed: true
        attack_speed_multiplier: 1.0
```

**Formula**: `cooldown = clamp(base + (attackSpeed - 1.0) × multiplier × 10, min, max)`

#### Speed Requirement Enforcement
```yaml
enforce_damage_speed_requirement: true       # Copper spears: require 4.6 b/s for damage
enforce_knockback_speed_requirement: true    # Copper spears: require 5.1 b/s for knockback
```

#### Debug & Testing
```yaml
debug_mode: false  # Enable verbose debug messages with velocity calculations, hit tracking, etc.
```

---

### 📝 Tooltip & Display Configuration

**Complete control over how spears appear in inventory:**

```yaml
tooltip:
    format: vanilla  # "vanilla" (minimal, native attributes) or "detailed" (full lore)
    
    # Detailed format options (only applies when format: detailed)
    show_dps: false              # Show damage per second calculation
    show_durability: false       # Display durability in lore
    show_enchantability: false   # Show enchantability stat
    show_attack_reach: false     # Display reach range (2-4.5 blocks)
    show_charge_info: false     # Show charge attack details
    show_attack_types: false     # Display attack type descriptions
```

**Vanilla Format**: Attack damage and speed appear as native Minecraft item attributes (green text, like vanilla weapons)

**Detailed Format**: Full lore with configurable additional information

---

### 🎨 Animation & Effect Configuration

**Per-attack-type, per-effect granular control:**

The animation system is **incredibly detailed** - you can configure:
- **Global toggles**: Enable/disable all animations, particles, or sounds
- **Per-attack-type settings**: Separate config for jab, thrust, charge start, charge stage 1/2/3, charge impact, charge release
- **Per-effect control**: Individual particle types, counts, offsets, sound types, volumes, pitches

#### Example: Jab Attack Configuration
```yaml
jab_attack:
    enabled: true
    particles:
        enabled: true
        sweep_attack:
            enabled: true
            type: SWEEP_ATTACK
            count: 1
        crit:
            enabled: true
            type: CRIT
            count: 3
            offset: 0.3
    sounds:
        enabled: true
        attack_sweep:
            enabled: true
            type: ENTITY_PLAYER_ATTACK_SWEEP
            volume: 1.0
            pitch: 1.2
        attack_strong:
            enabled: true
            type: ENTITY_PLAYER_ATTACK_STRONG
            volume: 0.8
            pitch: 1.0
```

**Available attack types with full configuration**:
- `jab_attack` - Left-click attacks
- `thrust_attack` - Right-click single tap
- `charge_start` - Charge initiation
- `charge_stage1` - Engaged stage effects
- `charge_stage2` - Tired stage effects
- `charge_stage3` - Disengaged stage effects
- `charge_impact_stage1/2/3` - Impact effects per stage
- `charge_release` - Charge release effects

**Each includes**: Particles (type, count, offset) and Sounds (type, volume, pitch)

---

### 📊 Per-Spear-Type Statistics

**Fully customizable stats for each spear tier:**

```yaml
types:
    WOODEN:
        attack_damage: 1.0
        attack_speed: 1.54
        base_material: WOODEN_SWORD
        durability: 59
        enchantability: 15
        charge_damage_multiplier: 0.7
        activation_delay: 0.75
        total_charge_duration: 15.0
        stage1_duration: 5.0
        stage2_duration: 1.0
        stage3_duration: 9.0
        dismount_speed_requirement: 14.0
        knockback_speed_requirement: 5.1
        damage_speed_requirement: 4.6
    # ... same for all 7 tiers
```

**Configurable per tier**:
- Base attack damage and speed
- Durability and enchantability
- Charge damage multiplier
- Charge activation delay
- Stage durations (total, stage 1, stage 2, stage 3)
- Speed requirements (dismount, knockback, damage)

---

### 🎣 Lunge Enchantment Configuration

**Complete control over the custom enchantment system:**

```yaml
lunge:
    enabled: true
    base_momentum: 0.458              # Horizontal momentum per level
    vertical_y_boost: 0.0              # Optional vertical boost
    exhaustion_base: 8.0               # Base exhaustion cost
    exhaustion_per_level: 4.0          # Additional exhaustion per level
    min_hunger_required: 6             # Minimum food points needed
    allow_on_mount: false              # Can use while mounted
    allow_gliding: false                # Can use while gliding
    allow_in_water: false              # Can use in water
    midair_bonus_enabled: true         # Enable midair multiplier
    midair_bonus_multiplier: 1.5       # Midair bonus strength
    play_sound: true                    # Sound feedback
    sound: ITEM_TRIDENT_THROW          # Sound type
    play_particles: true                # Particle feedback
    cooldown_ticks: 20                 # Lunge cooldown
```

---

### 📊 Boss Bar Feedback

**Optional visual indicators for charge progress:**

```yaml
bossbars:
    show_charge_bar: true    # Show progress bar during charge
    show_damage_bar: true     # Show damage dealt with charge attacks
```

---

### 🔄 Reloading Configuration

All configuration changes can be applied **without server restart**:

```bash
/spear reload
```

This reloads:
- All cooldown settings
- Animation configurations
- Tooltip formats
- Per-spear statistics
- Lunge enchantment settings
- Debug mode
- Speed requirement enforcement

---

### 💡 Configuration Tips

1. **Start with defaults**: The plugin comes with balanced defaults for all settings
2. **Use debug mode**: Enable `debug_mode: true` to see detailed combat calculations
3. **Per-spear fine-tuning**: Adjust individual spear stats to balance your server's economy
4. **Animation performance**: Disable particles/sounds if experiencing lag on lower-end servers
5. **Tooltip format**: Use "vanilla" for cleaner UI, "detailed" for informative displays

---

### 📋 Configuration Checklist

**Combat Balance**:
- [ ] Adjust cooldown base/min/max values
- [ ] Enable/disable speed requirement enforcement
- [ ] Tune per-spear damage/speed multipliers
- [ ] Configure charge stage durations

**Visual Customization**:
- [ ] Choose tooltip format (vanilla/detailed)
- [ ] Configure animation particles and sounds
- [ ] Enable/disable boss bar indicators
- [ ] Adjust per-attack-type visual effects

**Enchantment System**:
- [ ] Configure Lunge momentum values
- [ ] Set exhaustion and hunger requirements
- [ ] Adjust midair bonus multiplier
- [ ] Configure environment restrictions

**Performance**:
- [ ] Disable animations if needed
- [ ] Disable debug mode in production
- [ ] Adjust particle counts for lower-end servers

---

## 📜 Commands

| Command | Description | Permission | Default |
|---------|-------------|------------|---------|
| `/spear` | Shows help menu with all features | `spear.use` | true |
| `/spear give <type> [amount]` | Give spears to yourself | `spear.give` | op |
| `/spear list` | List all spear types and stats | `spear.list` | true |
| `/spear info` | View held spear information | `spear.info` | true |
| `/spear lunge <level\|remove>` | Add/remove Lunge enchantment | `spear.lunge` | op |
| `/spear reload` | Reload plugin configuration | `spear.reload` | op |

### Command Examples
```
/spear give diamond 3
/spear list
/spear info
/spear lunge 2
/spear lunge remove
/spear reload
```

---

## 🔐 Permissions

| Permission Node | Description | Default |
|-----------------|-------------|---------|
| `spear.use` | Use basic spear commands | true |
| `spear.give` | Give spears to players | op |
| `spear.list` | List available spear types | true |
| `spear.info` | View spear information | true |
| `spear.reload` | Reload plugin configuration | op |
| `spear.craft` | Craft spears using recipes | true |
| `spear.lunge` | Add/remove Lunge enchantment | op |

---

## 🎮 Player Guide

### Getting Started
1. **Craft your first spear**: Use the recipe (Material + 2 Sticks)
2. **Understand attack types**:
   - **Left-click**: Jab attack (standard melee)
   - **Right-click (tap)**: Thrust attack (extended reach)
   - **Right-click (hold)**: Charge attack (velocity-based)
3. **Learn charge stages**: Watch for visual/audio cues indicating stage
4. **Experiment with movement**: Fast charges deal more damage
5. **Try the Lunge enchantment**: Adds mobility to combat

### Combat Tips
- **Use charge attacks for crowd control** - can hit multiple enemies
- **Movement matters** - sprinting while charging increases damage
- **Manage durability** - repair spears before they break
- **Copper spears** require speed - must be moving fast for full effect
- **Stage timing** - release charge during "Engaged" stage for maximum damage

---

## 🔌 API & Integration

### Events
- **SpearKillEvent**: Fired when a spear attack kills an entity
  - Provides full damage breakdown
  - Enchantment information
  - Attack type (Jab/Charge/Lunge)
  - Charge stage information

### Example Integration
```java
@EventHandler
public void onSpearKill(SpearKillEvent event) {
    Player killer = event.getAttacker();
    LivingEntity victim = event.getVictim();
    double damage = event.getActualDamage();
    
    // Your custom logic here
    killer.sendMessage("You killed " + victim.getName() + " with " + damage + " damage!");
}
```

---

## 🛠️ Technical Details

### Performance Optimizations
- **Velocity updates**: Only tracked for actively charging players
- **Raycast throttling**: Runs every 2 ticks (10 times/second) instead of every tick
- **Debug mode**: Can be disabled to reduce console output
- **Config caching**: Reduces repeated file reads
- **Efficient hit tracking**: Uses UUID-based maps for O(1) lookups

### Compatibility
- **Server**: Paper 1.21+ recommended (Spigot 1.21+ supported)
- **Client**: Minecraft 1.21+ required
- **Resource Pack**: Required for proper visuals
- **No coremods**: 100% plugin-based, no server modifications

### Anti-Exploit Features
- **PrePlayerAttackEntityEvent**: Cancels attacks before swing animation
- **Raycast exemptions**: Prevents rapid re-hits
- **Force cooldowns**: Prevents attack spam
- **Block collision**: Prevents wall-hacking
- **Velocity validation**: Accurate speed calculations

---

## ❓ Frequently Asked Questions

### Q: Do players need the resource pack?
**A:** Yes, the resource pack is required for proper spear models and animations. Configure it to auto-download for best experience.

### Q: Can I disable certain attack types?
**A:** Not directly, but you can set very long cooldowns to effectively disable them. Future versions may add toggle options.

### Q: How do I customize spear stats?
**A:** Edit `plugins/AccurateSpears/config.yml` under the `types` section. Reload with `/spear reload`.

### Q: Are spears compatible with other combat plugins?
**A:** Generally yes, but conflicts may occur with plugins that modify attack damage/events. Test in development environment first.

### Q: Can spears stack?
**A:** No, each spear has unique NBT data to prevent stacking. This ensures accurate durability tracking.

### Q: How do charge attacks work with multiple enemies?
**A:** Charge attacks can hit multiple entities, but each entity can only be hit once per charge. Entities become exempt from raycasts for 2 seconds after being hit.

---

## 📞 Support & Resources

- **Documentation**: See `/docs/` directory for detailed mechanics
- **Configuration**: All options explained in `config.yml`
- **Commands**: Run `/spear` in-game for help menu
- **Debug Mode**: Enable `debug_mode: true` in config for troubleshooting

---

## 📝 Version Information

- **Current Version**: v2.0-SNAPSHOT
- **Minecraft Version**: 1.21+
- **API Version**: 1.21
- **Author**: Athulsib

---

**Thank you for using Accurate Spears!** 🗡️✨

For detailed technical documentation, API references, and development guides, see the `/docs/` directory.

