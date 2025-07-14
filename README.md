# 🛠️ Multiplayer Carpenter Game
*Unreal Engine 5.5 – Blueprint Only*

Started 9/07/2025 

Submitted 14/07/2025

## 📄 Overview
This is a multiplayer carpentry game prototype built entirely using Unreal Engine Blueprints. Players collaborate to fulfill dynamic furniture orders using a shared set of machines, a common budget, and real-time replicated item systems.

---

## 🎮 Gameplay Summary
- Players begin in a shared carpentry workshop with a fixed starting budget.
- Orders spawn at random intervals and must be fulfilled accurately.
- Workflow:
  1. Use the **Chipping Machine** to spawn an item.
  2. Use the **Painting Machine** to color the item.
  3. Deliver the item to the **Order Zone**.
- Budget increases with correct deliveries.
- Incorrect item color results in a 50% penalty.
- Incorrect item type results in no reward or penalty.

---

## 🧩 Core Features
- ✅ Networked multiplayer (up to 4 players)
- ✅ Shared shop budget (replicated)
- ✅ Random order generation system
- ✅ Item production (Chipping Machine)
- ✅ Color customization (Painting Machine)
- ✅ Delivery and validation system
- ✅ 3-slot production area with live availability tracking
- ✅ Simple, universal interaction system (`E` key)
- ✅ Clean Blueprint Interface usage (no casting)
- ✅ Blueprint-only implementation

---

## 🧠 Architecture Overview
| System         | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| **GameMode**   | Spawns customer orders and controls round flow                              |
| **GameState**  | Holds shared, replicated variables (e.g., Budget, ActiveOrders)             |
| **PlayerCharacter** | Handles interaction, movement, and item pickup/drop logic             |
| **PlayerController** | Manages UI creation, removal, and communication with widgets         |
| **BP_ProductionArea** | Tracks occupied/unoccupied slots and spawns items in valid positions |
| **Widgets**    | Dynamic, per-player UI for machine interaction and order visualization      |
| **Interfaces** | Used to keep machine ↔ character interaction decoupled and scalable         |

---

## 🔗 Replication Notes
- All spawn logic, budget updates, and order handling occur on the **server**.
- Replicated variables trigger **OnRep** events for UI updates.
- Multicast RPCs used to broadcast visual effects and item spawn events.
- Picked-up items replicate movement for accurate client-side positioning.

---

## 🧪 Testing Instructions
1. Open the project in **Unreal Engine 5.5+**
2. In the top toolbar, set:
   - **Play Mode**: *Play As Listen Server*
   - **Number of Players**: *2 to 4*
3. Press **Play** to simulate multiplayer
4. Interact with machines using the `E` key and fulfill orders cooperatively

---

## 📁 Project Details
- Focus: Core functionality and replication — art assets are placeholder
- Blueprint-only project — no C++ code required
- Modular design with room for extension (inventory, more machines, etc.)




