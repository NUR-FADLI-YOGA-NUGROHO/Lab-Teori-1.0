# Physics Simulations Testing Guide

## Quick Start Testing

### 1. Test Tab Switching (2 minutes)
1. Open the application in browser
2. Navigate to "Simulasi Fisika" / "Physics Simulations" section
3. **Expected:** You should see 3 tabs: Projectile Motion, Orbital Motion, Mechanical Waves
4. Click each tab one by one
5. **Expected:** 
   - Orbital and Wave simulations should auto-start with animation
   - Projectile Motion displays static canvas (wait for Start button)
   - Smooth tab transitions with slide-up animation

### 2. Test Projectile Motion (5 minutes)
1. Click on "Projectile Motion" tab
2. Verify you see three sliders and one button
3. Test slider updates:
   - Drag "Launch Angle" slider → Value should update (0-90°)
   - Drag "Initial Velocity" slider → Value should update (5-50 m/s)
   - Drag "Gravity" slider → Value should update (5-20 m/s²)
4. Click "Start Simulation" button
5. **Expected:**
   - Blue parabolic trajectory arc appears
   - Red ball moves along the path
   - Green velocity vector visible
   - Time and distance values update on canvas
   - Animation ends when ball hits ground
6. Change slider values and click Start again
   - 45° angle should give maximum range
   - Lower gravity should create higher trajectory
   - Higher velocity should increase range

### 3. Test Orbital Motion (5 minutes)
1. Click on "Orbital Motion" tab
2. **Expected:** Simulation auto-starts immediately
3. **Verify visualization:**
   - Yellow sun in center with glow effect
   - Colored planets orbiting at different distances
   - White orbital path circles
   - Planets maintain their orbits
4. Test planet count slider (1-5)
   - Move slider to 1 → Only 1 planet visible
   - Move to 3 → 3 planets visible
   - Move to 5 → All 5 planets visible
   - **Expected:** Animation adjusts instantly
5. Test orbital speed slider (0.1-1.0×)
   - Set to 0.1 → Planets move very slowly
   - Set to 1.0 → Planets orbit fast
   - **Expected:** Smooth speed adjustment
6. Click "Reset Simulation" button
   - **Expected:** Planets return to starting positions, animation restarts

### 4. Test Mechanical Wave (5 minutes)
1. Click on "Mechanical Wave" tab
2. **Expected:** Wave simulation auto-starts with sine wave
3. **Verify visualization:**
   - Red wavy curve drawn on canvas
   - Blue dots at regular intervals
   - Grid lines and center reference line
   - Frequency, amplitude, wavelength, and wave speed displayed
4. Test frequency slider (0.5-3.0 Hz)
   - Increase frequency → Waves get closer together
   - Decrease frequency → Waves get farther apart
   - **Expected:** Wave animation updates in real-time
5. Test amplitude slider (10-60 px)
   - Increase amplitude → Waves get taller
   - Decrease amplitude → Waves get shorter
   - **Expected:** Wave height changes instantly
6. Test wave type dropdown:
   - Select "Sine Wave" → Smooth curved wave
   - Select "Square Wave" → Sharp up/down transitions
   - Select "Triangle Wave" → Linear slopes
   - **Expected:** Waveform changes instantly
7. Click "Pause" button
   - **Expected:** Animation stops, button text changes
8. Click button again (now says "Start")
   - **Expected:** Animation resumes

---

## Detailed Physics Verification Tests

### Projectile Motion Physics Accuracy

**Test 1: Maximum Range (45° angle)**
1. Set Launch Angle to 45°
2. Set Initial Velocity to 30 m/s
3. Set Gravity to 9.8 m/s²
4. Click Start
5. **Expected calculation:**
   - Max range = v²sin(2θ)/g = 900×sin(90°)/9.8 ≈ 91.8 m
   - Time of flight ≈ 2×v×sin(θ)/g ≈ 4.3 s
   - Visual: Trajectory should be perfectly symmetric
   - Landing distance should be similar to calculated range

**Test 2: High Angle Launch (80°)**
1. Set Launch Angle to 80°
2. Keep Velocity 30 m/s, Gravity 9.8
3. Click Start
4. **Expected:**
   - Maximum height should be very large
   - Range should be small
   - Time of flight should be long
   - Trajectory should be steep and narrow

**Test 3: Low Gravity (Moon)**
1. Set Gravity to 1.62 m/s² (Moon gravity)
2. Keep Angle 45°, Velocity 30 m/s
3. Click Start
4. **Expected:**
   - Much higher arc (lower gravity pulls less)
   - Much longer range
   - Longer flight time
   - Trajectory should be more stretched

**Test 4: Extreme Parameters**
1. Set Angle to 0° (horizontal launch)
   - **Expected:** Ball should immediately fall
   - Range should be minimal
2. Set Angle to 90° (vertical launch)
   - **Expected:** Ball should go straight up and down
   - Range should be zero
   - Max height = v²/(2g)

