# Caldera (Boiler)

## Color Palette

| Color   | HEX Code  | RGB Code          | Legend            |
| :----------------------------------------------------------------- | :-------- | :---------------- | :---------------- |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  | Action            |
| <img src="https://placehold.co/15x15/FFA500/FFA500.png" width="15"> | `#FFA500` | `RGB(255, 165, 0)`  | Script            |
| <img src="https://placehold.co/15x15/D32F2F/D32F2F.png" width="15"> | `#D32F2F` | `RGB(211, 47, 47)`  | Alert             |
| <img src="https://placehold.co/15x15/2B2B2B/2B2B2B.png" width="15"> | `#2B2B2B` | `RGB(43, 43, 43)`   | Background        |
| <img src="https://placehold.co/15x15/555555/555555.png" width="15"> | `#555555` | `RGB(85, 85, 85)`   | Fumes             |
| <img src="https://placehold.co/15x15/1E1E1E/1E1E1E.png" width="15"> | `#1E1E1E` | `RGB(30, 30, 30)`   |                   |
| <img src="https://placehold.co/15x15/F1F1F1/F1F1F1.png" width="15"> | `#F1F1F1` | `RGB(241, 241, 241)`| Icons/Text        |
| <img src="https://placehold.co/15x15/C0C0C0/C0C0C0.png" width="15"> | `#C0C0C0` | `RGB(192, 192, 192)`| Aire              |
| <img src="https://placehold.co/15x15/C9A9A9/C9A9A9.png" width="15"> | `#C9A9A9` | `RGB(201, 169, 169)`| Vapor/Steam |
| <img src="https://placehold.co/15x15/FFEB3B/FFEB3B.png" width="15"> | `#FFEB3B` | `RGB(255, 235, 59)` | Gas               |
| <img src="https://placehold.co/15x15/2196F3/2196F3.png" width="15"> | `#2196F3` | `RGB(33, 150, 243)` | Agua Dura         |
| <img src="https://placehold.co/15x15/007ACC/007ACC.png" width="15"> | `#007ACC` | `RGB(0, 122, 204)`  | Agua Tratada      |
| <img src="https://placehold.co/15x15/1E8D62/1E8D62.png" width="15"> | `#1E8D62` | `RGB(30, 141, 98)`  | Agua Precalentada |		
| <img src="https://placehold.co/15x15/4E4D82/4E4D82.png" width="15"> | `#4E4D82` | `RGB(78, 77, 130)`  | Agua Caliente 	  |
| <img src="https://placehold.co/15x15/4CAF50/4CAF50.png" width="15"> | `#4CAF50` | `RGB(76, 175, 80)`  | Desague           |
| <img src="https://placehold.co/15x15/D35F2F/D35F2F.png" width="15"> | `#D35F2F` | `RGB(211, 95, 47)` | Fuego             |
| <img src="https://placehold.co/15x15/D38F6F/D38F6F.png" width="15"> | `#D38F6F` | `RGB(211, 143, 111)` | Aire Comprimido   |
| <img src="https://placehold.co/15x15/6CCF70/6CCF70.png" width="15"> | `#6CCF70` | `RGB(108, 207, 112)` | Condicional     |
| <img src="https://placehold.co/15x15/F92E73/F92E73.png" width="15"> | `#F92E73` | `RGB(249, 46, 115)` | Continue         |
| <img src="https://placehold.co/15x15/F92EF3/F92EF3.png" width="15"> | `#F92EF3` | `RGB(249, 46, 243)` | Delays           |

## Nomenclature

### Charts

All Charts start with capitals letters

### Variables Naming Conventions

`CONSTANTS` all in capital letters

#### State Variables

* `state_of`: Indicates the status or state of several components (e.g., `state_pump`) by bits.

#### Status Variables

* `status_chart`: status of initializing a chart (e.g., `state_pump`).

#### Specific Variables

element_type_extra Eg. PH_Temp

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

## Variables

### Pumps (`state_pumps` - 32 bits)

#### Water Pumps

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

#### Gas Pumps

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 8   | Burner      | B-201 | 006
| 9   | *(Reserved)*|       |
| 10  | *(Reserved)*|       |
| 11  | *(Reserved)*|       |
| 12  | *(Reserved)*|       |
| 13  | *(Reserved)*|       |
| 14  | *(Reserved)*|       |
| 15  | *(Reserved)*|       |

#### Air Pumps

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 16  | Burner FD   | B-202 | 007
| 17  | Burner ID   | B-203 | 008
| 18  | *(Reserved)*|       |
| 19  | *(Reserved)*|       |
| 20  | *(Reserved)*|       |
| 21  | *(Reserved)*|       |
| 22  | *(Reserved)*|       |
| 23  | *(Reserved)*|       |
| ... | ...         | |
| 32  | Main Compresor  | B-101      |

### Flows/Pressures (`state_flows` `state_pressures`- 64 bits)

#### Raw-Water Flows (Bits 0-15)

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

#### Treated Water (Bits 16-31)

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

#### Gasoil

