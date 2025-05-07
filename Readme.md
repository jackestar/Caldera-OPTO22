# Caldera (Boiler)

## Color Palette

| Color                                                              | HEX Code  | RGB Code          | Legend            |
| :----------------------------------------------------------------- | :-------- | :---------------- | :---------------- |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  | Action            |
| <img src="https://placehold.co/15x15/FFA500/FFA500.png" width="15"> | `#FFA500` | `RGB(255, 165, 0)`  | Script            |
| <img src="https://placehold.co/15x15/D32F2F/D32F2F.png" width="15"> | `#D32F2F` | `RGB(211, 47, 47)`  | Alert             |
| <img src="https://placehold.co/15x15/2B2B2B/2B2B2B.png" width="15"> | `#2B2B2B` | `RGB(43, 43, 43)`   | Background        |
| <img src="https://placehold.co/15x15/555555/555555.png" width="15"> | `#555555` | `RGB(85, 85, 85)`   | Fumes             |
| <img src="https://placehold.co/15x15/1E1E1E/1E1E1E.png" width="15"> | `#1E1E1E` | `RGB(30, 30, 30)`   |                   |
| <img src="https://placehold.co/15x15/F1F1F1/F1F1F1.png" width="15"> | `#F1F1F1` | `RGB(241, 241, 241)`| Icons/Text        |
| <img src="https://placehold.co/15x15/C0C0C0/C0C0C0.png" width="15"> | `#C0C0C0` | `RGB(192, 192, 192)`| Aire              |
| <img src="https://placehold.co/15x15/C9A9A9/C9A9A9.png" width="15"> | `#C9A9A9` | `RGB(201, 169, 169)`| Humo (Vapor/Steam)|
| <img src="https://placehold.co/15x15/FFEB3B/FFEB3B.png" width="15"> | `#FFEB3B` | `RGB(255, 235, 59)` | Gas               |
| <img src="https://placehold.co/15x15/2196F3/2196F3.png" width="15"> | `#2196F3` | `RGB(33, 150, 243)` | Agua Dura         |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  | Agua Tratada      |
| <img src="https://placehold.co/15x15/1E8D62/1E8D62.png" width="15"> | `#1E8D62` | `RGB(30, 141, 98)`  | Agua Precalentada |		
| <img src="https://placehold.co/15x15/4E4D82/4E4D82.png" width="15"> | `#4E4D82` | `RGB(78, 77, 130)`  | Agua Caliente 	    |
| <img src="https://placehold.co/15x15/4CAF50/4CAF50.png" width="15"> | `#4CAF50` | `RGB(76, 175, 80)`  | Desague           |
| <img src="https://placehold.co/15x15/D35F2F/D35F2F.png" width="15"> | `#D35F2F` | `RGB(211, 95, 47)`  | Fuego             |


#D38F6F Aire Comprimido (211,143,111)
#6CCF70 Condicional (108, 207, 112)
#F92E73 Continue (249, 46, 115)
#F92EF3 delay (249, 46, 243)


# Nomenclature

## Charts

**GlobalCharts**

* Powerup
* Security

## Variable Naming Conventions

### State variables

* `state_of`: Indicates the status or state of a component (e.g., `state_pump`).

### Especific Varibles what_of_where/how

| Prefix | Description |
| :----- | :---------- |
| `Temp` | Temperature |
| `Pres` | Pressure    |
| `Flow` | Flow        |
| `Levl` | Level       |
| `Humd` | Humidity    |
| `Sped` | Speed       |
| `Posc` | Position    |

## Constants in Mayus

---

# Variables

## Pumps (`state_pump` - 32 bits)

32 - Main Compresor

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

## Flows/Presures (`state_flows` `state_presures`- 64 bits)

### Raw-Water Flows (Bits 0-15)

| Bit | Description   | ID    |
| :-: | :------------ | :---- |
| 0   | Supply-HV001  |       |
| 1   | HV001-FSV001  |       |
| 2   | FSV-001-HV002 |       |
| 3   | HV002-TQ1	  |       |
| 4   | TQ1-HV003	  |       |
| 5   | HV003-FV001   |       |
| 6   | FV001-HV004   |       |
| 7   | HV004-FLT001  |       |

### Treated Water (Bits 16-31)

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 8   | FLT001-HV005|       |
| 9   | HV005-FV006 |       |
| 10  | FV006-PRHEAT|       |
| 11  | PRHEAT-HV007|       |
| 12  | HV007-FV002 |       |
| 13  | FV002-HV008 |       |
| 14  | HV008-BOILER|       |
| 15  | BOILER-HV009|       |
| 16  | HV009-FV003 |       |
| 17  | FV003-HV010 |       |
| 18  | HV010-PRHEAT|       |
| 19  | *(Reserved)*|       |
| 20  | *(Reserved)*|       |
| 21  | *(Reserved)*|       |
| 22  | *(Reserved)*|       |
| 23  | *(Reserved)*|       |

### Compress Air (Bits 56-63) [only Presures]

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 56  | SYSTEM		|       |
| 57  | FV001 		|       |
| 58  | FV002 		|       |
| 59  | FV003 		|       |
| 60  | *(Reserved)*|       |
| 61  | *(Reserved)*|       |
| 62  | *(Reserved)*|       |
| 63  | *(Reserved)*|       |

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

## Valvulas (`state_valves`) // Hand Valves

Bit
0-15 Suministro Agua HV-001 HV-009
16-31 Pneumatica HV-101 HV-103


## Power

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 0   | Main Power  |       |
| 1   | *(Reserved)*|       |
| 2   | *(Reserved)*|       |
| 3   | *(Reserved)*|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

`state_views`

| Bit | Description | Default |
| :-: | :---------- | :---- |
| 0   | Fail-SYS    | false |
| 1   | Neumatic-SYS| true  |
| 2   | *(Reserved)*|       |
| 3   | *(Reserved)*|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

`state_general_alerts`

| Bit | Description | Default |
| :-: | :---------- | :---- |
| 0   | TQ1 H 	    |       |
| 1   | TQ1 L 		|       |
| 2   | TQ1 HH 		|       |
| 3   | TQ1 LL 		|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

# Windows

Caldera		| C
Tratamiento	| F
Pre-Calent	| P
Quemador	| Q
Tanque		| T
Sistema		| S
Panel		| M

# Elements

## TQ1 Tanque Agua Dura

TQ1_level
TQ1_LEVEL_CAPACITY	10m3
TQ1_level_top
TQ1_level_bottom