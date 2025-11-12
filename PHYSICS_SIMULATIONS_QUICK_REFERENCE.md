# Physics Simulations - Quick Reference Guide

## 🚀 Quick Start (30 seconds)

1. Open the application
2. Scroll to **"Simulasi Fisika"** / **"Physics Simulations"** section
3. Click one of the three tabs:
   - **Gerak Parabola** / **Projectile Motion**
   - **Gerak Orbit** / **Orbital Motion**  
   - **Gelombang Mekanik** / **Mechanical Wave**
4. Adjust sliders and click buttons to run simulations

---

## 📊 Three Simulations Overview

### 1️⃣ Projectile Motion (Gerak Parabola)
**What it shows**: How objects move through the air under gravity

**Controls**:
- **Launch Angle**: 0-90° (default 45°)
- **Initial Velocity**: 5-50 m/s (default 30 m/s)
- **Gravity**: 5-20 m/s² (default 9.8 m/s²)

**Button**: Click **"Start Simulation"** to launch

**What to try**:
- Set angle to 45° for maximum range
- Increase velocity to throw farther
- Decrease gravity to see higher trajectory

**Physics**: `y = v₀×sin(θ)×t - ½×g×t²`

---

### 2️⃣ Orbital Motion (Gerak Orbit)
**What it shows**: Planets orbiting a star

**Controls**:
- **Orbital Speed**: 0.1-1.0× (default 0.5×)
- **Number of Planets**: 1-5 (default 3)

**Button**: Click **"Reset Simulation"** to restart

**What to try**:
- Increase planet count to see multiple orbits
- Speed up the simulation to see fast motion
- Reset to start over

**Physics**: Gravitational attraction `F = G×M×m/r²`

---

### 3️⃣ Mechanical Wave (Gelombang Mekanik)
**What it shows**: Different types of waves

**Controls**:
- **Frequency**: 0.5-3.0 Hz (default 1.0)
- **Amplitude**: 10-60 px (default 30)
- **Wave Type**: Sine / Square / Triangle

**Button**: Click to **"Start"** or **"Pause"**

**What to try**:
- Change frequency - waves get tighter/looser
- Adjust amplitude - waves get taller/shorter
- Try different waveforms

**Formula**: `y = A×sin(2π/λ × x - 2π×f × t)`

---

## 💡 Key Concepts

### Projectile Motion
```
Maximum Range occurs at 45° angle
Time to max height = v×sin(θ)/g
Horizontal range = v²×sin(2θ)/g
```

### Orbital Motion
```
Faster speed → planets orbit faster
More planets → see multiple orbits at once
Closer to sun → faster orbital speed
```

### Mechanical Waves
```
Frequency (Hz) = oscillations per second
Amplitude (px) = height of wave
Wave speed = wavelength × frequency
Wavelength gets smaller when frequency increases
```

---

## 🎮 Control Guide

### Sliders
- **Drag left/right** to change values
- **Real-time value** shown on right of slider
- Changes affect animation **instantly**

### Buttons
- **Start/Pause**: Begin or stop animation
- **Reset**: Restart simulation with current settings

### Dropdown (Wave only)
- **Sine Wave**: Smooth curved oscillation
- **Square Wave**: Sharp up-down transitions
- **Triangle Wave**: Linear rise and fall

---

## 🎨 Visual Indicators

### Colors
| Color | Meaning |
|-------|---------|
| Blue | Motion trajectory or wave curves |
| Red | Moving object or wave amplitude |
| Green | Velocity vector |
| Yellow | Central star (sun) |
| Multicolor | Different planets |

### Visual Effects
- **Glow**: Indicates light source or important object
- **Dashed lines**: Reference guides (orbits, equilibrium)
- **Grid**: Wavelength markers
- **Dots**: Sample points on the wave

---

## 📱 Mobile Tips

1. **Landscape mode** recommended for better view
2. **Touch sliders** to adjust values
3. **Tap buttons** to control simulations
4. Canvas scales to fit your screen

---

## 🌍 Language Support

### Indonesian
- UI labels in Indonesian
- All sliders and buttons labeled
- Physics terms in Indonesian

### English
- Click language button to switch to English
- All UI updates immediately
- Same physics, different language

---

## ⚡ Performance Tips

1. **Smooth animation** = happy learning!
2. **Close other tabs** if animation stutters
3. **Fullscreen mode** for better immersion
4. **Desktop/laptop** recommended for smoother experience

---

## 🧮 Physics Equations Cheat Sheet

### Projectile Motion
```
x(t) = v₀ × cos(θ) × t
y(t) = v₀ × sin(θ) × t - ½ × g × t²

vₓ(t) = v₀ × cos(θ)
vᵧ(t) = v₀ × sin(θ) - g × t

Max height = v₀² × sin²(θ) / (2g)
Range = v₀² × sin(2θ) / g
Time of flight = 2 × v₀ × sin(θ) / g
```

