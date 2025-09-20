# TuckshopKonnect Student Wallet

A modern, secure digital wallet interface for students to manage their tuckshop payments and transactions within educational institutions.

## Features

### Core Functionality
- **Digital Wallet Management**: Students can view their current balance and transaction history
- **Secure Payment Integration**: Paystack integration for safe online payments
- **Parent Dashboard**: Parents can fund their ward's wallet and monitor spending
- **Real-time Balance Updates**: Instant balance updates after successful transactions
- **Transaction History**: Comprehensive transaction logging with export functionality

### User Experience
- **Modern UI/UX**: Contemporary design with glassmorphism effects and smooth animations
- **Mobile Responsive**: Optimized for both desktop and mobile devices
- **Dark Theme**: Eye-friendly gradient background with high contrast elements
- **Interactive Elements**: Hover effects, smooth transitions, and micro-animations

### Security Features
- **SSL Encryption**: All transactions are secured with SSL encryption
- **Paystack Integration**: Industry-standard payment processing
- **Transaction Validation**: Server-side payment verification
- **Secure References**: Unique transaction references for tracking

## Technology Stack

### Frontend
- **HTML5**: Semantic markup structure
- **CSS3**: Advanced styling with modern features
  - CSS Grid and Flexbox
  - Backdrop filters and glassmorphism
  - CSS animations and transitions
- **JavaScript (ES6+)**: Interactive functionality
- **Bootstrap 5.3**: Responsive framework
- **Font Awesome 6**: Icon library
- **Google Fonts (Inter)**: Typography

### Payment Processing
- **Paystack**: Nigerian payment gateway integration
- **Paystack Inline JS**: Client-side payment processing

### External Dependencies
- Bootstrap CSS & JS
- Font Awesome icons
- Google Fonts
- Paystack JavaScript SDK

## Installation

1. **Clone/Download the HTML file**
   ```bash
   # Save the HTML file to your web server directory
   ```

2. **Configure Paystack**
   ```javascript
   // Replace with your actual Paystack public key
   const PAYSTACK_PUBLIC_KEY = 'pk_test_your_actual_key_here';
   ```

3. **Set up a web server**
   - Use any web server (Apache, Nginx, or simple Python/Node.js server)
   - Ensure HTTPS for production (required by Paystack)

4. **Backend Integration** (Required for production)
   - Implement payment verification endpoint
   - Set up database for transaction storage
   - Create user authentication system
   - Add API endpoints for wallet operations

## Configuration

### Payment Settings
```javascript
const PAYSTACK_PUBLIC_KEY = 'your_paystack_public_key';
const MINIMUM_AMOUNT = 100; // Minimum funding amount in Naira
```

### Mock Data Structure
The current implementation uses mock data that should be replaced with actual API calls:

```javascript
let parentInfo = {
    name: 'Parent Name',
    email: 'parent@email.com',
    phone: '08123456789',
    id: 'PAR001'
};

let studentInfo = {
    name: 'Student Name',
    id: 'STU001',
    class: 'JSS 2A',
    parentId: 'PAR001'
};
```

## Usage

### For Parents
1. **View Student Balance**: Current wallet balance is displayed prominently
2. **Add Funds**: Click "Add Funds" to top up the student's wallet
3. **Select Amount**: Choose from preset amounts or enter a custom amount
4. **Make Payment**: Complete payment through Paystack
5. **View Transactions**: Monitor all funding and spending activities

### For Students
1. **Check Balance**: View available funds for tuckshop purchases
2. **Transaction History**: Review past purchases and top-ups
3. **Profile Management**: Access student information and settings

## API Integration (Required for Production)

### Endpoints Needed
```
GET /api/student/{id}/wallet - Get wallet balance and info
GET /api/student/{id}/transactions - Get transaction history
POST /api/wallet/fund - Initialize payment
POST /api/webhook/paystack - Handle payment callbacks
GET /api/student/{id}/profile - Get student details
```

### Payment Flow
1. Frontend initiates payment with Paystack
2. Paystack processes payment
3. Webhook receives payment confirmation
4. Backend verifies payment with Paystack API
5. Database updated with new transaction
6. Frontend receives confirmation and updates UI

## Security Considerations

### Production Requirements
- **HTTPS Only**: Required for Paystack integration
- **Payment Verification**: Always verify payments server-side
- **Input Validation**: Validate all user inputs
- **Authentication**: Implement proper user authentication
- **Rate Limiting**: Prevent abuse of payment endpoints
- **Logging**: Log all transactions for audit trails

### Data Protection
- Never store payment card details
- Use secure session management
- Implement proper error handling
- Sanitize all user inputs

## Customization

### Styling
- Modify CSS variables for color scheme changes
- Adjust gradient backgrounds in the `body` selector
- Update card styling in `.wallet-card` and `.transaction-card`
- Customize animations in the `@keyframes` sections

### Functionality
- Add new payment amounts in the `amount-grid`
- Modify minimum payment amount in `MINIMUM_AMOUNT`
- Customize transaction categories
- Add export formats (PDF, Excel)

## Browser Support

- **Chrome**: 90+
- **Firefox**: 88+
- **Safari**: 14+
- **Edge**: 90+
- **Mobile**: iOS Safari 14+, Chrome Mobile 90+

## Performance Optimization

- CSS and JavaScript are minified in production
- Images are optimized and compressed
- Font loading is optimized with `display=swap`
- Lazy loading implemented for transaction lists

## Troubleshooting

### Common Issues
1. **Payment Not Processing**
   - Check Paystack public key
   - Ensure HTTPS connection
   - Verify parent email format

2. **UI Not Displaying Correctly**
   - Check browser compatibility
   - Ensure all CSS/JS files are loaded
   - Clear browser cache

3. **Mobile Responsiveness**
   - Test on actual devices
   - Check viewport meta tag
   - Verify Bootstrap grid implementation

## Future Enhancements

### Planned Features
- **QR Code Payments**: Quick payments via QR scanning
- **Spending Limits**: Parental controls for daily/weekly limits
- **Multi-language Support**: Support for local languages
- **Offline Mode**: Basic functionality when offline
- **Push Notifications**: Payment confirmations and low balance alerts
- **Biometric Authentication**: Fingerprint/Face ID login
- **Meal Planning**: Integration with cafeteria menu system

### Technical Improvements
- **PWA Support**: Progressive Web App capabilities
- **Real-time Updates**: WebSocket integration for live balance updates
- **Advanced Analytics**: Spending pattern analysis
- **Bulk Payments**: Fund multiple children's accounts
- **CSV Import**: Bulk transaction imports for schools

## Support

### Contact Information
- **WhatsApp Support**: +234 815 139 8031
- **Technical Issues**: Report via GitHub issues
- **Feature Requests**: Submit enhancement requests

### Documentation
- Paystack API Documentation: https://paystack.com/docs
- Bootstrap Documentation: https://getbootstrap.com/docs/
- Font Awesome Icons: https://fontawesome.com/icons

## License

This project is proprietary software developed for TuckshopKonnect. All rights reserved.

## Contributing

This is a proprietary project. External contributions are not currently accepted.

---

**Note**: This is a frontend demonstration. Production deployment requires backend API development, database setup, and proper security implementation.
