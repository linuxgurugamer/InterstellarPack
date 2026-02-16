# LGG's Intersidereal Explorer Pack

Definition:  Intersidereal is a rare adjective meaning situated, occurring, or existing between or among the stars and constellations, synonymous with interstellar. Derived from the prefix inter- and the Latin sīdus (star), it describes the space, matter, or travel between stellar bodies. It was first documented in the mid-1600s.  Seemed to be a good name for this pack

This is a combination of CKAN files and patches to set up a KSP install to run an interstellar colonization game

This was inspired by a thread on the KSP forum:
    https://forum.kerbalspaceprogram.com/topic/229759-*

Installation



Step-by-step (CKAN GUI)

1. Launch CKAN
2. Make sure the correct KSP instance is selected:
    Settings → Manage game instances
    Verify it points at your KSP 1.12.5 install
3. From the menu:
    File → Import installed mods…
4. Browse to where you downloaded the CKAN file and select the file
5. CKAN will show a list of mods it plans to install
    This is a metapackage, so it’s normal to see many dependencies
6. Click Apply changes
7. Wait for CKAN to finish downloading and installing everything

At this point:

    Near Future stack is installed
    Blueshift is installed
    Planet packs, colonization mods are installed
    ModuleManager is installed

In CKAN, select the mod:  InterstellarPack and install it


Overview

BlueShift
Sterling
Life Support
    Snacks
    USI-LS
    IFI-LD
    TAC-LS

--------------------------------------------------------
Blueshift

1. Tech Tree Alignment (CTT Integration)
    What the patch does
    It:
        * Creates a new tech node: Warp Field Theory
        * Places it after:
            o experimentalElectrics
            o veryHeavyRocketry
        * Moves all Blueshift warp engines into that node
    What that means in gameplay
    Before the patch:
        * Warp might unlock too early relative to your Near Future reactor tier.
        * Small, mid-game craft might gain warp capability prematurely.
    After the patch:
        * You must already have:
            o Advanced electrical infrastructure
            o Large-scale reactors
        * Warp becomes explicitly late-game
    Practical Result
    Near Future propulsion remains relevant for:
        * Kerbin system expansion
        * Jool/Saturn analog missions
        * Colony staging
    Warp becomes:
        * A deliberate milestone
        * A strategic infrastructure leap
        * Not a shortcut to skip mid-game

2. Warp Power & Resource Tuning
    The tuning patch modifies several Blueshift parameters:

    A) Increased Graviolium Consumption
        gravioliumConsumptionRate *= X
        startupCost *= Y

        Effect:
            * Warp jumps consume significantly more exotic fuel
            * Jump spam is discouraged
            * Colonies must support Graviolium logistics
            * Long-range missions require planning
        Warp becomes:
            * Strategic
            * Expensive
            * Infrastructure-backed

    B) Minimum Warp Mass
        minimumWarpMass = (e.g., 150 or 300 tons)
        Effect:
            * Tiny probes can t warp efficiently
            *  FTL cubesats  are no longer viable
            * Proper interstellar vessels are encouraged
        This enforces:
            * Big ship design
            * Radiators
            * Reactors
            * Real spacecraft architecture

    C) Efficiency Curve Scaling
        efficiencyCurve
        {
            key = 100   0.15
            key = 300   0.35
            key = 800   0.65
            key = 1500  1.0
        }
        Effect:
            * Small ships warp inefficiently
            * Large ships warp efficiently
            * Capital-class vessels are rewarded
        This prevents:
            * Micro-warp abuse
            * Lightweight warp exploitation

    D) Minimum EC Requirement
        minimumECRequirement = 500000
        Effect:
            * Warp startup requires serious power
            * Solar-only ships cannot warp
            * Capacitors become necessary
            * Near Future reactors are mandatory
        This keeps:
            * Fusion/fission infrastructure relevant
            * Power system engineering meaningful

3. Crew Skill Integration
    The patch sets:
        warpEngineerSkill = Engineer
        warpSpeedSkillMultiplier = X
        warpSpeedBoostRank = Y
    What this does
    Warp performance scales with:
        * Engineer presence
        * Engineer experience level
    Practical effects:
        Without Engineers:
            * Warp is slower
            * Less efficient
            * Less forgiving
        With high-level Engineers:
            * Warp field stabilizes better
            * Travel speed improves
            * Fuel usage effectively decreases
    Design philosophy
    Warp is no longer:
        Just a part you slap on.
        It becomes:
        A complex system requiring trained crew.
        This reinforces:
            * Colony staffing
            * Crew rotation
            * Veteran kerbal value

