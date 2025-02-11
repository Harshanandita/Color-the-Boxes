# Color Picker Application

Welcome to the **Color Picker Application**! This project is a dynamic and interactive web-based tool that generates random colors for multiple boxes. Each box displays a color with a corresponding text that represents the color value. Users can copy these color values seamlessly to the clipboard with just a click.

---

## Demo

![Demo](assets/Sample.gif)

---

## Preview

Preview the website by visiting: [Preview](https://harshanandita.github.io/Color-the-Boxes/) 

---

## Features

- **Dynamic Color Change:** Each box changes its background and text color every second.
- **Copy to Clipboard:** Users can click on the text within the box to copy the displayed color value.
- **Smooth UI Updates:** Colors transition smoothly, providing a visually engaging experience.
- **Advanced UI Design:** Implemented clipboard feedback using CSS pseudo-elements like `::before` for better UX.

---

## 📂 Project Structure

```plaintext
Color the Boxes/
│
├── index.html          # Main HTML file
├── style.css           # CSS file for styling
├── script.js           # JavaScript file
├── README.md           # This README file
└── assets/             # Images, GIFs
    └── Sample.gif      # Sample GIF
```

---

### 🔧 File Descriptions
- **index.html:** Contains the structure and layout of the application.
- **style.css:** Styles for the color boxes and the overall page, including visual effects.
- **script.js:** Core logic for color generation, clipboard functionality, and event handling.

---

## 📋 Usage Instructions

1. Clone the repository to your local machine:
```bash
git clone https://github.com/Harshanandita/Color-the-Boxes.git
```

2. Open `index.html` in your preferred browser.

---

### 💻 How to Use
- **Viewing Colors:**
  - Open the application and watch as colors change dynamically.
- **Copying Colors:**
  - Click on the color text inside any box to copy the color value.
  - A "Copied" label appears temporarily to indicate success.

---

## Technical Details

### JavaScript Highlights
- **Color Generation:**
  ```javascript
  function getRandomColor(flag) {
      let color = Math.floor(Math.random() * 16777216).toString(16).padStart(6, '0');
      let opacity = Math.floor(Math.random() * 256).toString(16).padStart(2, '0');
      if (flag === false) return `#${color}`;
      return `#${color}${opacity}`;
  }
  ```
- **Clipboard Copy:**
  ```javascript
  navigator.clipboard.writeText(span.innerText)
      .then(() => {
          span.classList.add("copied");
          setTimeout(() => span.classList.remove("copied"), 2000);
      })
      .catch(error => console.error(error));
  ```
- **Event Handling:**
  ```javascript
  document.querySelectorAll(".box span").forEach(span => {
      span.addEventListener("click", () => {
          navigator.clipboard.writeText(span.innerText);
      });
  });
  ```

### CSS Highlights
- Clipboard feedback with pseudo-elements:
  ```css
  .box span::before {
      content: "Copy to clipboard";
      color: white;
  }
  .box span.copied::before {
      content: "Copied!";
  }
  ```

---

## Future Enhancements
- Add user-defined color generation intervals.
- Support for different color formats (RGB, HSL, etc.).
- Mobile-friendly layout improvements.

---

## Contributing
Contributions are welcome! Please feel free to submit a pull request or report any issues.

## 📜 License
This project is licensed under the MIT License. See the [LICENSE](https://opensource.org/licenses/MIT) file for details.

## 📬 Contact

- Author: Harsh Singh Raghuvanshi
- Email: singh01ha@gmail.com
- GitHub: Harshanandita