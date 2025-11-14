# World of Sea Battle — DPS Comparator

A web-based tool for comparing ship cannon damage output in **World of Sea Battle (Early Access)**. Compare cannons by their expected damage over a 60-second window, with support for different ship types and armor configurations.

![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Features

- **Cannon Comparison**: Compare cannons across Light, Medium, and Heavy categories
- **Ship-Based DPS**: Calculate total ship DPS by multiplying cannon DPS by ship cannon count
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

| Ship | Cannons | Cannon Size |
|------|---------|-------------|
| **Black Wind** | 16 | Light |
| **Essex** | 21 | Medium |
| **Anson** | 30 | Medium |

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

1. **Select a Ship** (optional):
   - Choose "All Cannons" to compare cannons without ship context
   - Select a specific ship (Black Wind, Essex, or Anson) to see total ship DPS
   - When a ship is selected, the cannon size is automatically locked to the ship's allowed size

2. **Choose Cannon Size**:
   - Light, Medium, or Heavy
   - Automatically locked when a ship is selected

3. **Select Target Armor**:
   - Click individual armor values (2-15) for specific comparisons
   - Use grouping buttons (Small Ships, Medium Ships, Heavy Ships, All-Around) for aggregate analysis

4. **View Results**:
   - Table automatically sorts by the rightmost column (damage/DPS)
   - Winner and runner-up are highlighted
   - Visual meters show relative performance
   - Sparklines show damage curves across armor ranges

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