4. Difficulty Toggle System
    You created three optional patches:
        * Easy
        * Normal
        * Hard
    Only one is active at a time.
    EASY
        * Lower fuel cost
        * Lower minimum mass
        * Strong crew bonuses
    Result:
        * Warp is accessible
        * Good for exploration-focused saves

    NORMAL
        * Balanced fuel usage
        * Moderate mass requirements
        * Moderate crew influence
    Result:
        * Warp is powerful but infrastructure-dependent

    HARD
        * High Graviolium burn
        * High startup cost
        * Large minimum mass
        * Reduced crew bonus impact
    Result:
        * Warp is endgame infrastructure
        * Logistics becomes gameplay
        * Colonies are required, not optional

    Big Picture: What the Blueshift Tuning Achieves
    Without tuning, warp tends to:
        * Flatten progression
        * Replace advanced propulsion
        * Trivialize star systems
    With tuning:
        * Near Future propulsion remains meaningful
        * Power infrastructure matters
        * Large vessels are rewarded
        * Crew skill is important
        * Colonies become strategic assets
        * Warp feels like a technological revolution

Instead of:

    “I unlocked warp.”

It becomes:

    “We built the infrastructure to bend spacetime.”

--------------------------------------------------------

Sterling

1. Electrics (Fuel Cells + Photovoltaics)
    What the patches change
    A) Fuel Cells
        * Increase input resource consumption (Oxygen + refined metals)
        * Enable Engineer specialist bonus
        * Slightly reduce baseline efficiency without crew
    What that means in-game
    Without the patch:
        * Sterling fuel cells can feel like clean, compact, semi-permanent power.
        * They may undercut other mid-tier infrastructure.
    With the patch:
        * Fuel cells still work very well…
        * …but they now cost more logistics per unit of EC
        * An Engineer improves efficiency noticeably
    Effectively:
        * Colonies need supply chains
        * Staffed colonies outperform unstaffed outposts
        * “Drop and forget” power becomes less optimal

    B) PhotoVoltaic
        * Moves them to a later solar tech tier
        * Slightly increases entry cost
    What that means
    Sterling PV becomes:
        * Late-tier high-density solar
        * A complement to Near Future Solar
        * Not an early-game “why build reactors?” replacement
    You preserve:
        * Solar ? Reactor ? Fusion ? Warp progression

2. Engine Packs (Fission, Thermal Nozzle, Fusion, Antimatter)
    These patches primarily adjust propellant ratios.
    They don’t reduce thrust.
    They don’t change Isp.
    They don’t nerf identity.
    They increase operational cost.

    A) Fission Engines
        * Slightly increase ThermalPower usage
        * Slightly increase Hydrogen usage (if present)
    Effect:
        * Still excellent mid/late engines
        * Require better reactor support
        * Less “infinite” endurance

    B) Thermal Nozzle
    Thermal nozzles in Sterling are intended as major propulsion systems once you can supply huge ThermalPower. The patch:
        * Increases ThermalPower consumption a bit more than fission
        * Slightly increases hydrogen usage
    Effect:
        * They remain powerful
        * They demand real power infrastructure
        * They don’t trivialize other engine families

    C) Fusion Engines
    Fusion is where the biggest tuning happens.
    The patch:
        * Increases FusionPellets burn
        * Slightly increases ThermalPower draw
        * Optionally increases cryogenic fusion fuels (Deuterium/He3)
    Effect:
        * Fusion remains elite
        * But pellet logistics matter
        * Colonies become meaningful fuel depots
    Fusion becomes:
        Powerful but not infinite

    D) Antimatter Engines
    Antimatter is endgame. The patch:
        * Increases Antimatter consumption
        * Slightly increases ThermalPower draw
    Effect:
        * Antimatter becomes rare-strategic propulsion
        * Not “press button to win”
    It enforces:
        * Mining or production chains
        * Infrastructure dependency

3. Engineer Skill Integration
    For Electrics (fuel cells):
        * Uses stock ModuleResourceConverter specialist bonus
        * Engineer skill improves efficiency
        * Higher-level engineers reduce effective fuel burn
    For Fusion engines (via optional optimizer module):
        * Adds a tiny “fuel optimization” converter
        * High-level Engineers recover a small fraction of expensive fuel
    What this means:
    Colonies that are staffed:
        * Use less fuel
        * Perform better
        * Feel alive
    Empty infrastructure:
        * Works
        * But is inefficient
    This supports:
        * Crew rotation
        * Veteran kerbal value
        * Colony population mechanics

