# QR Code Generator

A modern, responsive web application for generating QR codes with configurable data fields. Perfect for manufacturing, inventory tracking, and product labeling applications.

## 🚀 Features

- **Dynamic Form Generation**: Form fields are automatically generated from a JSON configuration file
- **Multiple QR Code Generation**: Generate multiple QR codes in batch with incremental serial numbers
- **PDF Export**: Export generated QR codes as a PDF document
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- **Modern UI**: Beautiful gradient design with smooth animations and hover effects
- **Form Validation**: Built-in validation to ensure all required fields are completed
- **Configurable**: Easy to customize fields and options through the configuration file

## 📋 Prerequisites

- A modern web browser (Chrome, Firefox, Safari, Edge)
- A local web server (for loading the configuration file)

## 🛠️ Installation

1. **Clone or download** the project files to your local machine
2. **Start a local web server** in the project directory:

   **Using Python:**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   ```

   **Using Node.js:**
   ```bash
   npx http-server
   ```

   **Using PHP:**
   ```bash
   php -S localhost:8000
   ```

3. **Open your browser** and navigate to `http://localhost:8000`

## 📁 Project Structure

```
qr_generator_app/
├── qr_generator.html    # Main application file
├── styles.css          # CSS styles and responsive design
├── config.json         # Configuration file for form fields
└── README.md           # This documentation file
```

## ⚙️ Configuration

The application uses `config.json` to define form fields. Here's the structure:

```json
{
  "fields": [
    {
      "name": "Field Name",
      "type": "field_type",
      "options": ["option1", "option2", "option3"]
    }
  ]
}
```

### Field Types

- **`dropdown`**: Creates a select dropdown with predefined options
- **`text`**: Creates a text input field
- **`number`**: Creates a number input field (1-100)
- **`date`**: Creates a date picker
- **`email`**: Creates an email input field

### Example Configuration

```json
{
  "fields": [
    {
      "name": "Operator ID",
      "type": "dropdown",
      "options": ["OP1", "OP2", "OP3"]
    },
    {
      "name": "Machine ID",
      "type": "dropdown",
      "options": ["M1", "M2", "M3"]
    },
    {
      "name": "Dimension",
      "type": "dropdown",
      "options": ["Small", "Medium", "Large"]
    },
    {
      "name": "Date of Manufacturing",
      "type": "date"
    },
    {
      "name": "Count",
      "type": "number"
    }
  ]
}
```

## 🎯 Usage

### Basic Workflow

1. **Load the Application**: Open the HTML file in your browser
2. **Fill the Form**: Complete all required fields in the configuration form
3. **Generate QR Codes**: Click "Generate QR Codes" to create QR codes
4. **Export (Optional)**: Click "Export as PDF" to save as a PDF document

### QR Code Data Format

Each QR code contains JSON data with all form values plus a serial number:

```json
{
  "Operator ID": "OP1",
  "Machine ID": "M1", 
  "Dimension": "Small",
  "Date of Manufacturing": "2024-01-01",
  "Count": "5",
  "Serial": 1
}
```

### Features

- **Form Validation**: All fields are required and validated before generation
- **Clear Form**: Reset all fields and clear generated QR codes
- **Responsive Grid**: QR codes are displayed in a responsive grid layout
- **Hover Effects**: Interactive hover effects on QR code cards
- **Error Handling**: Graceful error handling for missing configuration files

## 🎨 Customization

### Styling

The application uses a separate `styles.css` file for all styling. Key customization points:

- **Colors**: Modify CSS custom properties for theme colors
- **Layout**: Adjust grid layouts and spacing
- **Typography**: Change fonts and text styling
- **Animations**: Customize hover effects and transitions

### Adding New Field Types

To add new field types, modify the `loadConfig()` function in the HTML file:

```javascript
// Add new field type handling
if (field.type === 'your_new_type') {
  input = document.createElement('input');
  input.type = 'your_input_type';
  // Add any additional properties
}
```

## 🔧 Technical Details

### Dependencies

- **QRious**: QR code generation library
- **html2pdf.js**: PDF export functionality
- **Modern CSS**: Grid, Flexbox, and CSS custom properties

### Browser Support

- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+

### Performance

- QR codes are generated client-side for fast performance
- PDF export uses high-quality settings for professional output
- Responsive design ensures optimal performance on all devices

## 🐛 Troubleshooting

### Common Issues

1. **Configuration not loading**: Ensure `config.json` exists and is valid JSON
2. **QR codes not generating**: Check that all required fields are filled
3. **PDF export issues**: Ensure QR codes are generated before exporting
4. **Styling not applied**: Verify `styles.css` is in the same directory

### Error Messages

- **"Error loading configuration"**: Check if `config.json` exists and is accessible
- **"Please fill in all required fields"**: Complete all form fields before generating
- **"Please generate QR codes first"**: Generate QR codes before PDF export

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For support or questions, please open an issue in the project repository.

---

**Made with ❤️ for efficient QR code generation** 