### Orbital Motion Physics Accuracy

**Test 1: Single Planet Orbit**
1. Set Number of Planets to 1
2. Set Orbital Speed to 1.0×
3. **Expected:**
   - Planet should complete full orbit in ~360-400 frames
   - Orbit should be perfectly circular
   - Planet should never change its orbital radius
   - No wobbling or drift

**Test 2: Multi-Planet System Stability**
1. Set Number of Planets to 5
2. Set Orbital Speed to 0.5×
3. Watch for 30+ seconds
4. **Expected:**
   - All 5 planets should maintain their orbits
   - Inner planets orbit faster than outer planets
   - No collisions between planets
   - No decay of orbits over time

**Test 3: Speed Scaling**
1. Set Number of Planets to 3
2. Record time for 1st planet to complete orbit at speed 1.0×
3. Change speed to 0.5×
4. Time should be approximately 2× longer
5. Change speed to 0.1×
6. Time should be approximately 10× longer

### Wave Motion Physics Accuracy

**Test 1: Frequency-Wavelength Relationship**
1. Set Wavelength in code to known value (e.g., 80 px)
2. Set Frequency to 1.0 Hz
3. Calculate wave speed = 80 × 1.0 = 80 px/s
4. **Expected:** Wave speed displayed on canvas should match
5. Change Frequency to 2.0 Hz
6. Wave speed should double to 160 px/s

**Test 2: Amplitude Verification**
1. Set Amplitude to 30 px
2. Observe maximum height above center line
3. Should be approximately 30 pixels
4. Change Amplitude to 60 px
5. Height should double to approximately 60 pixels

**Test 3: Waveform Correctness**
- **Sine Wave:** Smooth, continuous, symmetrical oscillation
- **Square Wave:** Flat top and bottom, sharp vertical transitions
- **Triangle Wave:** Linear rise and fall, symmetrical

---

## Browser Compatibility Testing

### Chrome (Latest)
- [ ] All three simulations display correctly
- [ ] Smooth animation (60fps)
- [ ] Canvas graphics render properly
- [ ] All controls responsive to input
- [ ] No console errors

### Firefox (Latest)
- [ ] All simulations functional
- [ ] Animation smooth
- [ ] Canvas rendering correct
- [ ] Check for any visual glitches

### Safari (macOS/iOS)
- [ ] Canvas implementation compatible
- [ ] Touch events work on iPad
- [ ] Performance acceptable
- [ ] No rendering artifacts

### Edge (Latest)
- [ ] Full compatibility
- [ ] Performance equivalent to Chrome
- [ ] No stability issues

---

## Mobile Responsiveness Testing

### Portrait Orientation
1. Open application on mobile phone in portrait mode
2. Navigate to Simulations section
3. **Expected:**
   - Canvas scales to fit screen width
   - All sliders accessible
   - Buttons clickable
   - Tab switching works
   - Text readable

### Landscape Orientation
1. Rotate phone to landscape
2. **Expected:**
   - Canvas uses available width/height
   - Layout adjusts properly
   - No horizontal scrolling
   - All controls still accessible

### Tablet Testing (iPad)
1. Open in Safari on iPad
2. Test landscape orientation (wider screen)
3. **Expected:**
   - Canvas scales appropriately
   - Better viewing experience with larger screen
   - Grid layout adjusts for wider display

### Touch Controls
1. Test sliders with touch/swipe
2. **Expected:**
   - Smooth dragging
   - Values update while dragging
   - Buttons clickable with single tap

---

## Dark Mode Testing

### Dark Theme Verification
1. Enable dark mode in application settings
2. Navigate to Simulations
3. **Verify each simulation:**

**Projectile Motion:**
- [ ] Canvas background: Light cyan-blue gradient
- [ ] Ground line visible (brown)
- [ ] Trajectory arc visible (blue)
- [ ] Projectile ball visible (red)
- [ ] Text readable (dark color on light background)

**Orbital Motion:**
- [ ] Canvas background: Dark gradient (gray-900 to black)
- [ ] Sun visible (yellow/gold)
- [ ] Planets visible (distinct colors)
- [ ] Orbits visible (white dashed)
- [ ] Readable in dark theme

**Mechanical Wave:**
- [ ] Canvas background: Dark gray
- [ ] Wave curve visible (red line)
- [ ] Grid lines visible
- [ ] Points visible (blue)
- [ ] Text readable

### Light Mode Verification
1. Switch to light mode
2. Verify all canvases readable
3. Check contrast of text and elements

---

## Internationalization Testing

### Indonesian Language
1. Set application language to Indonesian
2. Navigate to Simulations
3. **Verify all labels:**
   - Section title: "Simulasi Fisika Interaktif"
   - Tabs: "Gerak Parabola", "Gerak Orbit", "Gelombang Mekanik"
   - Slider labels in Indonesian
   - Button text in Indonesian
   - Canvas text in Indonesian (if applicable)

