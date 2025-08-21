
### Parameters

| Parameter | Type | Required | Description | Example |
|-----------|------|----------|-------------|---------|
| `phone` | string | ✅ Yes | Phone number with country code (7-15 digits) | `60123456789` |
| `message` | string | ❌ No | Pre-filled message for WhatsApp | `Hello%20World` |

### Country Code Examples

| Country | Code | Example Phone | Full Parameter |
|---------|------|---------------|----------------|
| Malaysia | +60 | 123456789 | `phone=60123456789` |
| Singapore | +65 | 87654321 | `phone=6587654321` |
| United States | +1 | 5551234567 | `phone=15551234567` |
| United Kingdom | +44 | 7911123456 | `phone=447911123456` |
| India | +91 | 9876543210 | `phone=919876543210` |

## 📱 Integration Examples

### HTML Link
```html
<a href="https://zack-airruder.github.io/whatsapp-qr/qrapi.html?phone=60123456789&message=Hi%20there!" target="_blank">
    Generate WhatsApp QR Code
</a>
```

### JavaScript
```javascript
function generateWhatsAppQR(phone, message) {
    const baseUrl = 'https://zack-airruder.github.io/whatsapp-qr/qrapi.html';
    const params = new URLSearchParams({
        phone: phone,
        message: message || ''
    });
    
    window.open(`${baseUrl}?${params.toString()}`, '_blank');
}

// Usage
generateWhatsAppQR('60123456789', 'Hello from our website!');
```

### React Component
```jsx
import React from 'react';

const WhatsAppQRGenerator = ({ phone, message, children }) => {
    const generateQR = () => {
        const baseUrl = 'https://zack-airruder.github.io/whatsapp-qr/qrapi.html';
        const params = new URLSearchParams({
            phone,
            ...(message && { message })
        });
        
        window.open(`${baseUrl}?${params.toString()}`, '_blank');
    };
    
    return (
        <button onClick={generateQR} className="whatsapp-qr-btn">
            {children || 'Generate QR Code'}
        </button>
    );
};

// Usage
<WhatsAppQRGenerator 
    phone="60123456789" 
    message="Hello from React!"
>
    Create WhatsApp QR
</WhatsAppQRGenerator>
```

### PHP Integration
```php
<?php
function generateWhatsAppQRUrl($phone, $message = '') {
    $baseUrl = 'https://zack-airruder.github.io/whatsapp-qr/qrapi.html';
    $params = http_build_query([
        'phone' => $phone,
        'message' => $message
    ]);
    
    return $baseUrl . '?' . $params;
}

// Usage
$qrUrl = generateWhatsAppQRUrl('60123456789', 'Hello from PHP!');
echo "<a href='$qrUrl' target='_blank'>Generate QR Code</a>";
?>
```

## 🎯 Use Cases

- **Business Cards**: Add QR codes to business cards for instant WhatsApp contact
- **Marketing Materials**: Include in flyers, posters, and advertisements
- **Customer Support**: Quick access to support chat
- **Event Registration**: Easy contact for event organizers
- **E-commerce**: Direct customer communication channel
- **Restaurant Menus**: Quick ordering or reservation system
- **Real Estate**: Instant contact for property inquiries

## 🔧 Advanced Usage

### URL Encoding
For messages with special characters, ensure proper URL encoding:

```javascript
const message = "Hello! How are you? 😊";
const encodedMessage = encodeURIComponent(message);
const url = `https://zack-airruder.github.io/whatsapp-qr/qrapi.html?phone=60123456789&message=${encodedMessage}`;
```

### Batch Generation
```javascript
const contacts = [
    { phone: '60123456789', message: 'Hello John!' },
    { phone: '60987654321', message: 'Hello Jane!' },
    { phone: '60555666777', message: 'Hello Bob!' }
];

contacts.forEach((contact, index) => {
    setTimeout(() => {
        const url = `https://zack-airruder.github.io/whatsapp-qr/qrapi.html?phone=${contact.phone}&message=${encodeURIComponent(contact.message)}`;
        window.open(url, '_blank');
    }, index * 1000); // 1 second delay between each
});
```

## 🚀 Self-Hosting

### GitHub Pages Setup

1. **Fork or Download**: Get the `qrapi.html` file
2. **Create Repository**: Create a new GitHub repository
3. **Upload File**: Add `qrapi.html` and `logo.png` to your repository
4. **Enable Pages**: Go to Settings → Pages → Source: Deploy from branch → main
5. **Access**: Your API will be available at `https://username.github.io/repository-name/qrapi.html`

### Custom Domain

1. **Upload Files**: Place `qrapi.html` and `logo.png` on your web server
2. **Configure Domain**: Point your domain to the hosting location
3. **SSL Certificate**: Ensure HTTPS is enabled for security
4. **Test**: Verify the API works with your domain

### Local Development

```bash
# Using Python
python -m http.server 8080

# Using Node.js
npx http-server -p 8080

# Using PHP
php -S localhost:8080
```

Then access: `http://localhost:8080/qrapi.html?phone=60123456789&message=Test`

## Mobile Optimization

- **Responsive Design**: Automatically adapts to mobile screens
- **Touch-Friendly**: Large buttons and touch targets
- **Fast Loading**: Optimized for mobile networks
- **Auto-Download**: QR codes download automatically on mobile devices

## Privacy & Security

- **No Data Storage**: No phone numbers or messages are stored
- **Client-Side Processing**: All processing happens in the browser
- **HTTPS Ready**: Secure transmission when hosted with SSL
- **No Tracking**: No analytics or tracking scripts included

## Error Handling

The API handles various error scenarios:

- **Missing Phone**: "Phone number is required"
- **Invalid Length**: "Phone number must be at least 7 digits"
- **Too Long**: "Phone number cannot exceed 15 digits"
- **QR Generation Failed**: Automatic fallback to basic QR pattern
- **Logo Load Failed**: Fallback to emoji icon

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Support

- **Issues**: Report bugs or request features via GitHub Issues
- **Documentation**: Check this README for comprehensive usage guide
- **Community**: Join discussions in GitHub Discussions

## Changelog

### v1.0.0
- Initial release
- Basic QR code generation
- Auto-download functionality
- Phone number validation
- WhatsApp logo overlay
- Responsive design
- Error handling

---

**Made by Zack Loo **

*Generate WhatsApp QR codes instantly with zero configuration!*
