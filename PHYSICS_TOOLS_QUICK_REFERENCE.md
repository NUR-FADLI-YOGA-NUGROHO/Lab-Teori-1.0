# 🔬 Physics Tools - Quick Reference Guide

## 📌 Quick Start

### Accessing Physics Tools
1. **Navigate:** Click "Alat Fisika" (Indonesian) or "Physics Tools" (English) in sidebar
2. **Select Calculator:** Click on desired calculator tab
3. **Enter Values:** Input numbers with appropriate units
4. **Calculate:** Click "Hitung" (ID) or "Calculate" (EN) button
5. **View Result:** Green result appears below the button

---

## 📐 Calculator Formulas & Units

### 1. **Kinetic Energy** ⚡
```
Formula: EK = ½ × m × v²
Units: Joules (J)

Inputs:
  • Mass (m) → Kilograms (kg)
  • Velocity (v) → Meters per second (m/s)

Quick Example:
  m = 2 kg, v = 5 m/s
  EK = 0.5 × 2 × 25 = 25 J
```

### 2. **Potential Energy** 📈
```
Formula: EP = m × g × h
Units: Joules (J)

Inputs:
  • Mass (m) → Kilograms (kg)
  • Height (h) → Meters (m)
  • Gravity (g) → m/s² (Default: 9.8)

Quick Example:
  m = 10 kg, h = 5 m, g = 9.8 m/s²
  EP = 10 × 9.8 × 5 = 490 J
```

### 3. **Momentum** 🚀
```
Formula: p = m × v
Units: Kilogram-meters per second (kg·m/s)

Inputs:
  • Mass (m) → Kilograms (kg)
  • Velocity (v) → Meters per second (m/s)

Quick Example:
  m = 3 kg, v = 4 m/s
  p = 3 × 4 = 12 kg·m/s
```

### 4. **Force** 💪
```
Formula: F = m × a
Units: Newtons (N)

Inputs:
  • Mass (m) → Kilograms (kg)
  • Acceleration (a) → Meters per second squared (m/s²)

Quick Example:
  m = 5 kg, a = 2 m/s²
  F = 5 × 2 = 10 N
```

### 5. **Power** ⚙️
```
Formula: P = W / t
Units: Watts (W)

Inputs:
  • Work (W) → Joules (J)
  • Time (t) → Seconds (s)

Quick Example:
  W = 100 J, t = 5 s
  P = 100 ÷ 5 = 20 W
```

---

## 🎯 Common Physics Scenarios

### Scenario 1: A Car Moving
**Problem:** A 1000 kg car moves at 20 m/s. What is its kinetic energy?
**Solution:**
- Go to: Kinetic Energy calculator
- Mass = 1000, Velocity = 20
- Result: **200,000 J** (200 kJ)

### Scenario 2: An Object at Height
**Problem:** A 50 kg package is on a shelf 2 meters high. Calculate potential energy.
**Solution:**
- Go to: Potential Energy calculator
- Mass = 50, Height = 2, Gravity = 9.8
- Result: **980 J**

### Scenario 3: Force Needed to Accelerate
**Problem:** How much force is needed to accelerate a 100 kg object at 3 m/s²?
**Solution:**
- Go to: Force calculator
- Mass = 100, Acceleration = 3
- Result: **300 N**

### Scenario 4: Power of an Electric Device
**Problem:** A device does 1500 J of work in 10 seconds. What is its power?
**Solution:**
- Go to: Power calculator
- Work = 1500, Time = 10
- Result: **150 W**

---

## ⚠️ Input Rules & Validation

| Input Type | Rule | Example |
|-----------|------|---------|
| **Mass** | Must be ≥ 0 | 5, 10.5, 0 ✓ |
| **Velocity** | Must be ≥ 0 | 10, 5.5, 0 ✓ |
| **Height** | Must be ≥ 0 | 2, 1.5, 0 ✓ |
| **Gravity** | Must be > 0 | 9.8, 10, 3.71 ✓ |
| **Acceleration** | Any number | 2, -3, 0 ✓ |
| **Work** | Must be ≥ 0 | 100, 50.5, 0 ✓ |
| **Time** | Must be > 0 | 5, 2.5, 0.1 ✓ |

### Invalid Inputs (Will Show Error)
```
❌ Empty field
❌ Text instead of numbers
❌ Negative mass, velocity, height, work
❌ Zero time value
❌ Zero gravity value
```

---

## 🌐 Language Toggle

### **To Switch Language:**
1. Click language button in header (ID/EN flag or button)
2. All text updates immediately:
   - Calculator names
   - Input labels
   - Button text
   - Results display
   - Error messages

### **Supported Languages:**
- 🇮🇩 **Indonesian** (Bahasa Indonesia)
- 🇬🇧 **English** (English)

---

## 🎨 Visual Indicators

### **Tab Colors**
- **Active Tab:** Blue/Indigo color with underline
- **Inactive Tab:** Gray text, hover changes to blue

### **Result Colors**
- 🟢 **Green:** Successful calculation
- 🔴 **Red:** Error or invalid input

### **Input Focus**
- **Border:** Changes to blue when focused
- **Shadow:** Light blue glow around input

---

## ⌨️ Keyboard Navigation