| Bit | Description | ID    |
| :-: | :---------- | :---- |
| 24  | TQ2-HV201   |       |
| 25  | HV201-FV201 |       |
| 26  | FV201-HV202 |       |
| 27  | HV202-BRN   |       |
| 28  | *(Reserved)*| Capilar |
| 29  | *(Reserved)*|       |
| 30  | *(Reserved)*|       |
| 31  | *(Reserved)*|       |

#### Air
| 32  | *(Reserved)*|       |
| 33  | *(Reserved)*|       |
| 34  | *(Reserved)*|       |
| 35  | *(Reserved)*|       |

## Steam (Bits 48-55)

| 48  | BLR-HV301      |       |
| 49  | HV301-FV301    |       |
| 50  | FV301-Fabric   |       |
| 51  | *(Reserved)*   |       |

#### Compress Air (Bits 56-63) [only Pressures]

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

### Alarms (`state_alarms`)

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

### Hand Valves (`state_valves`)

Bit
0-15 Suministro Agua HV-001 HV-010
16-31 Pneumatic HV-101 HV-103
32-45 Gas/Air HV-201
46 steam HV301
46-63


### Power

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

### View `state_views`

| Bit | Description | Default |
| :-: | :---------- | :---- |
| 0   | Fail-SYS    | false |
| 1   | Pneumatic-SYS| true  |
| 2   | *(Reserved)*|       |
| 3   | *(Reserved)*|       |
| 4   | *(Reserved)*|       |
| 5   | *(Reserved)*|       |
| 6   | *(Reserved)*|       |
| 7   | *(Reserved)*|       |

### `state_general_alerts`

| Bit | Description | Default |
| :-: | :---------- | :---- |
| 0   | TQ1 H 	    | LT003 |
| 1   | TQ1 L 		  | LT002 |
| 2   | TQ1 HH 		  | LT004 |
| 3   | TQ1 LL 		  | LT001 |
| 4   | TQ2 H       | LT007 |
| 5   | TQ2 L       | LT006 |
| 6   | TQ2 HH      | LT008 |
| 7   | TQ2 LL      | LT005 |

### View `state_fails`

| Bit | ID          | Direction   | Alarm  |
| :-: | :---------- | :---        | :---   |
| 0   | PT-001      | Supply-TQ1  | PT-001 |
| 1   | FT-001      | Supply-TQ1  | FT-001 |
| 2   | PT-002      | TQ1-Filter  | PT-002 |
| 3   | FT-002      | TQ1-Filter  | FT-002 |
| 4   | PT-003      | Filter-PreH | PT-003 |
| 5   | PT-004      | PreH-Boiler | PT-004 |
| 6   | FT-003      | PreH-Boiler | FT-003 |
| 7   | ZT-001      | Boiler-PreH | ZT-001 |
| 8   | PT-005      | Boiler-PreH | PT-005 |
| 9   | FT-004      | Boiler-PreH | FT-004 |


## Windows

| Name         | Keycut      |
| :----------- | :---------- |
| Caldera		   | C           |
| Tratamiento	 | F           |
| Pre-Calent.	 | P           |
| Quemador	   | Q           |
| TQ1	(Raw)	   | T           |
| Sistema	Suministro | S           |
| Sistema Caldera    | M           |
| Panel Mec.		     | F1           |
| TQ2	(Gasoil)	     | G           |

## Constants

| Name              | Description      |
| :-----------      | :---------- |
| P_FLOW_CAPACITY   | Pump Max (Flow) |
| SUPPLY_FLOW  | Water service (Flow) |
| AMBIENT_TEMP | Ambient (Temp)  |
| PH_HEAT_COEF |  Preheater Heat Coefficient (°C/s) |

## Units

| Name        | Unit  |
| :---------- | :----- |
| Temperature | °C |
| Pressure    |  mmHG |
| Flow        | m3/s |
| Level       | m |
| Humidity    |  |
| Speed       | m/s2 |
| Position    |  |

## Elements

### Tanque Agua Dura (TQ1)

* TQ1_level (ind)
  * TQ1_level_p (dep)
* TQ1_LEVEL_CAPACITY	10m3
* TQ1_level_top (dep)
  * TQ1_level_top_p (ind)
* TQ1_level_bottom (dep)
  * TQ1_level_bottom_p (ind)

### Tratamiento de Agua (FLT-001 [FLT])

### Pre Calentador (PH-001 [PH])

## Caldera (BLR-001 [BLR])

## Quemador (BRN-001 [BRN])

### states

**BRN_state**
0 - Off
1 - Purged
2 - PilotOn
3 - PilotOn // Main Flame

**FV-201 (Gasoil)**
0-1% -> Loss
X   Y
1%  4.6e-007
100% 0.0001

Y = X * 1.00545e-6 - 545.455e-9

**BRN_status_pilot**

==1       Turn On the flame
bits 0-3  (Sequence)
bit 0-4 (ON)     TurnOff (==31)

## Caldera

## Alarms

SensorFail -> Exp1

state_fails 0-8

## TODO

Al fallar un fluido debe detenerce en el proceso (Como el sistema de seguridad se activa los flujos se detienen...)

## Sounds

```
Sounds/
  Alert.wav
  Exp1.wav
  Exp2.wav
  Exp3.wav
```