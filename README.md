# shelfLife 📚

Your personal book companion — track your TBR, prep for bookstore trips, and never buy a duplicate again.

## Features
- 📊 **Dashboard** with customizable widgets (library stats, mood search, season search, random pick, want-to-buy list)
- 📖 **TBR browser** with mood, ownership, and search filters + 3 view modes
- ✈️ **Trip prep** — tag books by author origin & setting, search by destination
- 🔍 **Bookstore mode** — search Google Books, cross-reference your library
- 📷 **Barcode scanner** — scan ISBNs with your phone camera
- 📈 **Stats** — reading trends, genre breakdown, mood distribution
- 🎨 **6 themes** (Bold, Dark Academia, Cottagecore, Midnight, Matcha, Sunset)
- 📱 **PWA** — install on your phone's home screen

## Setup (10 minutes)

### 1. Supabase
1. Go to [supabase.com](https://supabase.com) and open your project
2. Go to **SQL Editor** (left sidebar)
3. Paste the contents of `supabase/schema.sql` and click **Run**
4. Go to **Settings → API** and copy:
   - **Project URL** (looks like `https://abc123.supabase.co`)
   - **anon public** key (long string starting with `eyJ...`)

### 2. Environment Variables
1. Copy `.env.local.example` to `.env.local`
2. Fill in your Supabase URL and anon key:
   ```
   NEXT_PUBLIC_SUPABASE_URL=https://your-project.supabase.co
   NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJ...your-key
   ```

### 3. Deploy to Vercel
1. Push this repo to GitHub
2. Go to [vercel.com](https://vercel.com) → **Add New Project**
3. Import your GitHub repo
4. Add the two environment variables:
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
5. Click **Deploy**

Your app will be live at `your-project.vercel.app`!

### 4. Import Your Data
1. Open the app on your phone
2. Tap the import icon (top right)
3. Upload your Goodreads CSV first, then StoryGraph CSV
4. Run the Google Books enrichment to fetch covers and genres

### 5. Install as App (Optional)
On your phone, open the Vercel URL in Safari/Chrome and:
- **iOS**: Tap Share → Add to Home Screen
- **Android**: Tap the three dots → Add to Home Screen

## Development
```bash
npm install
npm run dev
```
Open [http://localhost:3000](http://localhost:3000)

## Tech Stack
- **Next.js 14** — React framework
- **Supabase** — PostgreSQL database (free tier)
- **Vercel** — Hosting (free tier)
- **Google Books API** — Book search & metadata
- **html5-qrcode** — Barcode scanning via camera
