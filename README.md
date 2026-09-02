# OneGas — Frontend Prototype

Multi-provider LPG booking, tracking, and reminder app.
"Get all your gas in one place — track your delivery and never miss a refill."

This is the **frontend only**, built with Flutter, matching the tech stack decided
for the project (Flutter + Firebase, Google Maps for tracking). It runs standalone
with mock/dummy data — no backend setup is required to see every screen.

## How to run

1. Install Flutter: https://flutter.dev/docs/get-started/install
2. Open a terminal in this folder and run:
   ```
   flutter pub get
   flutter run
   ```
3. Pick any connected device or emulator when prompted.

## What's included

All 16 screens from the Day 3 user flow, fully navigable end-to-end:

- Splash → Login (mobile + OTP) → Account Type (Self/Shop)
- Home Dashboard — subsidy quota tracker, government schemes carousel,
  provider list, Book/Emergency CTAs, recent order
- Provider Selection (HP Gas / Bharat Gas / Indane, dummy pricing)
- Cylinder Booking (Self/Other, type, quantity)
- Delivery Slot (normal + Emergency/Priority variant)
- Address (auto-filled from registered number + manual override)
- Review & Payment (UPI / Cash on Delivery)
- Booking Confirmation
- Live Tracking — simulated route animation + transparent status timeline
- OTP Delivery Confirmation + empty-cylinder-pickup notice
- Delivery Rating
- Profile — Self/Shop connections, subsidy tracker, order history, settings
- Notifications (all past alerts)

## Design system

- **Palette**: grounded in a gas flame — blue (`#2F6FED → #17C3E6`) for primary
  actions and trust/tracking moments, orange (`#FF7A30 → #FFB347`) for
  urgency/priority, on a near-black background (`#0B1120`).
- **Type**: Sora for headings, Inter for body (via `google_fonts`).

## What's mocked (by design, per the project's Week 1 plan)

- **Data**: `lib/data/app_data.dart` is an in-memory singleton standing in for
  Firebase. Replace it with real Firebase Auth + Firestore calls when ready.
- **Live tracking**: a `CustomPaint` animation simulates agent movement.
  Swap it for a real `google_maps_flutter` `GoogleMap` widget once you have a
  Maps API key.
- **Multi-provider pricing/availability**: static dummy values — real
  integration would need partnership APIs with HP/Bharat Gas/Indane.
- **OTP**: hardcoded on screen for demo purposes; wire up real SMS OTP via
  Firebase Auth phone sign-in later.

## Next steps (not in this build)

- Firebase project wiring (Auth, Firestore, Cloud Messaging for reminders)
- Google Maps API key + real GoogleMap widget
- Regional language support, chatbot/FAQ assistant (Nice-to-Have features)
