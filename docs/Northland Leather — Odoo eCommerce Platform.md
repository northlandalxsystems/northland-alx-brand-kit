Northland Leather — Odoo eCommerce Platform

Northland Leather is a luxury eCommerce platform for handcrafted leather goods made in Ghana, targeting local and international customers. Built on Odoo, the system is designed to handle high-quality branding, seamless payments, real-time shipping, and role-based inventory management.

 📌 Key Features

* Fully responsive eCommerce frontend
* Integrated with Paystack for payment processing
* DHL and GhanaPost shipping API integrations
* Role-based product, inventory, and order management
* Elegant, African-influenced branding and UI
* Modular packaging flow for bespoke customer experience

🧱 Technologies Used

| Layer      | Tech                              |
| _--_--_--_-| _--_--_--_--_--_--_--_--_--_-     |
| Frontend   | Odoo Website Builder (customized) |
| Backend    | Odoo (Python, PostgreSQL)         |
| Payments   | Paystack API                      |
| Shipping   | DHL API, GhanaPost API            |
| Deployment | Azure (Ubuntu VM)                 |
| Versioning | Git / GitHub                      |

📦 Product Types

* Men's Bags (Briefcases, Backpacks)
* Women's Bags (Handbags, Clutches)
* Wallets (Unisex)
* Belts
* Custom Leather Gifts

📋 SKU Naming Convention

[ProductCategory]-[MaterialCode]-[ColorCode]-[SizeCode]-[BatchYear]
Example: MBG-FL-BLK-MD-25  ➔ Men's Bag, Full Leather, Black, Medium, 2025 batch

🔐 Roles & Permissions

| Role      | Permissions               |
| _--_-- -- | _--_--_--_--_--_--_--_--_ |
| Director  | Full system access        |
| Manager   | Product, Order, Inventory |
| Designer  | Upload product media      |
| Sales Rep | View & manage orders      |
| Customer  | Browse, purchase, review  |

_---
 💳 Paystack Integration

* Endpoint: `https://api.paystack.co/transaction/initialize`
* Auth: Bearer Token (Secure via `.env`)
* Webhook handler for success/failure callbacks
* Reference → Order link enabled

_---
 🚚 Shipping Integration

* DHL API: International rates + tracking
* GhanaPost API: Local delivery + address verification
* Shipping selection shown at checkout with live pricing

🔧 Deployment
Hosting:

* **Platform:** Azure Ubuntu 22.04 VM
* **Odoo:** Community Edition 17
* **Domain:** `northlandleather.com`
# Setup:

```bash
sudo apt update && sudo apt upgrade
# Install PostgreSQL
sudo apt install postgresql -y
# Install Python and dependencies
sudo apt install python3-pip build-essential wget -y
pip3 install wheel werkzeug odoo
# Pull project from GitHub
git clone https://github.com/Northland-Analytics/northland-leather.git
cd northland-leather
# Run Odoo
./odoo-bin -c odoo.conf
```

Use **PM2 or Supervisor** for process management, **Nginx** as reverse proxy, and **Certbot** for SSL.

🔪 Testing & QA

* ✅ Product page loading time
* ✅ Payment gateway response time (<3s)
* ✅ Inventory update after purchase
* ✅ Shipping label generation
* ✅ Mobile responsive layouts

📞 Contact

**Northland Analytics**
📧 [northlandanalytics@protonmail.com](mailto:northlandanalytics@protonmail.com)
🌍 Accra, Ghana

🎨 UI/UX & Branding Kit (Figma)
# Brand Colors

| Name           | Hex       |
| _--_--_--_--_--_--_-- | _--_--_--_--- |
| Deep Orange    | `#D35400` |
| Charcoal Black | `#1C1C1C` |
| Warm Cream     | `#F8F1E7` |
| Accent Gold    | `#E1C699` |
# Font Pairing

* **Headings**: Playfair Display
* **Body**: Inter or Source Sans Pro
# Screens to Design

* Landing Page
* Product Detail Page
* Checkout Flow
* Admin Dashboard
* Customer Order Tracker
* Auth Pages

> Figma files will include exportable components, brand icons, and responsive layouts.

🧱 Inventory Structure & SKU Logic
# DB Tables

| Table       | Key Columns                                               |
| _--_--_--_--| _--_--_--_--_--_--_--_--_--_--_--_--_--_--_--_--_--_--_--_|
| `products`  | id, name, sku, category\_id, material, color, size, price |
| `inventory` | product\_id, quantity\_available, reorder\_threshold      |
| `orders`    | order\_id, customer\_id, status, total\_price             |
| `media`     | product\_id, image\_url, alt\_text                        |
# Categories (JSON Sample)

```json
{
  "men_bags": ["Briefcase", "Messenger", "Backpack"],
  "women_bags": ["Tote", "Shoulder", "Clutch"],
  "wallets": ["Slim", "Fold", "Zip"],
  "belts": ["Classic", "Braided"],
  "custom": ["Gift Box", "Engraved Set"]
}
```

📦 Packaging Design Concepts

1. **Rigid Kraft Boxes** with embossed Northland logo
2. **Branded Dust Bags** (suede-textured cotton)
3. **QR Code Care Cards** (maintenance instructions + story)
4. **Tamper-proof Shipping Sleeves** (DHL-compliant)
# Local vs. International

| Type            | Contents                            |
| _--_--_--_--_--_| _--_--_--_--_--_--_--_--_--_--_--_--|
| GhanaPost Local | Branded paper bag + rigid box       |
| DHL Intl.       | Hard box + protective wrap + labels |

> Mockups for packaging are in progress. Will provide PNG/SVG/Figma export options.

