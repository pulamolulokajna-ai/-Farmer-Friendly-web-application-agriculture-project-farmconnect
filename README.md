# FarmConnect React

A Vite + React conversion of the FarmConnect agriculture marketplace. The original source ZIP is unchanged; this is a separate clean project with one `src` directory.

## Run on Windows, macOS, or Linux

1. Install Node.js (LTS).
2. Open a terminal in this folder.
3. Run `npm install`.
4. Run `npm run dev` and open the local address printed by Vite.

To create a production build, run `npm run build`.

## Screens and workflows

- Public landing page and buyer account sign-in/registration
- Farmer registration/login, dashboard, products, add/edit/delete, orders, sales trends, and profile
- Buyer dashboard, product search/category filters, favorites, cart quantity controls, checkout, orders, and profile
- Data saved in browser localStorage using the source app's compatible keys where possible: `farmProducts`, `farmOrders`, `farmerProfile`, `farmConnectFarmerAccount`, `farmConnectFarmerLoggedIn`, `buyerAccounts`, `currentBuyer`, `buyerCart`, and `buyerFavorites`

The app seeds a starter product catalog when `farmProducts` has not been set yet. To clear local app data, clear this site's localStorage in your browser developer tools.

## Replication notes

The original project is a frontend-only prototype and contains no server, payment gateway, shipping service, or real authentication provider. This conversion keeps sign-in and data local to the browser, and checkout creates a pending order with cash on delivery as the visible option. Accounts and credentials are not secure server-side authentication. Original payment processing, live inventory synchronization, remote image uploads, and cross-device syncing cannot be replicated without backend services. Sales charts use locally recorded orders; the monthly chart is illustrative because the source does not store a robust month-by-month sales dataset.

The original source contained separate but overlapping farmer and buyer pages and inconsistent per-buyer storage behavior. The conversion keeps the shared data structures recognizable and scopes new buyer carts/favorites by account after sign-in; older unscoped data is preserved.

## Build verification

The production build was verified with the command npm run build.
pm run build.

Buyer sign-in normalizes email addresses and trims passwords to match the original app's behavior. On the first sign-in, entering a valid email and any password creates a local demo buyer account and opens the buyer dashboard. Later sign-ins require the same password. This is demo-only browser storage, not secure authentication.




