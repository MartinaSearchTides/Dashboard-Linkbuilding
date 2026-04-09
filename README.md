# SearchTides LV Dashboard

Real-time LV dashboard pulling data from three SeaTable bases.

## Setup

### 1. GitHub
Push this folder to a new GitHub repository (can be private).

### 2. Vercel
1. Go to [vercel.com](https://vercel.com) → New Project → Import from GitHub
2. Select this repository
3. Click **Deploy** (default settings are fine)

### 3. Environment Variables
In Vercel → Project Settings → Environment Variables, add:

| Name | Value |
|------|-------|
| `OM_API_TOKEN`  | `e04c9404877a98d87b5b7530667d7449828eab2d` |
| `LBT_API_TOKEN` | `ec482699cb614535b22e3df5acfdcb372b82f632` |
| `CMS_API_TOKEN` | `7450049f789260e64a393ad91bbb33184be0d37e` |

After adding variables, click **Redeploy**.

### 4. Done
Your dashboard is live at `your-project.vercel.app`

## Data sources
- **HSS base** — internal OM data + QUOTAS (internal quotas per client)
- **LBT base** — external linkbuilders (FanDuel, FanDuel Casino, FanDuel Racing, CreditNinja)
- **CMS Master** — journalists/press links for FanDuel only (filtered by Live Link Date current month)

## Notes
- Company quotas and AS fee per LV are stored in browser localStorage — set them once per month via the "edit" button
- Data refreshes automatically on page load, or manually via the Refresh button
- Vercel caches API responses for 5 minutes to avoid hitting SeaTable rate limits
