# Physics Simulations Documentation

## Overview
Physics Simulations adalah fitur interaktif yang memvisualisasikan tiga konsep fisika fundamental menggunakan HTML5 Canvas dan JavaScript. Dirancang untuk membantu mahasiswa memahami kinematika, mekanika orbit, dan gelombang mekanik melalui animasi real-time.

---

## 1. Projectile Motion Simulation

### Deskripsi
Simulasi gerak parabola yang menunjukkan bagaimana sebuah proyektil bergerak di bawah pengaruh gravitasi. Pengguna dapat menyesuaikan sudut peluncuran, kecepatan awal, dan akselerasi gravitasi untuk melihat pengaruhnya terhadap lintasan.

### Physics Equations
```
Horizontal Position:  x(t) = v₀ₓ × t = v₀ × cos(θ) × t
Vertical Position:    y(t) = v₀ᵧ × t - ½ × g × t² = v₀ × sin(θ) × t - ½ × g × t²
Horizontal Velocity:  vₓ = v₀ × cos(θ)  [constant]
Vertical Velocity:    vᵧ(t) = v₀ × sin(θ) - g × t
```

### Input Parameters
| Parameter | Range | Unit | Default | Description |
|-----------|-------|------|---------|-------------|
| Launch Angle | 0 - 90 | degrees | 45 | Angle of launch from horizontal |
| Initial Velocity | 5 - 50 | m/s | 30 | Speed at which projectile is launched |
| Gravity | 5 - 20 | m/s² | 9.8 | Gravitational acceleration |

### Visualization Features
- **Sky gradient background**: Blue gradient for realistic sky appearance
- **Ground line**: Brown horizontal line at launch height
- **Trajectory arc**: Blue dashed line showing the complete parabolic path
- **Projectile ball**: Red circle representing the moving object
- **Velocity vector**: Green arrow showing current velocity direction
- **Real-time data**: Time, horizontal distance, vertical distance displayed on canvas
- **Interactive**: Sliders update values in real-time; "Start" button launches new trajectory

### HTML Classes & IDs
```html
<input class="proj-angle" type="range" min="0" max="90" value="45">
<input class="proj-velocity" type="range" min="5" max="50" value="30">
<input class="proj-gravity" type="range" min="5" max="20" value="9.8" step="0.1">
<button class="proj-start" data-i18n="simulations.start">Start Simulation</button>
<canvas id="projectile-canvas" width="800" height="400"></canvas>
```

### JavaScript Implementation
- **Canvas dimensions**: 800×400 pixels
- **Scale factor**: 5 pixels per meter
- **Time step (dt)**: 0.05 seconds per frame
- **Animation**: Runs until projectile hits ground or leaves canvas bounds
- **Function**: `drawProjectileMotion()` handles physics and rendering

### Physics Accuracy Notes
- Uses kinematic equations for parabolic motion
- Gravity is constant (no air resistance modeling)
- Time-stepping integration may have minor accumulation errors at very high parameters
- Display precision: 1 decimal place for calculations

---

## 2. Orbital Motion Simulation

### Deskripsi
Simulasi mekanika orbit yang menunjukkan interaksi gravitasi antara bintang pusat dan beberapa planet. Mengikuti hukum gravitasi universal Newton dan hukum gerak Kepler. Pengguna dapat menyesuaikan kecepatan orbit dan jumlah planet untuk mengamati dinamika sistem multi-benda.

### Physics Equations
```
Gravitational Force:  F = G × M₁ × M₂ / r²
Acceleration:         a = F / m
Position Update:      r(t+dt) = r(t) + v(t) × dt + ½ × a(t) × dt²
Velocity Update:      v(t+dt) = v(t) + a(t) × dt
Orbital Velocity:     v = √(G × M / r)  [for circular orbits]
```

### Input Parameters
| Parameter | Range | Unit | Default | Description |
|-----------|-------|------|---------|-------------|
| Orbital Speed | 0.1 - 1.0 | × | 0.5 | Multiplier for simulation speed factor |
| Number of Planets | 1 - 5 | count | 3 | How many planets to simulate |

### Visualization Features
- **Dark space background**: Black gradient simulating deep space
- **Star field**: Small white dots creating a starfield effect
- **Central sun**: Large yellow circle with glow effect (stationary)
- **Planets**: 5 different colored circles at different orbital radii
- **Orbital paths**: White dashed circles showing orbits
- **Planet glows**: Color-matched glow around each planet
- **Multi-scale orbits**: Planets at increasing distances with decreasing orbital speeds
- **Real-time animation**: Smooth 60fps orbital motion