4. CTT Flavor & Progression Shaping
    The flavor patches:
        * Reframe Sterling power as ThermalPower-centric infrastructure
        * Emphasize heat rejection & engineering
        * Bridge Sterling ? Warp narrative
    Mechanically:
        * Adjust some tech placements
        * Raise entry costs modestly
    Philosophically:
        * Sterling becomes a stepping stone to warp
        * Not a parallel tech tree that bypasses it

5. Difficulty Toggle Behavior
    The difficulty patches scale three things:
    EASY
        * Lower fuel costs
        * Strong Engineer bonuses
        * Fusion & antimatter burn reduced
    Result:
        * Colonization-focused gameplay
        * Logistics forgiving
        * Power is fun, not work

    NORMAL
        * Baseline tuning
        * Balanced fuel multipliers
        * Moderate Engineer benefit
    Result:
        * Strategic but not punishing
        * Fusion feels advanced
        * Antimatter feels rare

    HARD
        * Increased fuel burn across engines
        * Reduced Engineer benefit
        * Higher ThermalPower demand
    Result:
        * Logistics becomes gameplay
        * Fusion/AM require real infrastructure
        * Colonies are mandatory, not optional

6. Overall Gameplay Impact
    With the Sterling patches active:
    Power Systems
        * Fuel cells are good but not free
        * PV is strong but late-tier
        * ThermalPower becomes meaningful infrastructure
    Engines
        * Fission = reliable mid-late
        * Thermal nozzle = power-hungry workhorse
        * Fusion = elite but logistically expensive
        * Antimatter = strategic apex
    Crew
        * Engineers matter
        * Staffing colonies improves performance
        * High-level kerbals become valuable assets

Progression
    You preserve this arc:
    Solar -> Fission -> Thermal -> Fusion -> Antimatter -> Warp
    Nothing skips ahead.
    Nothing becomes trivial.

--------------------------------------------------------

Life Support


Life Support Mods the Controller Touches
1. Snacks!
    Snacks!
    What gets patched:
        * Any ModuleResourceConverter that outputs Snacks
        * The patch scales the INPUT_RESOURCE ratios
    Effect:
        * Easy -> greenhouses/recyclers need fewer inputs
        * Hard -> greenhouses/recyclers need more inputs
        * Per-kerbal consumption rate is NOT changed

    2. USI Life Support
    USI Life Support
    What gets patched:
        * Converters producing Supplies
        * Input resources to those converters are scaled
    Effect:
        * Easy -> recycling loop more efficient
        * Hard -> recycling loop less efficient
        * The actual Supplies-per-kerbal-per-day setting is NOT modified

3. IFI Life Support
    IFI Life Support
    What gets patched:
        * Converters producing LifeSupport
        * Input ratios scaled
    Effect:
        * Easy -> slurry/sludge recycling more forgiving
        * Hard -> closed-loop more demanding
        * Base life-support drain is untouched

4. TAC Life Support
    TAC Life Support
    What gets patched:
        * Converters that output Oxygen or Water
        * Input resource ratios scaled
    Effect:
        * Easy -> recyclers more efficient
        * Hard -> recyclers less efficient
        * Per-kerbal Food/Water/O2 drain unchanged

What the Controller Does NOT Touch
    It does NOT modify:
        * Kerbal consumption rates per day
        * Plugin-level difficulty settings
        * Habitation timers
        * Stress mechanics (USI)
        * Kerbalism (not included at all)
    The controller only adjusts converter efficiency, because:
        1. That s reliably patchable with ModuleManager.
        2. LS plugins usually store per-kerbal drain in plugin config files.
        3. Converter efficiency is the safest global difficulty lever.

Important Clarification
    If you have none of these LS mods installed:
    The life-support sections do nothing.
    They are gated with :NEEDS[ModName].
    If you have multiple LS mods installed (not recommended, but possible):
        The controller will patch all of them.

Summary Table   

Mod         Touched?    What Changes    
Snacks      Yes         Greenhouse/recycler efficiency
USI-LS      Yes         Supplies conversion efficiency
IFI-LS      Yes         LifeSupport recycling efficiency
TAC-LS      Yes         O2/Water recycling efficiency
Kerbalism   No          Not included
Stock       No          No effect
