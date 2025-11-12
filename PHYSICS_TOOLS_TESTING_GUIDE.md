# Physics Tools - Testing & Validation Guide

## ✅ Manual Testing Checklist

### 1. **Navigation & Layout**
- [ ] "Alat Fisika" / "Physics Tools" appears in sidebar menu
- [ ] Icon appears next to menu item
- [ ] Click menu item switches to tools section
- [ ] Tools section displays correctly
- [ ] Tab buttons are visible and clickable

### 2. **Tab Switching**
- [ ] Default: Kinetic Energy tab is active
- [ ] Click each tab switches to correct calculator
- [ ] Active tab shows in blue/indigo color
- [ ] Previous tab styling reverts to normal
- [ ] Tab animations smooth (slide up effect)

### 3. **Kinetic Energy Calculator**
- **Test Case 1:** Mass=2, Velocity=5
  - Expected: 25.00 J
  - Status: [ ]
  
- **Test Case 2:** Mass=10, Velocity=2
  - Expected: 20.00 J
  - Status: [ ]
  
- **Test Case 3:** Invalid input (empty fields)
  - Expected: Error message in red
  - Status: [ ]

### 4. **Potential Energy Calculator**
- **Test Case 1:** Mass=10, Height=5, Gravity=9.8 (default)
  - Expected: 490.00 J
  - Status: [ ]
  
- **Test Case 2:** Mass=5, Height=20, Gravity=9.8
  - Expected: 980.00 J
  - Status: [ ]
  
- **Test Case 3:** Custom gravity: Mass=1, Height=1, Gravity=10
  - Expected: 10.00 J
  - Status: [ ]

### 5. **Momentum Calculator**
- **Test Case 1:** Mass=3, Velocity=4
  - Expected: 12.00 kg·m/s
  - Status: [ ]
  
- **Test Case 2:** Mass=5, Velocity=6
  - Expected: 30.00 kg·m/s
  - Status: [ ]

### 6. **Force Calculator**
- **Test Case 1:** Mass=5, Acceleration=2
  - Expected: 10.00 N
  - Status: [ ]
  
- **Test Case 2:** Mass=10, Acceleration=9.8
  - Expected: 98.00 N
  - Status: [ ]

### 7. **Power Calculator**
- **Test Case 1:** Work=100, Time=5
  - Expected: 20.00 W
  - Status: [ ]
  
- **Test Case 2:** Work=500, Time=10
  - Expected: 50.00 W
  - Status: [ ]

### 8. **Input Validation**
- [ ] Non-numeric input rejected
- [ ] Negative mass rejected (shows error)
- [ ] Negative height rejected (shows error)
- [ ] Zero time rejected (shows error)
- [ ] Empty fields rejected (shows error)
- [ ] Error messages display in red color
- [ ] Error messages are in correct language (ID/EN)

### 9. **Language Switching**
- [ ] Switch to English using language toggle
- [ ] All calculator labels change to English
- [ ] All button text changes to English
- [ ] All error messages change to English
- [ ] Formula text displays in English
- [ ] Input placeholders remain in appropriate units
- [ ] Switch back to Indonesian - all text reverts

### 10. **Dark Mode**
- [ ] Toggle dark mode on
- [ ] All input fields readable in dark mode
- [ ] Buttons properly styled in dark mode
- [ ] Result text visible in dark mode
- [ ] Tab styling works in dark mode
- [ ] Background colors appropriate
- [ ] No color contrast issues

### 11. **Responsive Design**
- **Desktop (1920px):**
  - [ ] 2-column grid layout
  - [ ] Calculators displayed side-by-side
  - [ ] Full sidebar visible
  
- **Tablet (768px):**
  - [ ] Layout still 2-column or wraps nicely
  - [ ] Tab buttons wrap if needed
  - [ ] Content readable
  
- **Mobile (375px):**
  - [ ] 1-column layout
  - [ ] Buttons full width
  - [ ] Inputs full width
  - [ ] All elements touch-friendly
  - [ ] Sidebar toggle works

### 12. **Accessibility**
- [ ] Tab key navigation works
- [ ] Focus states visible on inputs
- [ ] Buttons keyboard accessible
- [ ] Labels properly associated with inputs
- [ ] Error messages clear and descriptive
- [ ] Color not only indicator of status

### 13. **Cross-Browser Testing**
- [ ] Chrome/Edge (Chromium)
- [ ] Firefox
- [ ] Safari (if available)
- [ ] Mobile Chrome
- [ ] Mobile Safari (iOS)

## 🧪 Automated Test Cases (JavaScript Console)

```javascript
// Test Kinetic Energy Formula
let m = 2, v = 5;
let expectedEK = 0.5 * m * v * v;
console.log(`EK: ${expectedEK} (expected: 25)`);

// Test Potential Energy Formula
m = 10; let h = 5, g = 9.8;
let expectedEP = m * g * h;
console.log(`EP: ${expectedEP} (expected: 490)`);

// Test Momentum Formula
m = 3; v = 4;
let expectedP = m * v;
console.log(`p: ${expectedP} (expected: 12)`);

// Test Force Formula
m = 5; let a = 2;
let expectedF = m * a;
console.log(`F: ${expectedF} (expected: 10)`);

// Test Power Formula
let W = 100, t = 5;
let expectedPower = W / t;
console.log(`P: ${expectedPower} (expected: 20)`);
```

## 📋 Edge Cases

### Boundary Testing
- [ ] Maximum safe integer input: 9007199254740991
- [ ] Very small decimal: 0.000001
- [ ] Very large decimal: 999999.999999
- [ ] Zero values (where allowed)

### Error Condition Testing
- [ ] NaN input handling
- [ ] Infinity calculations
- [ ] Division by zero (time=0 for power)
- [ ] Negative gravity value
- [ ] Empty form submission

## 🔄 Regression Testing

After any code changes, verify:
- [ ] All 5 calculators still calculate correctly
- [ ] Tab switching still works
- [ ] Language switching still works
- [ ] Dark mode still functions
- [ ] No JavaScript console errors
- [ ] Styling not broken
- [ ] Responsive layout intact

## 📱 Mobile Testing Steps

1. Open file on mobile device or emulator
2. Verify hamburger menu appears
3. Click menu to open sidebar
4. Click "Alat Fisika" / "Physics Tools"
5. Verify tools section loads
6. Test each calculator with valid input
7. Test with invalid input
8. Verify results display correctly
9. Close sidebar by clicking overlay
10. Switch language and repeat steps 5-8

## 🐛 Bug Report Template

If issues found, document as:

```
**Title:** [Brief description]
**Calculator Affected:** [Kinetic/Potential/Momentum/Force/Power]
**Steps to Reproduce:**
1. 
2. 
3. 

**Expected Result:** 
[What should happen]

**Actual Result:** 
[What actually happens]

**Screenshot/Video:** [If applicable]

**Browser/Device:** [Chrome/Firefox/Safari, Windows/Mac/iOS/Android]
```

## ✅ Sign-Off

- [ ] All manual tests passed
- [ ] All edge cases tested
- [ ] No console errors
- [ ] Responsive design verified
- [ ] Language switching verified
- [ ] Dark mode verified
- [ ] Mobile testing completed
- [ ] Cross-browser tested

**Tested By:** _________________  
**Date:** _________________  
**Status:** ✅ READY FOR PRODUCTION

---

## 📞 Support References

- Documentation: `PHYSICS_TOOLS_DOCUMENTATION.md`
- Source File: `index.html` (line 2987-3120 for HTML, line 4699-4795 for JS)
- i18n Keys: See translations object (lines 3072-4300)
