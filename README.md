# calculator
A modern, responsive web-based calculator built with HTML, CSS, and JavaScript. Features a sleek glass-morphism design with full keyboard support and smooth animations.


![Calculator Preview](https://img.shields.io/badge/Status-Complete-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

## ✨ Features

### Core Functionality
- **Basic Arithmetic Operations**: Addition (+), Subtraction (-), Multiplication (×), Division (/)
- **Real-time Display**: Instant feedback as you input numbers and operations
- **Decimal Support**: Handle floating-point calculations with precision
- **Error Handling**: Graceful handling of invalid operations and division by zero

### User Experience
- **Modern Glass-morphism Design**: Sleek, contemporary interface with blur effects
- **Responsive Layout**: Works seamlessly on desktop, tablet, and mobile devices
- **Smooth Animations**: Button hover effects and slide-in animations
- **Visual Feedback**: Different color schemes for operators, equals, and clear buttons

### Input Methods
- **Mouse/Touch Support**: Click or tap buttons for input
- **Full Keyboard Support**: Type numbers, operators, and use keyboard shortcuts

## 🎮 Keyboard Shortcuts

| Key | Action |
|-----|--------|
| 0-9 | Input digits |
| +, -, *, / | Mathematical operators |
| Enter or = | Calculate result |
| Escape or C | Clear display |
| Backspace | Delete last character |
| . | Decimal point |

## 🚀 Demo



## 📷 Screenshots

![Calculator Screenshot](screenshots/calculator-demo.png)

*Modern glass-morphism design with gradient background*

## 🛠️ Technologies Used

- **HTML5**: Structure and semantic markup
- **CSS3**: Styling, animations, and responsive design
  - CSS Grid for button layout
  - Flexbox for display alignment
  - CSS backdrop-filter for glass effect
  - CSS animations and transitions
- **Vanilla JavaScript**: Logic and interactivity
  - Event handling
  - DOM manipulation
  - Keyboard event listeners


## 🔧 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/simple-calculator.git
   cd simple-calculator
   ```

2. **Open in browser**
   - Simply open `index.html` in any modern web browser
   - Or use a local server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js (if you have it installed)
   npx http-server
   
   # Using VS Code Live Server extension
   # Right-click on index.html and select "Open with Live Server"
   ```

3. **Start calculating!**
   - No build process or dependencies required
   - Works offline once loaded

## 💻 Usage

### Basic Operations
1. **Input Numbers**: Click digit buttons (0-9) or type on keyboard
2. **Select Operation**: Click operator buttons (+, -, ×, /) or use keyboard
3. **Calculate**: Click equals (=) button or press Enter
4. **Clear**: Use C button or press Escape to clear display
5. **Delete**: Use ⌫ button or press Backspace to delete last character

### Advanced Features
- **Decimal Numbers**: Click . button or press period key
- **Continuous Calculations**: Result becomes the first operand for next calculation
- **Error Recovery**: Calculator shows "Error" for invalid operations, press C to continue

## 🎨 Design Features

### Visual Elements
- **Glass-morphism Effect**: Semi-transparent background with backdrop blur
- **Gradient Background**: Purple to blue gradient for modern look
- **Button Animations**: Hover effects with lift and glow
- **Color Coding**: 
  - White: Number buttons
  - Red: Operator buttons
  - Green: Equals button
  - Red: Clear buttons

### Responsive Design
- **Mobile-First**: Optimized for touch interfaces
- **Flexible Layout**: Adapts to different screen sizes
- **Touch-Friendly**: Large buttons with adequate spacing

## 🔍 Code Highlights

### Smart Input Handling
```javascript
function appendToDisplay(value) {
    // Prevent multiple decimal points
    if (value === '.' && currentInput.includes('.')) {
        return;
    }
    
    // Handle operator replacement
    const operators = ['+', '-', '*', '/'];
    const lastChar = currentInput.slice(-1);
    if (operators.includes(value) && operators.includes(lastChar)) {
        currentInput = currentInput.slice(0, -1) + value;
    }
}
```

### Safe Calculation
```javascript
function calculate() {
    try {
        let expression = currentInput.replace(/×/g, '*');
        let result = Function('"use strict"; return (' + expression + ')')();
        
        // Handle division by zero and invalid results
        if (!isFinite(result)) {
            currentInput = 'Error';
        } else {
            // Round to avoid floating point precision issues
            result = Math.round(result * 1000000000) / 1000000000;
            currentInput = result.toString();
        }
    } catch (error) {
        currentInput = 'Error';
    }
}
```

## 🐛 Known Issues & Limitations

- **Display Overflow**: Very long numbers may overflow display (handled with word-break)
- **Floating Point Precision**: JavaScript floating-point limitations (mitigated with rounding)
- **No Advanced Functions**: Currently supports only basic arithmetic operations

## 🚀 Future Enhancements

- [ ] **Scientific Mode**: Add advanced mathematical functions
- [ ] **Memory Functions**: M+, M-, MR, MC buttons
- [ ] **History**: Show calculation history
- [ ] **Themes**: Multiple color themes
- [ ] **Sound Effects**: Button click sounds
- [ ] **Percentage**: Add percentage calculations
- [ ] **Copy/Paste**: Clipboard integration
- [ ] **PWA**: Progressive Web App features

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the project
2. **Create** your feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Areas for Contribution
- Bug fixes and improvements
- New features and functionality
- UI/UX enhancements
- Documentation improvements
- Performance optimizations

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Your Name

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your Profile](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com
- Portfolio: [your-portfolio.com](https://your-portfolio.com)

## 🙏 Acknowledgments

- Inspired by modern calculator applications
- Glass-morphism design trend
- [CSS-Tricks](https://css-tricks.com/) for advanced CSS techniques
- [MDN Web Docs](https://developer.mozilla.org/) for JavaScript references
- [Google Fonts](https://fonts.google.com/) for typography

## 📊 Project Stats

![GitHub repo size](https://img.shields.io/github/repo-size/yourusername/simple-calculator)
![GitHub last commit](https://img.shields.io/github/last-commit/yourusername/simple-calculator)
![GitHub issues](https://img.shields.io/github/issues/yourusername/simple-calculator)
![GitHub stars](https://img.shields.io/github/stars/yourusername/simple-calculator)
![GitHub forks](https://img.shields.io/github/forks/yourusername/simple-calculator)

---

⭐ **If you found this project helpful, please consider giving it a star!**
