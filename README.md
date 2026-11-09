
# NPC & Persona Portrait Switcher
 
A lightweight SillyTavern extension for narrator/DM setups. When your DM character's message contains an NPC's name (or any keyword you define), their portrait automatically appears on the right side of the chat. The active user persona can be shown on the left side at the same time.
 
Supports **expression overrides**: if both a character keyword and an expression keyword appear in the same message, the matching expression portrait is shown instead of the default.

Supports **multiple NPCs**: an icon tray appears above the portrait for recently mentioned NPCs. Select an icon to switch the main portrait.
 
The portrait is interactive — hover to reveal `‹ ›` arrows to manually cycle through all portraits for that character.
 
## Installation
 
1. In SillyTavern, open the **Extensions** panel (puzzle-piece icon)
2. Click **Install extension** and paste:
```
   https://github.com/NoaThouard/SillyTavern-Extension-NPC-Portait-Switcher
```
   Or manually copy this folder into:
```
   SillyTavern/public/scripts/extensions/third-party/npc-portrait-switcher/
```
3. Reload SillyTavern
## Setup
 
1. Open the **Extensions** panel and find **NPC Portrait Switcher**
2. Open the chat you want to configure; settings and NPC entries are stored per chat
3. Click **+ Add NPC** for each character you want
4. Type the keyword(s) to watch for, comma separated (e.g. `Vexis, Vex`)
5. Upload their default portrait — a 2:3 crop dialog will open automatically
6. Optionally add **expressions** under each NPC — each expression has its own keyword(s) and image
7. Enable or disable **Show active user persona portrait** as desired
8. Optionally set **Sticky replies** — the number of replies the NPC remains after its last mention (0 = clear immediately)
## How it works
 
- After every AI message, the extension scans the text for your keywords
- Opening or switching chats restores the NPCs found in the latest assistant message
- The persona portrait follows persona and chat changes automatically
- NPC and persona portraits can be enabled independently in the extension settings
- All switches, NPC entries, expressions, and matching options are stored in the current chat metadata
- **Character match first**: the first NPC entry whose keyword appears in the message wins
- **Expression match second**: within that character, the first expression whose keyword also appears wins — otherwise the default portrait is shown
- Both portraits use the colors of the selected SillyTavern theme and appear symmetrically on wide screens
- The settings drawer uses SillyTavern's native UI components, so third-party themes can style it too
- Keyword matching is case-insensitive by default (toggle in settings)
- Hover the portrait to reveal: a **✕** close button and **‹ ›** arrows to manually cycle portraits
## Examples

### NEW Multi-NPC support!

<img width="400" alt="image" src="https://github.com/user-attachments/assets/229efa2a-a7da-4e82-8ad1-445a60ba6be9" />
<img width="400" alt="image" src="https://github.com/user-attachments/assets/8479fc7a-1f8c-42fb-b905-4ca6e75c3e71" />


---
<img width="400" alt="default portrait" src="https://github.com/user-attachments/assets/298d3e3b-871e-475b-b4ac-6704e3e32ba0" />
<img width="400" alt="angry expression" src="https://github.com/user-attachments/assets/ddf6620c-e169-43b8-b791-7c026a83ee8f" />

## Tips
 
- Works best with **Visual Novel Mode** enabled (wider side panels)
- Persona and NPC portraits are hidden below 1200 px viewport width to preserve chat space
- Separate multiple keywords with commas: `Vexis, Vex, the drow`
- Portrait clears automatically on chat switch
- The manual `‹ ›` arrows let you browse all expressions for the current character regardless of what was detected
## Notes
 
- Images are stored as **base64 in the current chat metadata** — keep portraits under ~500KB to avoid bloating the chat file
- Existing global settings are migrated once to the first chat opened after updating to version 1.3.0
- All uploaded images are cropped to **2:3 portrait ratio** (512×768) automatically
- Expressions are checked in the order you define them — first match wins