### Planet Configuration
```javascript
Orbit Radii:   60px, 100px, 140px, 180px, 220px
Colors:        Yellow, Blue, Green, Red, Purple
Sizes:         Decreasing with distance
Base Speeds:   0.015, 0.01, 0.007, 0.005, 0.003 (rad/frame)
```

### HTML Classes & IDs
```html
<input class="orbital-speed" type="range" min="0.1" max="1" value="0.5" step="0.1">
<input class="orbital-count" type="number" min="1" max="5" value="3">
<button class="orbital-reset" data-i18n="simulations.reset-btn">Reset Simulation</button>
<canvas id="orbital-canvas" width="800" height="500"></canvas>
```

### JavaScript Implementation
- **Canvas dimensions**: 800×500 pixels
- **Center point**: (400, 250) - middle of canvas
- **Gravitational constant**: Effective G embedded in orbital speeds
- **Animation**: Continuous loop with dynamic planet generation
- **Reset button**: Reinitializes planets when clicked
- **Function**: `drawOrbitalMotion()` handles physics and rendering

### Physics Accuracy Notes
- Uses Verlet integration for position/velocity updates
- Simplified gravitational model (not true N-body gravity)
- Orbital speeds are pre-calculated for stable circular orbits
- Multiple planets don't interact gravitationally with each other (only with sun)
- Suitable for educational visualization, not scientific accuracy

---

## 3. Mechanical Wave Simulation

### Deskripsi
Simulasi gelombang mekanik yang memvisualisasikan propagasi gelombang dalam berbagai bentuk. Pengguna dapat mengamati bagaimana frekuensi, amplitudo, dan jenis gelombang (sinus, persegi, segitiga) mempengaruhi karakteristik gelombang. Animasi menunjukkan osilasi titik-titik di sepanjang medium.

### Physics Equations
```
Sine Wave:           y(x,t) = A × sin(2π/λ × x - 2π × f × t)
Square Wave:         y(x,t) = A × sgn(sin(2π/λ × x - 2π × f × t))
Triangle Wave:       y(x,t) = A × arcsin(sin(2π/λ × x - 2π × f × t))
Wave Speed:          v = λ × f  (wavelength × frequency)
Angular Frequency:   ω = 2π × f
Wave Number:         k = 2π / λ
Phase:               φ = kx - ωt
```

### Input Parameters
| Parameter | Range | Unit | Default | Description |
|-----------|-------|------|---------|-------------|
| Frequency | 0.5 - 3.0 | Hz | 1.0 | Oscillations per second |
| Amplitude | 10 - 60 | pixels | 30 | Height of wave oscillation |
| Wave Type | sine/square/triangle | - | sine | Mathematical waveform shape |

### Visualization Features
- **White background**: Clean canvas for wave visualization
- **Grid lines**: Thin gray vertical lines marking wavelength quarters
- **Horizontal reference**: Dashed line at center showing equilibrium
- **Wave curve**: Red thick line showing the wave shape
- **Wave points**: Blue dots at regular intervals showing particle positions
- **Dynamic labels**: Displays frequency, amplitude, wavelength, wave speed
- **Real-time updates**: All parameters change wave instantly on slider adjustment

### Wave Type Characteristics
```
Sine Wave:
- Smooth continuous oscillation
- Fundamental frequency component
- Used in: Sound, light, AC electricity

Square Wave:
- Abrupt transitions between max/min
- Contains odd harmonics (1x, 3x, 5x fundamental)
- Used in: Digital signals, synthesizers

Triangle Wave:
- Linear rise and fall
- Contains odd harmonics like square (weaker)
- Used in: Synthesizer sounds
```

### HTML Classes & IDs
```html
<input class="wave-frequency" type="range" min="0.5" max="3" value="1" step="0.1">
<input class="wave-amplitude" type="range" min="10" max="60" value="30">
<select class="wave-type">
    <option value="sine" data-i18n="simulations.sine">Sine</option>
    <option value="square" data-i18n="simulations.square">Square</option>
    <option value="triangle" data-i18n="simulations.triangle">Triangle</option>
</select>
<button class="wave-toggle" data-i18n="simulations.start">Start</button>
<canvas id="wave-canvas" width="900" height="300"></canvas>
```

### JavaScript Implementation
- **Canvas dimensions**: 900×300 pixels
- **Center Y**: 150 pixels (middle of canvas)
- **Fixed wavelength**: 80 pixels (can be modified in code)
- **Time step**: 0.02 per frame
- **Animation**: Continuous wave propagation when running
- **Pause/Play toggle**: Button toggles simulation on/off
- **Function**: `drawWaveMotion()` handles wave generation and rendering

### Wave Speed Calculation
```
v = λ × f = 80 px × frequency (Hz)
Example: 1 Hz frequency → 80 pixels/second wave speed
```

