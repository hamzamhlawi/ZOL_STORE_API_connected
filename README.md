# ZOL STORE — API connected starter

This Flutter starter loads products from:
`http://node3.serverix.cloud:3145/api/products`

It submits new orders to:
`POST /api/orders` with `product_code`, `customer_name`, `contact`, `recipient`, and `quantity`.

It then opens WhatsApp with the order summary. A successful API response does NOT mean payment or digital delivery is complete. Your current backend's `/api/orders` endpoint must return a compatible JSON response; the app handles a JSON object with optional `id`.

## Build
1. Extract the ZIP.
2. In the project folder run:
   - `flutter pub get`
   - `flutter run`
3. To build APK: `flutter build apk --release`

## Important
- Current API uses plain HTTP, enabled for this test build only. Configure HTTPS before real customer data/production use, then remove `usesCleartextTraffic=true`.
- Never put Telegram bot tokens, admin keys, or other secrets in the Flutter app.
- API product categories are taken from each product's `category` field. Price uses `price_sdg` first, then `price`.
- Product prices currently returned as null will show “السعر غير محدد” until set in the server database.
- Backend response shape and required fields should be checked against the actual Flask code before production use.