### English Language
1. Set application language to English
2. Navigate to Simulations
3. **Verify all labels:**
   - Section title: "Interactive Physics Simulations"
   - Tabs: "Projectile Motion", "Orbital Motion", "Mechanical Waves"
   - Slider labels in English
   - Button text in English
   - Canvas text in English

### Language Switching
1. While in Simulations section, switch language
2. **Expected:**
   - All UI updates instantly
   - Simulation continues running (unaffected)
   - Values remain the same

---

## Performance Testing

### Frame Rate Monitoring
1. Open browser DevTools (F12)
2. Go to Performance tab
3. Start recording
4. Run each simulation for 10 seconds
5. **Expected:**
   - 60 FPS (or close to it)
   - No dropped frames
   - Smooth animation visually

### CPU Usage
1. Open System Monitor (Windows Task Manager)
2. Watch CPU usage while running simulations
3. **Expected:**
   - Reasonable CPU (not maxed out)
   - Browser thread utilization ~20-40%
   - No thermal throttling

### Memory Usage
1. Open DevTools → Memory tab
2. Take heap snapshot before simulation
3. Run simulation for 30 seconds
4. Take another snapshot
5. **Expected:**
   - Memory stable
   - No continuous growth
   - No memory leaks

### Long-Running Test
1. Set orbital motion to run for 5+ minutes
2. Monitor memory and performance
3. **Expected:**
   - Performance remains constant
   - No degradation over time
   - Memory doesn't continuously increase

---

## Edge Cases & Error Handling

### Invalid Input Handling
1. Test slider extremes
   - Min value → Animation should work
   - Max value → Animation should work
   - **Expected:** No crashes or errors

### Rapid Parameter Changes
1. Quickly adjust sliders while animation running
2. **Expected:**
   - Animation updates smoothly
   - No lag or stuttering
   - No animation crashes

### Tab Switching During Animation
1. Start Projectile animation
2. Switch to Orbital tab while animation running
3. **Expected:**
   - Projectile animation stops
   - Orbital animation starts
   - No visual artifacts or overlap

### Window Resize
1. Start simulation
2. Resize browser window
3. **Expected:**
   - Canvas may redraw but continues animation
   - No major visual issues
   - Animation recovers smoothly

### Multiple Simulations Simultaneously (not typical)
1. In browser console, start multiple animations
2. **Expected:**
   - Only one runs smoothly (others should be canceled)
   - No performance degradation

---

## Test Report Template

```
Date: ___________
Tester: ___________
Browser: ___________ Version: ___________
Device: ___________ OS: ___________

FUNCTIONALITY TESTS
Projectile Motion:
  ☐ Slider updates working
  ☐ Start button launches animation
  ☐ Trajectory physics looks correct
  ☐ Animation completes properly

Orbital Motion:
  ☐ Auto-starts on tab switch
  ☐ Planet count slider works
  ☐ Speed slider works
  ☐ Reset button functions

Mechanical Wave:
  ☐ Auto-starts on tab switch
  ☐ Frequency slider works
  ☐ Amplitude slider works
  ☐ Wave type dropdown works
  ☐ Pause/play toggle works

TAB NAVIGATION
  ☐ All tabs clickable
  ☐ Content switches correctly
  ☐ Smooth transitions

INTERNATIONALIZATION
  ☐ Indonesian text displays
  ☐ English text displays
  ☐ Language switching works
  ☐ All labels translated

DARK MODE
  ☐ Projectile readable
  ☐ Orbital readable
  ☐ Wave readable

PERFORMANCE
  ☐ 60 FPS achieved
  ☐ No stuttering
  ☐ Reasonable CPU usage
  ☐ No memory leaks

NOTES:
___________________________________________
___________________________________________

ISSUES FOUND:
1. ___________________________________________
2. ___________________________________________

OVERALL STATUS: ☐ PASS  ☐ FAIL

Signature: ___________ Date: ___________
```

---

## Regression Testing Checklist

Use this checklist after making any code changes to simulations:

- [ ] Physics equations still produce correct results
- [ ] Canvas rendering looks unchanged
- [ ] Animations are smooth (no new stutters)
- [ ] All sliders still update values
- [ ] All buttons still trigger correct actions
- [ ] Tab switching works as before
- [ ] No new console errors
- [ ] Dark mode still works
- [ ] Both languages still display correctly
- [ ] No new memory leaks
- [ ] Mobile layout still responsive

---

## Known Test Issues

1. **Animation Timing:** Frame rate varies by device/browser - perfect 60fps not guaranteed on all systems
2. **Touch Events:** Some mobile browsers may have delayed response to slider input
3. **Canvas Scaling:** Very high pixel density displays may show aliasing
4. **Wave Type Options:** Different browsers may render slightly differently
5. **Language Switching:** Page refresh not needed but may take 1-2 seconds to update all text

---

**Last Updated**: 2024
**Test Suite Version**: 1.0
**Minimum Test Coverage**: All above tests recommended for production release