### Physics Accuracy Notes
- Uses mathematical sine/square/triangle functions (not physical medium simulation)
- Wavelength is fixed at 80 pixels (can be adjusted in code)
- Amplitude is in pixel units (not physical units)
- Simulation shows spatial snapshot at each time; not particle tracking
- Suitable for frequency-amplitude relationship visualization

---

## Tab Navigation System

### Implementation
Each simulation is in a separate tab accessed via `.sim-tab` buttons:

```html
<button class="sim-tab" data-tab="projectile">Projectile Motion</button>
<button class="sim-tab" data-tab="orbital">Orbital Motion</button>
<button class="sim-tab" data-tab="wave">Mechanical Wave</button>

<div class="sim-content" data-tab="projectile"><!-- Content --></div>
<div class="sim-content" data-tab="orbital"><!-- Content --></div>
<div class="sim-content" data-tab="wave"><!-- Content --></div>
```

### JavaScript Tab Handler
```javascript
simTabs.forEach(tab => {
    tab.addEventListener('click', () => {
        const tabName = tab.dataset.tab;
        // Remove active class from all, add to clicked
        // Automatically start orbital/wave on tab switch
    });
});
```

### Behavior
- Clicking a tab switches to that simulation
- Previous animation is canceled
- Projectile waits for "Start" button
- Orbital and Wave auto-start when tab becomes active

---

## Slider Value Display Updates

### Implementation
Real-time display of slider values with appropriate units:

```javascript
updateSliderDisplay('.proj-angle', '.proj-angle-value', '°');
updateSliderDisplay('.proj-velocity', '.proj-velocity-value', ' m/s');
updateSliderDisplay('.proj-gravity', '.proj-gravity-value', ' m/s²');
updateSliderDisplay('.orbital-speed', '.orbital-speed-value', '×');
updateSliderDisplay('.wave-frequency', '.wave-frequency-value', ' Hz');
updateSliderDisplay('.wave-amplitude', '.wave-amplitude-value', ' px');
```

### Function
```javascript
function updateSliderDisplay(sliderClass, valueClass, unit = '') {
    const slider = document.querySelector(sliderClass);
    slider.addEventListener('input', () => {
        const displayEl = document.querySelector(valueClass);
        displayEl.textContent = parseFloat(slider.value).toFixed(1) + unit;
    });
}
```

---

## Internationalization (i18n)

### Indonesian Keys
```
'nav.simulations': 'Simulasi Fisika'
'simulations.title': 'Simulasi Fisika Interaktif'
'simulations.subtitle': 'Jelajahi konsep-konsep fisika...'
'simulations.projectile': 'Gerak Parabola'
'simulations.orbital': 'Gerak Orbit'
'simulations.wave': 'Gelombang Mekanik'
... [35+ total keys]
```

### English Keys
```
'nav.simulations': 'Physics Simulations'
'simulations.title': 'Interactive Physics Simulations'
'simulations.subtitle': 'Explore fundamental physics concepts...'
'simulations.projectile': 'Projectile Motion'
'simulations.orbital': 'Orbital Motion'
'simulations.wave': 'Mechanical Waves'
... [35+ total keys]
```

### Language Switching
- All UI labels use `data-i18n` attributes
- `updateAllTranslations()` called on language change
- Canvas-drawn text uses `t()` function for translation
- Wave toggle button text updates dynamically

---

## CSS Styling

### Tab Styling
```css
.sim-tab {
    cursor: pointer;
    transition: all 0.3s ease;
    border-bottom: 2px solid transparent;
}

.sim-tab.active {
    color: #4f46e5;
    border-bottom-color: #4f46e5;
}
```

### Content Styling
```css
.sim-content {
    display: none;
}

.sim-content.active {
    display: block;
    animation: slideUp 0.3s ease-out;
}
```

### Canvas Styling
```css
canvas {
    max-width: 100%;
    height: auto;
    display: block;
    margin: 0 auto;
    border: 1px solid #d1d5db;
    border-radius: 0.5rem;
}
```

### Dark Mode
- All canvases have dark mode backgrounds
- Projectile: gradient from cyan to blue
- Orbital: gradient from gray-900 to black
- Wave: dark gray background
- Text colors adapt to background

---

## Testing Checklist

### Functionality Tests
- [ ] Projectile Motion: Launch at various angles, verify parabolic path
- [ ] Projectile Motion: Change velocity, observe range changes
- [ ] Projectile Motion: Adjust gravity, see steeper/flatter trajectories
- [ ] Orbital Motion: Start/reset simulation, planets move smoothly
- [ ] Orbital Motion: Adjust planet count, verify correct number displayed
- [ ] Orbital Motion: Change speed, verify animation rate changes
- [ ] Wave Motion: Change frequency, observe wavelength changes
- [ ] Wave Motion: Adjust amplitude, see taller/shorter waves
- [ ] Wave Motion: Switch wave type, see different waveforms
- [ ] Wave Motion: Pause/resume with toggle button

