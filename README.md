# InterstellarPack

This is a combination of CKAN files and patches to set up a KSP install to run an interstellar colonization game


Installation


Download the CKAN file for the life support mod you want to use:

    InterstellarColonization-NF-Blueshift-Snacks.ckan
    InterstellarColonization-NF-Blueshift-USI-LS.ckan
    InterstellarColonization-NF-Blueshift-IFI-LS.ckan
    InterstellarColonization-NF-Blueshift-TAC-LS.ckan


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
    Planet packs, colonization mods, life support are installed
    ModuleManager is installed

In CKAN, select the mod:  InterstellarPack and install it



Sterling
Adds flavor text that explicitly bridges Sterling power → late-game field/warp tech, and also reinforces Sterling’s ThermalPower model.
Sterling fuel cells (per Sterling docs) run on Oxygen + distilled metals such as Aluminium/Silicon/Beryllium.
    Increases “fuel cost” (input consumption)
    Adds Engineer specialist bonus (better efficiency with higher-level Engineers)

Solar has no “fuel,” so the knobs are:
    Tech placement (late solar)
    Output scaling via difficulty toggles (optional; see Extras)
    (Engineer skill doesn’t naturally apply to stock solar modules without a plugin, so I’m not faking it.)

Sterling fission/thermal engines heavily leverage ThermalPower as the main energy flow, and reactors are described as exceptionally fuel efficient.
This patch increases the “energy appetite” slightly so they don’t eclipse Near Future / Kerbal Atomics too aggressively at the same tier.

Thermal nozzles are explicitly called out by Sterling as “new standard main engines” once you can supply hundreds/thousands of ThermalPower/s.
Same idea as above, but a touch stronger because thermal nozzles can dominate quickly.

Sterling fusion engines are known to consume FusionPellets in common setups (players discuss making/using them in the Sterling ecosystem).
This patch increases FusionPellets burn and slightly increases ThermalPower draw if present.

Engineer skill for fusion engines (config-only approach)

Stock engines don’t support specialist bonuses, so the “no-plugin” way is to add a small efficiency converter that “recovers” a tiny fraction of expensive fuel, and scales with Engineer skill.

Antimatter should be rare and expensive, and the engines should be tuned so they don’t become “press button to win” once unlocked.
Because resource names vary by install, this patch targets common antimatter resource names and otherwise just nudges ThermalPower.