| Action | Key |
|--------|-----|
| Move to next input | `Tab` |
| Move to previous input | `Shift + Tab` |
| Click button | `Enter` (when focused) |
| Switch tabs | Click or `Tab` to button, then `Enter` |

---

## 🔧 Troubleshooting

### **Problem:** Result not showing
**Solution:** 
- Check all fields have valid numbers
- Look for red error message
- Ensure values meet input rules above

### **Problem:** Wrong result displayed
**Solution:**
- Verify you entered correct values
- Check units are SI standard
- Confirm formula in tooltip matches expected formula

### **Problem:** Text in wrong language
**Solution:**
- Click language toggle button
- Refresh page if toggle not working
- Check browser language settings

### **Problem:** Calculator looks broken on mobile
**Solution:**
- Rotate device to landscape
- Zoom out if text too large
- Try different browser
- Clear cache and reload

### **Problem:** Dark mode colors hard to read
**Solution:**
- Click dark mode toggle to switch
- Adjust browser zoom level
- Check system dark mode is enabled correctly

---

## 📊 SI Units Quick Reference

| Quantity | Unit | Symbol | Base Units |
|----------|------|--------|-----------|
| Mass | Kilogram | kg | Base |
| Length/Height | Meter | m | Base |
| Time | Second | s | Base |
| Velocity | Meter per second | m/s | m·s⁻¹ |
| Acceleration | Meter per second squared | m/s² | m·s⁻² |
| Force | Newton | N | kg·m·s⁻² |
| Energy/Work | Joule | J | kg·m²·s⁻² |
| Power | Watt | W | kg·m²·s⁻³ |
| Momentum | Kilogram-meter per second | kg·m/s | kg·m·s⁻¹ |

---

## 🔢 Gravity Values by Location

Use these values when calculating potential energy:

| Location | Gravity (m/s²) |
|----------|-----------------|
| **Earth (Sea Level)** | 9.81 |
| **Moon** | 1.62 |
| **Mars** | 3.71 |
| **Jupiter** | 24.79 |
| **Sun** | 273.95 |

---

## 📝 Example Problems & Solutions

### **Problem 1: Kinetic Energy**
A 500g ball is thrown at 15 m/s. What's the kinetic energy?

```
Given: m = 0.5 kg (convert 500g), v = 15 m/s
Formula: EK = ½ × m × v²
Calculation: EK = 0.5 × 0.5 × 15² = 0.5 × 0.5 × 225 = 56.25 J

Using Calculator:
1. Select "Kinetic Energy" tab
2. Mass = 0.5
3. Velocity = 15
4. Click Calculate
5. Result: 56.25 J ✓
```

### **Problem 2: Potential Energy**
A 20 kg object is lifted 3 meters. How much potential energy?

```
Given: m = 20 kg, h = 3 m, g = 9.8 m/s²
Formula: EP = m × g × h
Calculation: EP = 20 × 9.8 × 3 = 588 J

Using Calculator:
1. Select "Potential Energy" tab
2. Mass = 20
3. Height = 3
4. Gravity = 9.8 (default)
5. Click Calculate
6. Result: 588 J ✓
```

### **Problem 3: Force**
What force is needed to accelerate a 2000 kg car at 0.5 m/s²?

```
Given: m = 2000 kg, a = 0.5 m/s²
Formula: F = m × a
Calculation: F = 2000 × 0.5 = 1000 N

Using Calculator:
1. Select "Force" tab
2. Mass = 2000
3. Acceleration = 0.5
4. Click Calculate
5. Result: 1000 N ✓
```

---

## 💡 Tips & Tricks

✅ **Always use SI units** - Calculator expects meters, kilograms, seconds
✅ **Convert units before entering** - 5 cm = 0.05 m
✅ **Use decimal points** - 2.5 instead of 2,5
✅ **Check formula tooltip** - Hover over formula text for explanation
✅ **Take note of units in result** - J, N, W, kg·m/s
✅ **Validate your answer** - Does result make physical sense?
✅ **Use for homework** - Great for checking calculations
✅ **Practice problems** - Solve many problems to build understanding

---

## 📞 Getting Help

**In-app:**
- Hover over input labels for unit information
- Read formula display for calculation method
- Check error messages (in your language)

**Documentation:**
- Full documentation: `PHYSICS_TOOLS_DOCUMENTATION.md`
- Testing guide: `PHYSICS_TOOLS_TESTING_GUIDE.md`

**Common Issues:**
- See Troubleshooting section above

---

## 🎓 Learning Resources

### **Concepts to Study**
- [ ] Kinetic Energy and Work-Energy Theorem
- [ ] Potential Energy and Conservation of Energy
- [ ] Momentum and Impulse
- [ ] Newton's Laws of Motion
- [ ] Work, Energy, and Power

### **Physics Formulas to Memorize**
1. E = mc² (Einstein's mass-energy equivalence)
2. F = ma (Newton's second law)
3. p = mv (Momentum)
4. W = F×d (Work)
5. P = W/t (Power)
6. E = ½mv² (Kinetic energy)
7. E = mgh (Potential energy)

---

**Last Updated:** November 13, 2025  
**Version:** 1.0  
**Status:** ✅ Production Ready
