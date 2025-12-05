# VLinkPay Embed Demo

A simple demonstration of integrating VLinkPay payment services into a web application using an embedded iframe popup.

## 🚀 Demo Overview

This demo showcases how to embed VLinkPay's interface into your website using a popup overlay. Users can initiate payments without leaving your application.

## 📋 Features

- **Popup Integration**: Clean popup overlay with VLinkPay iframe
- **Event Handling**: Listen for sign-in and registration events
- **Responsive Design**: Works on desktop and mobile devices
- **Easy Integration**: Simple HTML, CSS, and JavaScript implementation

## 🛠️ Files Structure

```
vlinkpay-embed/
├── index.html      # Main demo page with integration code
├── styles.css      # Styling for popup and button
└── readme.md       # This documentation file
```

## 💻 How to Run

1. **Clone or download** this repository
2. **Open** `index.html` in your web browser
3. **Click** the "Open VLinkPay" button to see the integration in action

No server required - this is a static HTML demo that runs directly in the browser.

## 🔧 Integration Guide

### Basic Setup

1. **Include the CSS and JavaScript** in your HTML:
```html
<link rel="stylesheet" href="styles.css" />
```

2. **Add the button** to trigger VLinkPay:
```html
<button class="vlinkpay-button" onclick="openPopup()">Open VLinkPay</button>
```

3. **Add the popup structure**:
```html
<div class="popup-overlay" id="popup" onclick="closePopupOnOverlay(event)">
  <div class="popup-content">
    <button class="popup-close" onclick="closePopup()">×</button>
    <div class="popup-body">
      <iframe
        src="https://staging-web-app.vlinkpay.com/embed/common?ref=YOUR_REF_ID"
        width="500"
        height="800">
      </iframe>
    </div>
  </div>
</div>
```

### Event Listening

The demo includes event listeners to handle VLinkPay responses:

```javascript
// Listen for sign in events
window.addEventListener('message', (event) => {
  console.log(event.data.type); // signin_error or signin_success
  console.log(event.data.url);  // Redirect URL after successful sign in
});

// Listen for sign up events
window.addEventListener('message', (event) => {
  console.log(event.data.type); // register_error or register_success
});
```

## 🎨 Customization

### Button Styling
Modify the `.vlinkpay-button` class in `styles.css` to match your brand:

```css
.vlinkpay-button {
  padding: 16px 40px;
  font-size: 18px;
  color: #667eea;
  background: #ffffff;
  border: 2px solid #e5e7eb;
  border-radius: 12px;
  /* Add your custom styles here */
}
```

### Popup Appearance
Customize the popup by modifying:
- `.popup-overlay`: Background overlay
- `.popup-content`: Popup container
- `.popup-body`: Iframe container

## 🌐 Configuration

### Environment URLs

- **Staging**: `https://staging-web-app.vlinkpay.com/embed/common?ref=YOUR_REF_ID`
- **Production**: `https://web-app.vlinkpay.com/embed/common?ref=YOUR_REF_ID`

### Parameters

- `ref`: Your unique reference ID provided by VLinkPay

## 📱 Browser Support

- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ✅ Mobile browsers

## 🔒 Security Notes

- The iframe loads VLinkPay's secure payment interface
- All payment processing is handled by VLinkPay's secure servers
- Event messages are used for communication between frames

## 📞 Support

For technical support or questions about VLinkPay integration:

- **Documentation**: Contact VLinkPay support team
- **Issues**: Report issues in this repository
- **Integration Help**: Refer to VLinkPay's official documentation

## 📄 License

This demo is provided as-is for integration testing and reference purposes.

---

**Note**: This is a demo implementation. For production use, ensure you follow VLinkPay's security guidelines and best practices.