### Orbital Motion
```
F = G × M × m / r²        [Gravitational Force]
a = F / m                  [Acceleration]
r(t+dt) = r(t) + v(t)×dt [Position Update]

For circular orbit: v = √(GM/r)
Angular velocity: ω = v/r
```

### Mechanical Waves
```
y(x,t) = A × sin(2π/λ × x - 2π×f × t)

Wavelength: λ
Frequency: f (Hz) = 1/T (T = period)
Wave speed: v = λ × f
Angular frequency: ω = 2π × f
Wave number: k = 2π / λ
```

---

## 🎓 Learning Activities

### Activity 1: Projectile Optimization
**Goal**: Find the angle that gives maximum range

1. Try different angles from 10° to 80°
2. Record the range for each angle
3. Notice the peak at 45°
4. Understand why: sin(2×45°) = sin(90°) = 1 (maximum)

### Activity 2: Orbital Patterns
**Goal**: Understand multi-body orbital mechanics

1. Set planet count to 1, watch single orbit
2. Increase to 3, notice different speeds
3. Increase to 5, see complex system
4. Vary speed to observe scaling

### Activity 3: Wave Analysis
**Goal**: Learn frequency-wavelength relationship

1. Start with sine wave, frequency = 1 Hz
2. Increase frequency to 2 Hz → wavelength halves
3. Increase to 3 Hz → wavelength thirds
4. Try different waveforms to see the difference

---

## ❓ Troubleshooting

### Problem: Animation won't start
**Solution**: 
- Click the button again (maybe already running)
- Refresh page if stuck
- Try different browser

### Problem: Canvas looks empty
**Solution**:
- Check if dark mode is enabled
- Try switching to light mode
- Canvas should be visible in both modes

### Problem: Sliders not responding
**Solution**:
- Refresh the page
- Try different browser
- Check JavaScript is enabled

### Problem: UI text in wrong language
**Solution**:
- Switch language button twice
- Reload page
- Check browser language settings

---

## 📈 What Each Simulation Teaches

### Projectile Motion
✅ **Understands**:
- Parabolic motion path
- Independence of x and y motion
- Effect of angle and velocity on range
- Gravitational acceleration

### Orbital Motion
✅ **Understands**:
- Centripetal acceleration
- Gravitational force
- Kepler's laws of motion
- Multi-body systems

### Mechanical Wave
✅ **Understands**:
- Frequency and wavelength
- Wave speed relationship
- Periodic motion
- Different waveform types

---

## 🔗 Related Topics in App

**For deeper physics knowledge**, also check:
- **Physics Topics**: Detailed theory and history
- **Physics Tools**: Quick calculators for formulas
- **Physics Simulations**: This page (animations)

---

## ⏱️ Typical Session Times

| Activity | Time | Difficulty |
|----------|------|-----------|
| Quick demo | 2-5 min | Easy |
| Single simulation | 5-10 min | Easy |
| Compare parameters | 10-15 min | Medium |
| Full exploration | 20-30 min | Medium |
| Deep learning | 30+ min | Hard |

---

## 🎯 Best Practices

✅ **Do**:
- Experiment with extreme values
- Compare different parameters
- Pause and observe carefully
- Try predictions before changing values
- Take notes on observations

❌ **Don't**:
- Spam buttons (it's fine, but unnecessary)
- Expect perfectly accurate physics (educational simplifications)
- Run on very old devices (may be slow)
- Expect 3D (this is 2D for simplicity)

---

## 💾 Saving/Recording

**This is a web app** - nothing is saved automatically

**To save your learning**:
- Take screenshots of interesting simulations
- Record videos of animations
- Take notes on findings
- Sketch the trajectories you see

---

## 🌟 Pro Tips

1. **Pause mechanics**: Great for frame-by-frame analysis (wave only)
2. **Extreme values**: See what happens at min/max slider positions
3. **Real-world context**: Think of real examples for each simulation
4. **Compare settings**: Run same simulation with different parameters
5. **Teach others**: Use simulations to explain physics concepts

---

## 📊 Comparison Table

| Feature | Projectile | Orbital | Wave |
|---------|-----------|---------|------|
| Start type | Click button | Auto-start | Auto-start |
| Parameter count | 3 | 2 | 3 |
| Pause available | No | Reset only | Yes |
| Physics accuracy | High | Medium | Medium |
| Difficulty | Medium | Hard | Medium |
| Fastest learning | 5 min | 10 min | 5 min |

---

## 🎓 Educational Standards

These simulations address:
- **Kinematics**: Motion and forces
- **Dynamics**: Gravitational interactions
- **Waves**: Periodic motion and propagation
- **STEM Learning**: Hands-on physics exploration

---

**Last Updated**: 2024
**Version**: Quick Reference v1.0
**Perfect for**: Students, teachers, physics enthusiasts

💡 **Tip**: Bookmark this page for quick reference while exploring!

