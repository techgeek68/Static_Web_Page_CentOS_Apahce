# Fun Static Website Project

![Website Preview](https://via.placeholder.com/800x400?text=Fun+Static+Website+Preview)

A colorful, interactive static website featuring animated backgrounds, a joke generator, and party mode – deployed on CentOS Stream 10 with Apache.

---

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation & Deployment](#installation--deployment)
- [Usage](#usage)
- [Customization](#customization)
- [Troubleshooting](#troubleshooting)
- [Best Practices](#best-practices)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- **Animated Gradient Background:** Smooth color transitions using CSS animations
- **Random Joke Generator:** Click a button to get tech-themed humor
- **Party Mode:** Toggle falling emoji confetti for celebrations
- **Responsive Design:** Adapts to desktop, tablet, and mobile screens
- **Lightweight Implementation:** Pure HTML/CSS/JavaScript with no dependencies

---

## Technologies Used

- **Frontend:** HTML5, CSS3 (Animations, Gradients), JavaScript (DOM Manipulation)
- **Web Server:** Apache HTTP Server
- **Operating System:** CentOS Stream 10
- **Virtualization:** UTM (for macOS users)
- **Version Control:** Git

---

## Installation & Deployment

### Prerequisites

- CentOS Stream 10 server (can run in UTM on macOS)
- Terminal access (SSH)
- Basic command-line knowledge

### Step 1: Install Apache

```bash
sudo dnf install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```

### Step 2: Deploy Website

```bash
# Clone repository
git clone https://github.com/techgeek68/Static_Web_Page_CentOS_Apahce.git

# Copy to web directory
sudo cp -r Static_Web_Page_CentOS_Apahce /var/www/html/myfunwebsite

# Set permissions
sudo chown -R apache:apache /var/www/html/myfunwebsite
sudo chmod -R 755 /var/www/html/myfunwebsite

# Restart Apache
sudo systemctl restart httpd
```

### Step 3: Access Website

- **Local:** [http://localhost/myfunwebsite/](http://localhost/myfunwebsite/)
- **Remote:** `http://<your-server-ip>/myfunwebsite/`

---

## Usage

- **Animated Background:** Colors transition automatically.
- **Joke Generator:** Click "Tell Me a Joke" for random tech humor.
- **Party Mode:** Toggle switch to activate falling emoji confetti.
- **Responsive Design:** Resize browser to see layout adapt.

---

## Customization

Personalize your website by modifying:

### Jokes

Edit the `jokes` array in JavaScript:

```javascript
const jokes = [
  "Why do programmers prefer dark mode? Because light attracts bugs!",
  "New joke here",
  "Another funny tech joke"
];
```

### Gradient Colors

Adjust in CSS `@keyframes gradientBG`:

```css
@keyframes gradientBG {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}
```

### Confetti Emojis

Update the `emojis` array:

```javascript
const emojis = ['🎉', '✨', '🥳', '🎊', '💻'];
```

### Color Scheme

Modify CSS variables in `:root`:

```css
:root {
  --primary-color: #ff6b6b;
  --secondary-color: #4ecdc4;
}
```

---

## Troubleshooting

| Issue                 | Solution                                              |
|-----------------------|------------------------------------------------------|
| 403 Forbidden         | `sudo chmod -R 755 /var/www/html/myfunwebsite`       |
| Apache not starting   | Check logs: `sudo journalctl -u httpd`               |
| Website not loading   | Verify firewall: `sudo firewall-cmd --list-all`      |
| JavaScript errors     | Check browser console for debugging                  |
| Permission issues     | `sudo chown -R apache:apache /var/www/html/myfunwebsite` |

---

## Best Practices

**Enable HTTPS:**

```bash
sudo dnf install certbot python3-certbot-apache
sudo certbot --apache -d yourdomain.com
```

**Regular Backups:**

```bash
tar -czvf website-backup-$(date +%F).tar.gz /var/www/html/myfunwebsite
```

**Monitor Logs:**

```bash
tail -f /var/log/httpd/access_log
tail -f /var/log/httpd/error_log
```

**System Updates:**

```bash
sudo dnf update -y && sudo dnf upgrade -y
```

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch:  
   `git checkout -b feature/new-feature`
3. Commit your changes:  
   `git commit -m 'Add new feature'`
4. Push to branch:  
   `git push origin feature/new-feature`
5. Open a pull request

For major changes, please [open an issue](../../issues) first to discuss.

---

## License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

**Project Maintainer:** [techgeek68](https://github.com/techgeek68)  
**Repository:** [Static_Web_Page_CentOS_Apahce](https://github.com/techgeek68/Static_Web_Page_CentOS_Apahce)
