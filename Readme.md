# Caldera (Boiler)

## Color Palette

| Color                                                              | HEX Code  | RGB Code          | Legend            |
| :----------------------------------------------------------------- | :-------- | :---------------- | :---------------- |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  |                   |
| <img src="https://placehold.co/15x15/FFA500/FFA500.png" width="15"> | `#FFA500` | `RGB(255, 165, 0)`  |                   |
| <img src="https://placehold.co/15x15/D32F2F/D32F2F.png" width="15"> | `#D32F2F` | `RGB(211, 47, 47)`  | Alert             |
| <img src="https://placehold.co/15x15/2B2B2B/2B2B2B.png" width="15"> | `#2B2B2B` | `RGB(43, 43, 43)`   | Background        |
| <img src="https://placehold.co/15x15/555555/555555.png" width="15"> | `#555555` | `RGB(85, 85, 85)`   |                   |
| <img src="https://placehold.co/15x15/1E1E1E/1E1E1E.png" width="15"> | `#1E1E1E` | `RGB(30, 30, 30)`   |                   |
| <img src="https://placehold.co/15x15/F1F1F1/F1F1F1.png" width="15"> | `#F1F1F1` | `RGB(241, 241, 241)`| Icons/Text        |
| <img src="https://placehold.co/15x15/C0C0C0/C0C0C0.png" width="15"> | `#C0C0C0` | `RGB(192, 192, 192)`| Aire              |
| <img src="https://placehold.co/15x15/A9A9A9/A9A9A9.png" width="15"> | `#A9A9A9` | `RGB(169, 169, 169)`| Humo (Vapor/Steam)|
| <img src="https://placehold.co/15x15/FFEB3B/FFEB3B.png" width="15"> | `#FFEB3B` | `RGB(255, 235, 59)` | Gas               |
| <img src="https://placehold.co/15x15/2196F3/2196F3.png" width="15"> | `#2196F3` | `RGB(33, 150, 243)` | Agua Dura         |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  | Agua Tratada      |
| <img src="https://placehold.co/15x15/1E8D62/1E8D62.png" width="15"> | `#1E8D62` | `RGB(30, 141, 98)`  | Agua Precalentada |
| <img src="https://placehold.co/15x15/4E4D82/4E4D82.png" width="15"> | `#4E4D82` | `RGB(78, 77, 130)`  | Agua Caliente     |
| <img src="https://placehold.co/15x15/4CAF50/4CAF50.png" width="15"> | `#4CAF50` | `RGB(76, 175, 80)`  | Desague           |
| <img src="https://placehold.co/15x15/D35F2F/D35F2F.png" width="15"> | `#D35F2F` | `RGB(211, 95, 47)`  | Fuego             |


# Nomenclature

## Charts

**GlobalCharts**

* Powerup
* Security

## Variable Naming Conventions

### Base Variable Names

* `state_of`: Indicates the status or state of a component (e.g., `state_pump`).

### Variable Prefixes (for Location/Type)

| Prefix | Description |
| :----- | :---------- |
| `Temp` | Temperature |
| `Pres` | Pressure    |
| `Flow` | Flow        |
| `Levl` | Level       |
| `Humd` | Humidity    |
| `Sped` | Speed       |
| `Posc` | Position    |

---

# Variables

## Pumps (`state_pump` - 32 bits)

Indicates the operational state of various pumps. Each bit corresponds to a specific pump.

### Water Pumps

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 0   | Raw         | B-001 |
| 1   | Treated     | B-002 |
| 2   | Preheat     | B-003 |
| 3   | Heat        | B-004 |
| 4   | Bilge (Boiler)| B-005 |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

### Gas Pumps

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 8   | Burner      | B-006 |
| 9   | *(Reserved)*|       |
| 10  | *(Reserved)*|       |
| 11  | *(Reserved)*|       |
| 12  | *(Reserved)*|       |
| 13  | *(Reserved)*|       |
| 14  | *(Reserved)*|       |
| 15  | *(Reserved)*|       |

### Air Pumps

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 16  | Burner      | B-007 |
| 17  | *(Reserved)*|       |
| 18  | *(Reserved)*|       |
| 19  | *(Reserved)*|       |
| 20  | *(Reserved)*|       |
| 21  | *(Reserved)*|       |
| 22  | *(Reserved)*|       |
| 23  | *(Reserved)*|       |

### Other Pumps

| Bit | Description | ID |
| :-: | :---------- | :- |
| 24  | *(Reserved)*|    |
| 25  | *(Reserved)*|    |
| 26  | *(Reserved)*|    |
| 27  | *(Reserved)*|    |
| 28  | *(Reserved)*|    |
| 29  | *(Reserved)*|    |
| 30  | *(Reserved)*|    |
| 31  | *(Reserved)*|    |

## Flows (`state_flows` - 64 bits)

### Water Flows (Bits 0-15)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 0   | *(Reserved)*|       |
| 1   | *(Reserved)*|       |
| 2   | *(Reserved)*|       |
| 3   | *(Reserved)*|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

### Air Flows (Bits 16-23)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 8   | *(Reserved)*|       |
| 9   | *(Reserved)*|       |
| 10  | *(Reserved)*|       |
| 11  | *(Reserved)*|       |
| 12  | *(Reserved)*|       |
| 13  | *(Reserved)*|       |
| 14  | *(Reserved)*|       |
| 15  | *(Reserved)*|       |

### Gas Flows (Bits 24-31)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 16  | *(Reserved)*|       |
| 17  | *(Reserved)*|       |
| 18  | *(Reserved)*|       |
| 19  | *(Reserved)*|       |
| 20  | *(Reserved)*|       |
| 21  | *(Reserved)*|       |
| 22  | *(Reserved)*|       |
| 23  | *(Reserved)*|       |

### Steam Flows (Bits 32-39)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 24  | *(Reserved)*|       |
| 25  | *(Reserved)*|       |
| 26  | *(Reserved)*|       |
| 27  | *(Reserved)*|       |
| 28  | *(Reserved)*|       |
| 29  | *(Reserved)*|       |
| 30  | *(Reserved)*|       |
| 31  | *(Reserved)*|       |

## Alarms (`state_alarms`)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 0   | *(Reserved)*|       |
| 1   | *(Reserved)*|       |
| 2   | *(Reserved)*|       |
| 3   | *(Reserved)*|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

