# Zorro PRO Cruise - Pre-Order Website

Advanced motorcycle cruise control system pre-order registration website.

## Features

- **Product Information**: Detailed sections explaining Pro Cruise Control, Emergency Braking System (ESS), and Engine Stall Alert
- **Bike Compatibility**: Shows supported models (Triumph Speed 400) and upcoming models (Royal Enfield Himalayan 450, Bajaj NS 400)
- **Pre-Order Form**: Collects user information including name, phone, email, location, and bike details
- **Real-time Counter**: Shows live count of interested users
- **Pricing Section**: Displays early bird pricing for first 20 customers
- **Responsive Design**: Mobile-friendly layout with modern dark theme

## Setup Instructions

### 1. Formspree Setup (Required for Form Submissions)

1. Go to [Formspree.io](https://formspree.io/)
2. Sign up for a free account
3. Create a new form
4. Copy your Form ID (looks like: `https://formspree.io/f/YOUR_FORM_ID`)
5. Replace `YOUR_FORM_ID` in `index.html` line 559 with your actual Form ID

Example:
```html
<form action="https://formspree.io/f/your_actual_form_id" method="POST">
```

### 2. Deploy to GitHub Pages

#### Option A: Using GitHub Web Interface

1. Create a new repository on GitHub
2. Upload the `index.html` file to the repository
3. Go to repository Settings > Pages
4. Under "Source", select `main` branch and save
5. Your site will be live at `https://yourusername.github.io/repository-name`

#### Option B: Using Git Command Line

```bash
# Add files
git add index.html README.md .gitignore

# Commit changes
git commit -m "Initial commit - Zorro PRO Cruise pre-order website"

# Add remote repository (replace with your repository URL)
git remote add origin https://github.com/yourusername/zorro-cruise-website.git

# Push to GitHub
git push -u origin main

# Enable GitHub Pages in repository settings
```

### 3. Custom Domain (Optional)

If you want to use a custom domain:
1. Buy a domain from a registrar (GoDaddy, Namecheap, etc.)
2. Go to your repository Settings > Pages
3. Add your custom domain
4. Update DNS settings as instructed by GitHub

## Features Breakdown

### Form Data Collection
The form collects:
- Full Name
- Phone Number
- Email Address
- Country, State, City
- Bike Brand, Model, Variant (optional)
- Request for different bike models

All submissions are sent to your configured email via Formspree.

### Real-time Counter
Uses CountAPI free service to track interested users. The counter:
- Starts at 0 and increments as users show interest
- Shows live count on page load
- Updates every 30 seconds
- Increments when someone submits the form

### LED Indicator Animations
The website includes animated LED indicators that show:
- Green (Active/Normal)
- Yellow (Standby/Alert)
- Red (Error)
- Off (Inactive)

## Customization

### Change Colors
Edit the Tailwind config in the `<script>` tag at the top of `index.html`:
```javascript
colors: {
    midnight: '#0a0a0a',
    neon: '#22c55e',      // Change this for accent color
    amber: '#f59e0b',
    danger: '#ef4444',
}
```

### Update Pricing
Find the pricing section in the HTML (around line 610) and update the prices:
- Standard price: ₹14,499
- Early bird price: ₹11,499
- Early bird quantity: First 20 customers

### Modify Counter Initial Value
The counter starts at 0 and increments naturally as users show interest. To reset the counter:
- Visit `https://api.countapi.xyz/set/zorro-cruise/interested-count?value=0`

## Support

For issues or questions, contact: zorrotech0@gmail.com

## License

Copyright © 2024 Zorro Tech. All rights reserved.