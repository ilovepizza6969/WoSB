# World of Sea Battle — DPS Comparator v1.3.2

A web-based tool for comparing ship cannon damage output in **World of Sea Battle (Early Access)**. Compare cannons by their expected damage over a 60-second window, with support for different ship types and armor configurations. Features an interactive PvP front-load damage analysis graph.

🔗 **Live Demo**: [https://ilovepizza6969.github.io/WoSB/](https://ilovepizza6969.github.io/WoSB/)

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Features

- **Cannon Comparison**: Compare cannons across Light, Medium, and Heavy categories
- **Ship-Based DPS**: Calculate total ship DPS by multiplying cannon DPS by ship cannon count
- **Boarding Damage**: View total boarding damage per cannon configuration (multiplied by ship's cannon count)
- **Boarding Damage Rate**: See boarding damage output over 60 seconds (Boarding DMG / 60s) to compare sustained boarding damage potential
- **PvP Front-Load Damage Analysis**: Interactive graph showing cumulative damage over 60 seconds
  - Step function visualization (horizontal lines = cooldown, vertical lines = shots)
  - Compare burst damage potential across all cannons
  - Independent controls for ship, cannon size, and target armor
  - Legend shows total damage at 60 seconds
- **Multiple Armor Modes**: 
  - Individual armor values (2-15)
  - Small Ships (armor 2-5)
  - Medium Ships (armor 6-10)
  - Heavy Ships (armor 11-15)
  - All-Around (armor 2-15)
- **Visual Indicators**: 
  - Winner/runner-up highlighting
  - Damage meters with visual bars
  - Sparkline charts for armor range performance
- **Real-Time Updates**: Instant recalculation when changing selections
- **No Dependencies**: Pure HTML, CSS, and JavaScript - no build process required

## Supported Ships

Ships are organized into two classes for visual organization. Ship class has no relationship to cannon size capabilities.

### Combat Class
| Ship | Cannons | Cannon Size |
|------|---------|-------------|
| **Black Wind** | 16 | Light |
| **Essex** | 21 | Medium, Light |
| **Anson** | 30 | Medium, Light |
| **Sans Pareil** | 38 | Heavy, Medium, Light |
| **Victory** | 49 | Heavy, Medium, Light |

### Heavy Class
| Ship | Cannons | Cannon Size |
|------|---------|-------------|
| **San Martin** | 20 | Light |
| **Constitution** | 26 | Medium, Light |
| **Bellona** | 35 | Medium, Light |
| **Redoutable** | 43 | Heavy, Medium, Light |
| **Apostolov** | 59 | Heavy, Medium, Light |

## How It Works

### Damage Calculation

The tool calculates damage using the following formula:

```
damage_per_shot = max(0, penetration − armor)
shots_in_60s = 60 ÷ reload_time_seconds
damage_in_60s = damage_per_shot × shots_in_60s
```

When a ship is selected, the total ship DPS is calculated as:

```
ship_dps = damage_in_60s × number_of_cannons
```

### Modes

1. **Individual Armor Mode**: Shows exact damage at a specific armor value (2-15)
2. **Aggregate Modes**: Shows average performance across armor ranges with sparkline visualizations
   - Small Ships: Armor 2-5
   - Medium Ships: Armor 6-10
   - Heavy Ships: Armor 11-15
   - All-Around: Armor 2-15

## Usage

### Comparison Table

1. **Select a Ship** (optional):
   - Choose "All Cannons" to compare cannons without ship context
   - Select a specific ship to see total ship DPS (ships are organized by Combat and Heavy classes)
   - When a ship is selected, the cannon size is automatically locked to the ship's allowed sizes

2. **Choose Cannon Size**:
   - Light, Medium, or Heavy
   - Automatically restricted to allowed sizes when a ship is selected

3. **Select Target Armor**:
   - Click individual armor values (2-15) for specific comparisons
   - Use grouping buttons (Small Ships, Medium Ships, Heavy Ships, All-Around) for aggregate analysis

4. **View Results**:
   - Table automatically sorts by the rightmost column (damage/DPS)
   - Winner and runner-up are highlighted
   - Visual meters show relative performance
   - Sparklines show damage curves across armor ranges

### PvP Front-Load Damage Graph

1. **Select Ship, Cannon Size, and Target Armor**: Independent controls specific to the graph
2. **View the Graph**:
   - X-axis: Time from 0-60 seconds
   - Y-axis: Cumulative damage
   - Horizontal lines: Reload/cooldown periods (no shots fired)
   - Vertical lines: Shots fired (damage increases)
   - Steeper lines = faster front-load damage = better for quick PvP bursts
3. **Legend**: Shows final damage values at 60 seconds, sorted by total damage

## Installation

No installation required! This is a single HTML file that runs entirely in your browser.

### Running Locally

1. Clone or download this repository
2. Open `index.html` in any modern web browser
3. That's it!

### Hosting

You can host this on any static hosting service:
- GitHub Pages
- Netlify
- Vercel
- Any web server

Simply upload `index.html` to your hosting service.

## Technical Details

- **Pure Vanilla JavaScript**: No frameworks or dependencies
- **Responsive Design**: Works on desktop and mobile devices
- **Modern CSS**: Uses CSS variables, flexbox, and gradients
- **Accessibility**: ARIA labels and semantic HTML
- **Performance**: Lightweight and fast - all calculations happen client-side

## Cannon Data

The tool includes data for:

- **Light Cannons**: 6-pdr rusty, 6-pdr culverin, 12-pdr carronade, 8-pdr cannon, 8-pdr culverin, 16-pdr carronade
- **Medium Cannons**: 16-pdr cannon, 16-pdr culverin, 24-pdr carronade, 18-pdr cannon, 18-pdr long cannon, 28-pdr carronade, 20-pdr admiral, 22-pdr Scorcher, 32-pdr Stormbringer
- **Heavy Cannons**: 32-pdr cannon, 32-pdr long cannon, 42-pdr carronade, 36-pdr inrog, 38-pdr jericho, 48-pdr colossus

Each cannon has:
- **Penetration**: Base penetration value
- **Reload**: Reload time in seconds
- **Boarding Damage**: Damage dealt during boarding actions (multiplied by ship's cannon count)
- **Boarding DMG / 60s**: Boarding damage output rate over 60 seconds, calculated as (boarding_damage / reload) × 60 × number_of_cannons

## Assumptions

The calculations assume:
- Every shot hits (no misses)
- No critical hits or damage multipliers
- No damage falloff
- Constant reload times
- No overheating or ammo limits
- 60-second time window

## Contributing

Contributions are welcome! Feel free to:
- Add more ships
- Add more cannons
- Improve the UI/UX
- Fix bugs
- Add new features

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

Built for the **World of Sea Battle (Early Access)** community to help players make informed decisions about cannon loadouts.

---

**Tip**: Faster reload shines at low armor; at higher armor, bigger penetration can catch up.

