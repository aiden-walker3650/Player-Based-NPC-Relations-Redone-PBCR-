# Player-Based-NPC-Relations-Redone-PBCR-

# Player Based NPC Relations Redone (PBCR)

![Garry's Mod](https://shields.io)
![License](https://shields.io)

**Player Based NPC Relations Redone (PBCR)** is a powerful and dynamic faction and relation management system for Garry's Mod. It allows players and server administrators to change their faction alignments on the fly, seamlessly shifting how NPCs interact with them. 

Whether you want to blend in with the Combine, lead a squad of Rebels, or test complex NPC behaviors, PBCR provides a robust framework to handle it all.

---

## 🚀 Features

- **Dynamic Faction Switching:** Instantly change your faction alignment via a clean UI or console commands.
- **Smart NPC Logic:** Advanced relationship overriding that updates NPC hostility in real-time.
- **Admin Controls & Persistence:** Complete control over player permissions, including a built-in system to save player model factions permanently.
- **Extensive Base Compatibility:** Out-of-the-box compatibility and enhanced integration with popular custom NPC bases like **VJ Base** and **ZBase**.
- **Developer-Friendly API:** Simple hooks and functions for third-party addon integration.

---

## 🛠️ Configuration & Admin Commands

PBCR includes server settings and commands to help administrators manage factions efficiently.

### Admin ConVars
* `pbcr_admin_only <0/1>` — Set to `1` to restrict faction switching exclusively to server administrators.

### Model Faction Saving
The addon features an automatic system that links specific player models to predefined factions. When a player spawns with or changes to that model, their faction updates automatically and saves across sessions.

---

## 💻 Developer API & Custom Factions

You can easily extend PBCR by registering custom factions or hooking into its events from your own third-party addons.

### Adding a Custom Faction
Use the following example to register a new faction into the PBCR system:

```lua
-- Example: Registering a custom "Zeta_Squad" faction
hook.Add("PBCR_OnInitialize", "RegisterCustomFactions", function()
    if PBCR and PBCR.RegisterFaction then
        PBCR.RegisterFaction("Zeta_Squad", {
            Name = "Zeta Squad",
            DefaultRelations = {
                ["D_HT"] = { "npc_combine_s" }, -- Hated by Combine
                ["D_LI"] = { "npc_citizen" }    -- Liked by Citizens
            }
        })
    end
end)
```

### Third-Party Integration
To check a player's current PBCR faction from another script:

```lua
-- Example: Custom door that only opens for the Combine faction
hook.Add("PlayerUse", "PBCR_FactionDoorCheck", function(ply, ent)
    if ent:GetName() == "combine_gate" then
        local currentFaction = ply:GetNWString("PBCR_Faction", "Default")
        if currentFaction == "Combine" then
            ent:Fire("Open")
            return true
        else
            ply:ChatPrint("Access Denied: You are not aligned with the Combine.")
            return false
        end
    end
end)
```

---

## 📦 Installation

1. Download or clone this repository.
2. Drop the `pbcr` folder into your Garry's Mod `garrysmod/addons/` directory.
3. Restart your server or launch your singleplayer game.

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