### UI Tests
- [ ] All three tabs clickable and switch content correctly
- [ ] Slider value displays update in real-time
- [ ] Buttons are clickable and responsive
- [ ] Proper spacing and layout on different screen sizes
- [ ] Dark mode: Canvas readability and colors correct

### Language Tests
- [ ] All labels in Indonesian when language is 'id'
- [ ] All labels in English when language is 'en'
- [ ] Language switching updates all UI text
- [ ] Wave toggle button text changes correctly

### Performance Tests
- [ ] Smooth animation at 60fps (no stuttering)
- [ ] CPU usage reasonable while running
- [ ] No memory leaks after long simulation runs
- [ ] Switching tabs doesn't cause delays

### Compatibility Tests
- [ ] Chrome: All simulations work smoothly
- [ ] Firefox: Canvas rendering correct
- [ ] Safari: No animation performance issues
- [ ] Mobile (iOS/Android): Canvas scales properly, touch controls work

---

## Modification Guide

### Changing Physics Parameters

**Projectile Motion - Change gravity default:**
```javascript
const gravity = parseFloat(document.querySelector('.proj-gravity').value);
// Default: 9.8 m/s² (Earth gravity)
// Moon: 1.62 m/s²
// Jupiter: 24.79 m/s²
```

**Orbital Motion - Add more planets:**
```javascript
const baseRadii = [60, 100, 140, 180, 220, 260];  // Add 6th orbit
const colors = ['#fbbf24', '#3b82f6', '#10b981', '#f87171', '#a78bfa', '#f472b6'];
const baseSpeeds = [0.015, 0.01, 0.007, 0.005, 0.003, 0.002];
```

**Wave Motion - Change wavelength:**
```javascript
const wavelength = 80;  // pixels
// Decrease for tighter waves, increase for stretched waves
```

### Adding Physics Enhancements

1. **Air resistance in projectile motion:**
```javascript
const dragCoefficient = 0.1;  // Add to velocity calculation
```

2. **True N-body gravity in orbital motion:**
```javascript
// Calculate gravitational force between all planet pairs
// Not just attraction to sun
```

3. **Particle velocity visualization in waves:**
```javascript
// Draw velocity vectors at each point
// Show particles oscillating, not just curve
```

---

## Known Limitations

1. **Projectile Motion:**
   - No air resistance modeling
   - No rotation of projectile visualized
   - Canvas coordinate system may not match expected physics coordinates

2. **Orbital Motion:**
   - Planets don't gravitationally interact with each other
   - Simplified orbital speed calculation (not true Kepler orbits)
   - Limited to 5 planets maximum

3. **Wave Motion:**
   - Not a true wave medium simulation
   - Doesn't show transverse particle motion
   - Mathematical function rather than physical wave equation solution

4. **General:**
   - Canvas resolution fixed at definition time
   - No data export/save functionality
   - Simulations run in browser thread (can block if CPU-heavy)
   - No 3D visualization (yet - could be added with Three.js)

---

## Future Enhancements

### High Priority
- [ ] Add physics simulation speed controls
- [ ] Export canvas as image/video
- [ ] Adjustable canvas resolution for different screen sizes
- [ ] Pause/resume functionality for all simulations

### Medium Priority
- [ ] 3D visualization using Three.js
- [ ] Additional simulations (pendulum, spring oscillation, collisions)
- [ ] Real-time data plotting (position vs time graphs)
- [ ] Multiple object tracking and comparison

### Low Priority
- [ ] Advanced physics options (relativistic, quantum effects)
- [ ] Custom background images
- [ ] Sound effects for collisions/impacts
- [ ] Physics parameter presets (Earth/Moon/planets)

---

## File Locations

- **Main file**: `index.html` (lines ~3126-3320 for HTML, lines ~5070-5450 for JavaScript)
- **CSS**: `<style>` section (lines ~1527-1590)
- **i18n keys**: Lines ~3973-4000 (Indonesian), ~4435-4462 (English)
- **Canvas elements**: IDs `projectile-canvas`, `orbital-canvas`, `wave-canvas`

---

## Contact & Support

For questions about physics implementation or feature requests, refer to:
- Physics concepts: Refer to the detailed topic pages in the application
- Implementation details: Check the inline code comments in index.html
- Troubleshooting: See Testing Checklist section above

---

**Last Updated**: 2024
**Physics Simulations Version**: 1.0
**Status**: Production Ready ✅
