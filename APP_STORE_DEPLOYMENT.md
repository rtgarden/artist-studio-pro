# Artist Studio Pro - App Store Deployment Guide

This guide walks you through deploying Artist Studio Pro to both the Google Play Store and Apple App Store.

---

## Prerequisites

Before you begin, you'll need:
- A GitHub account (free) - for hosting
- Google Play Developer account ($25 one-time) - for Android
- Apple Developer account ($99/year) - for iOS
- A Mac computer (for iOS builds only)

---

## Part 1: Set Up Free Web Hosting (Required First)

Both app stores require your app to be hosted online. We'll use GitHub Pages (free).

### Step 1: Create a GitHub Repository

1. Go to [github.com](https://github.com) and sign in (or create account)
2. Click the **+** button â†’ **New repository**
3. Name it: `artist-studio-pro`
4. Select **Public**
5. Click **Create repository**

### Step 2: Upload Your Files

1. On your new repository page, click **uploading an existing file**
2. Drag and drop these files from the ArtistStudio_Pro folder:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icons/` folder (with all icon files)
3. Enter commit message: "Initial release"
4. Click **Commit changes**

### Step 3: Enable GitHub Pages

1. Go to your repository **Settings**
2. Click **Pages** in the left sidebar
3. Under "Source", select **main** branch
4. Click **Save**
5. Wait 2-3 minutes, then visit: `https://YOUR-USERNAME.github.io/artist-studio-pro/`

### Step 4: Update manifest.json

Edit `manifest.json` in GitHub to update the URLs:

```json
{
  "start_url": "https://YOUR-USERNAME.github.io/artist-studio-pro/",
  "scope": "https://YOUR-USERNAME.github.io/artist-studio-pro/",
  ...rest stays the same
}
```

**Your app is now live!** Test it on your phone by visiting the URL.

---

## Part 2: Google Play Store Deployment

We'll use PWABuilder (free tool by Microsoft) to create an Android app.

### Step 1: Generate Android Package

1. Go to [pwabuilder.com](https://www.pwabuilder.com)
2. Enter your GitHub Pages URL: `https://YOUR-USERNAME.github.io/artist-studio-pro/`
3. Click **Start**
4. PWABuilder will analyze your app and show a score
5. Click **Package For Stores**
6. Select **Android**
7. Fill in the details:
   - **Package ID**: `com.artiststudiopro.app` (or your own)
   - **App name**: Artist Studio Pro
   - **App version**: 1.0.0
   - **Icon**: Upload the 512x512 icon from your icons folder
8. Click **Generate**
9. Download the ZIP file containing your AAB (Android App Bundle)

### Step 2: Create Google Play Developer Account

1. Go to [play.google.com/console](https://play.google.com/console)
2. Sign in with your Google account
3. Pay the $25 one-time registration fee
4. Complete the account setup (takes 24-48 hours for approval)

### Step 3: Create Your App Listing

1. In Play Console, click **Create app**
2. Fill in:
   - **App name**: Artist Studio Pro
   - **Default language**: English
   - **App or game**: App
   - **Free or paid**: Paid (set your price, e.g., $9.99)
3. Accept the declarations
4. Click **Create app**

### Step 4: Fill Out Store Listing

Navigate through the dashboard and complete:

**Main store listing:**
- Short description (80 chars): "Complete inventory management for visual and theatrical artists"
- Full description (4000 chars max):
```
Artist Studio Pro is the complete inventory management system designed specifically for creative professionals.

PERFECT FOR:
â€¢ Visual artists tracking paintings, sculptures, and mixed media
â€¢ Theatrical professionals managing costumes and props
â€¢ Art collectors cataloging their collections
â€¢ Studio managers organizing supplies and materials

KEY FEATURES:
âœ“ Track 6 types of items: Artworks, Books, Supplies, Costumes, Characters, and Vendors
âœ“ Add photos to every item
âœ“ Cross-reference items (link costumes to characters, artworks to vendors, etc.)
âœ“ Search and filter your entire inventory
âœ“ Works offline - no internet required
âœ“ Your data stays on YOUR device - complete privacy
âœ“ No subscriptions, no recurring fees

ORGANIZE YOUR CREATIVE LIFE:
Whether you're managing a personal art collection, running a theatrical wardrobe department, or keeping track of studio supplies, Artist Studio Pro gives you the tools you need.

PRIVACY FIRST:
All your data is stored locally on your device. We never see your inventory, never upload to the cloud, and never share your information. Your creative work stays yours.

Buy once, use forever. No subscriptions. No ads. No tracking.
```

**Graphics:**
- Screenshots (upload 2-8 screenshots, min 320px, max 3840px)
- Feature graphic (1024 x 500 px)
- App icon (512 x 512 px) - use your icon-512.png

### Step 5: Upload Your App

1. Go to **Production** â†’ **Releases**
2. Click **Create new release**
3. Upload the `.aab` file from PWABuilder
4. Add release notes: "Initial release of Artist Studio Pro"
5. Click **Save** â†’ **Review release** â†’ **Start rollout**

### Step 6: Complete Content Rating

1. Go to **Policy** â†’ **App content**
2. Complete the content rating questionnaire
3. Complete the privacy policy section (create a simple privacy policy)
4. Complete the ads declaration (select "No ads")

### Step 7: Set Pricing

1. Go to **Monetize** â†’ **Pricing**
2. Set your price (e.g., $9.99 USD)
3. Prices will auto-convert to other currencies

### Step 8: Submit for Review

Click **Submit for review**. Google typically reviews apps within 3-7 days.

---

## Part 3: Apple App Store Deployment

This requires a Mac computer and more technical setup.

### Step 1: Set Up Your Mac

1. Install Xcode from the Mac App Store (free, ~12GB)
2. Install Node.js from [nodejs.org](https://nodejs.org)
3. Open Terminal and install Capacitor:
   ```bash
   npm install -g @capacitor/cli
   ```

### Step 2: Create Capacitor Project

1. Create a new folder and open Terminal there:
   ```bash
   mkdir ArtistStudioPro-iOS
   cd ArtistStudioPro-iOS
   npm init -y
   npm install @capacitor/core @capacitor/ios
   npx cap init "Artist Studio Pro" "com.artiststudiopro.app"
   ```

2. Copy[İ\ˆÙXˆš[\Î‚ˆHÜ™X]HHİİØ›Û\‚ˆHÛÜH[™^š[İËšœØX[šY™\İšœÛÛ˜[™XÛÛœËØ[ÈİİËØ‚ŒËˆÛÛ™šYİ\™HØ\XÚ]ÜˆHY]Ø\XÚ]Ü‹˜ÛÛ™šYËšœÛÛ˜‚ˆœÛÛ‚ˆÂˆ˜\Yˆ˜ÛÛK˜\\İİY[Ü›Ë˜\‹ˆ˜\˜[YHˆ\\İİY[È›È‹ˆÙX‘\ˆˆİİÈ‹ˆ˜[™YÙX”[[YHˆ˜[ÙBˆBˆ‚ˆYSÔÈ]›Ü›N‚ˆ˜\ÚˆœØ\Y[ÜÂˆœØ\Ş[˜Âˆ‚ˆÈÈÈİ\ÎˆÜ[ˆ[ˆÛÙB‚˜˜\Ú›œØ\Ü[ˆ[ÜÂ˜‚•\ÈÜ[œÈ[İ\ˆ›Ú™Xİ[ˆÛÙK‚‚ˆÈÈÈİ\ˆÛÛ™šYİ\™H\[ˆÛÙB‚ŒKˆÙ[Xİ[İ\ˆ›Ú™Xİ[ˆHYÚYX˜\‚Œ‹ˆ[™\ˆ
Š”ÚYÛš[™È	ˆØ\Xš[]Y\ÊŠ‚ˆHÙ[Xİ[İ\ˆ\H]™[Ü\ˆX[BˆH]ÛÙHX[˜YÙHÚYÛš[™ÂŒËˆ[™\ˆ
Š‘Ù[™\˜[
Š‚ˆHÙ]™\œÚ[ÛˆKŒŒˆHÙ]Z[ˆBˆY[İ\ˆ\XÛÛœÎ‚ˆHÛÈÈ\ÜÙ]ËØ\ÜÙ]Ø8¡¤ˆ\XÛÛ˜ˆH˜YÈ[İ\ˆXÛÛœÈÈH\›ÜšX]HÛİÂ‚ˆÈÈÈİ\NˆÜ™X]H\H]™[Ü\ˆXØÛİ[‚ŒKˆÛÈÈÙ]™[Ü\‹˜\K˜ÛÛWJÎ‹ËÙ]™[Ü\‹˜\K˜ÛÛJBŒ‹ˆ[œ›Û[ˆH\H]™[Ü\ˆ›ÙÜ˜[H
	NKŞYX\ŠBŒËˆÛÛ\]HH[œ›ÛY[
X^HZÙHMİ\œÊB‚ˆÈÈÈİ\ˆÜ™X]H\[ˆ\İÜ™HÛÛ›™Xİ‚ŒKˆÛÈÈØ\İÜ™XÛÛ›™Xİ˜\K˜ÛÛWJÎ‹ËØ\İÜ™XÛÛ›™Xİ˜\K˜ÛÛJBŒ‹ˆÛXÚÈ
Š“^H\ÊŠˆ8¡¤ˆ
ŠŠÊŠˆ8¡¤ˆ
Š“™]È\
Š‚ŒËˆš[[‚ˆH]›Ü›NˆSÔÂˆH˜[YNˆ\\İİY[È›ÂˆHš[X\H[™İXYÙNˆ[™Û\ÚˆH[™HQˆÙ[Xİ[İ\ˆ\QˆHÒÕNˆ\\İİY[Ü›ÌB‚ˆÈÈÈİ\Îˆš[İ]\[™›Ü›X][Û‚‚ŠŠ\[™›Ü›X][ÛŠŠ‚‹HØ]YÛÜNˆ›ÙXİ]š]HÜˆY™\İ[B‹HÛÛ[šYÚÎˆÙ\È›İÛÛZ[ˆ\™\\HÛÛ[‚ŠŠ”šXÚ[™ÎŠŠ‚‹HšXÙNˆY\ˆ
	ËNJHÜˆY\ˆÈ
	‹NJHÜˆ[İ\ˆÚÚXÙB‚ŠŠ\š]˜XŞNŠŠ‚‹H]HÛÛXİ[ÛˆÙ[Xİ‘]H›İÛÛXİY‚‚ŠŠ”ØÜ™Y[œÚİÎŠŠ‚‹HTÛ™H‹Hˆ
LÍÎ
HH™\]Z\™Y‹HTÛ™HKHˆ
LˆŒŒ
HH™\]Z\™Y‹HTY›ÈL‹Hˆ
ŒÌÌˆ
HHYˆİ\Ü[™ÈTY‚ŠŠ‘\ØÜš\[ÛŠŠ‚•\ÙHHØ[YH\ØÜš\[Ûˆ\ÈÛÛÙÛH^K‚‚ˆÈÈÈİ\ˆZ[[™\ØY‚’[ˆÛÙN‚‚ŒKˆÙ[Xİ
Š[HSÔÈ]šXÙJŠˆ\ÈZ[\™Ù]Œ‹ˆ
Š”›ÙXİ
Šˆ8¡¤ˆ
Š\˜Ú]™JŠ‚ŒËˆÚ[ˆÛÛ\]KÛXÚÈ
Š‘\İšX]H\
Š‚ˆÙ[Xİ
Š\İÜ™HÛÛ›™Xİ
Šˆ8¡¤ˆ
Š•\ØY
Š‚Kˆ›ÛİÈH›Û\Â‚ˆÈÈÈİ\NˆİX›Z]›Üˆ™]šY]Â‚ŒKˆ˜XÚÈ[ˆ\İÜ™HÛÛ›™XİÙ[Xİ[İ\ˆZ[Œ‹ˆš[[ˆ[H™[XZ[š[™È™\]Z\™YšY[ÂŒËˆÛXÚÈ
Š”İX›Z]›Üˆ™]šY]ÊŠ‚‚\H\XØ[H™]šY]ÜÈ\ÈÚ][ˆKMÈ^\Ë‚‚‹KKB‚ˆÈÈš]˜XŞHÛXŞH[\]B‚›İİÜ™\È™\]Z\™HHš]˜XŞHÛXŞKˆÜ™X]HHÚ[\HÙXœYÙHÜˆ\ÙH\È^‚‚˜T•TÕÕQSÈ“È’UPÖHÓPÖB‚“\İ\]YˆÑUWB‚\\İİY[È›È\È\ÚYÛ™YÚ][İ\ˆš]˜XŞH[ˆZ[™‚‚‘UHÓÓPÕSÓ‚•ÙHÈ›İÛÛXİ[H\œÛÛ˜[]Kˆ[[™›Ü›X][Ûˆ[İH[\ˆ[Â\\İİY[È›È\ÈİÜ™YØØ[HÛˆ[İ\ˆ]šXÙH[™\È™]™\‚˜[œÛZ]YÈ\ÈÜˆ[H\™\K‚‚‘UHÕÔQÑN‚–[İ\ˆ[™[ÜH]K[˜ÛY[™È[XYÙ\È[™][H]Z[Ë\ÈİÜ™Yš[ˆ[İ\ˆ]šXÙIÜÈØØ[İÜ˜YÙKˆ\È]H™[XZ[œÈÛˆ[İ\ˆ]šXÙB˜[™\È›İXØÙ\ÜÚX›HÈ\Ë‚‚•T‘TT•HÑT•’PÑTÎ‚\\İİY[È›ÈÙ\È›İ\ÙH[H\™\\H[˜[]XÜË˜Y™\\Ú[™ËÜˆ˜XÚÚ[™ÈÙ\šXÙ\Ë‚‚ÒS‘S‰ÔÈ’UPÖN‚\\İİY[È›ÈÙ\È›İÛ›İÚ[™ÛHÛÛXİ[™›Ü›X][Ûˆœ›ÛB˜Ú[™[ˆ[™\ˆLË‚‚ÒS‘ÑTÎ‚•ÙHX^H\]H\ÈÛXŞHØØØ\Ú[Û˜[Kˆ\]\ÈÚ[™HÜİYÚ][ˆH\‚‚ÓÓ•PÕ‚–Ö[İ\ˆ[XZ[Y™\Ü×B˜‚’Üİ\ÈÛˆ[İ\ˆÚ]XˆYÙ\ÈÚ]H\Èš]˜XŞKš[‚‚‹KKB‚ˆÈÈ[Y[[™Hİ[[X\B‚Ÿİ\[YH™\]Z\™YŸKKKKK_KKKKKKKKKKKKKK_ŸÚ]XˆÙ]\	ˆÜİ[™ÈÌZ[]\ÈŸĞPZ[\ˆ
[™›ÚY
HMHZ[]\ÈŸÛÛÙÛH^HXØÛİ[Mİ\œÈ\›İ˜[Ÿ^HİÜ™H\İ[™ÈKLˆİ\œÈŸ^HİÜ™H™]šY]ÈËMÈ^\ÈŸ
Š[™›ÚYİ[
Šˆ
ŠŸŒHÙYZÊŠˆŸŸ\H]™[Ü\ˆXØÛİ[Mİ\œÈ\›İ˜[ŸÛÙKĞØ\XÚ]ÜˆÙ]\‹LÈİ\œÈŸ\İÜ™HÛÛ›™Xİ\İ[™ÈKLˆİ\œÈŸ\İÜ™H™]šY]ÈKMÈ^\ÈŸ
ŠšSÔÈİ[
Šˆ
ŠŸŒKLˆÙYZÜÊŠˆ‚‹KKB‚ˆÈÈÛÜİİ[[X\B‚Ÿ][HÛÜİŸKKKKK_KKKKK_ŸÚ]XˆYÙ\ÈÜİ[™Èœ™YHŸĞPZ[\ˆœ™YHŸÛÛÙÛH^H]™[Ü\ˆ	H
Û™K][YJHŸ\H]™[Ü\ˆ›ÙÜ˜[H	NKŞYX\ˆŸ
Š•İ[YX\ˆJŠˆ
Š‰L
ŠˆŸ
Š”İXœÙ\]Y[YX\œÊŠˆ
Š‰NKŞYX\ŠŠˆ
\HÛ›JH‚‹KKB‚ˆÈÈ\È›ÜˆİXØÙ\ÜÂ‚ŒKˆ
Š”ØÜ™Y[œÚİÈX]\ŠŠˆHÜ™X]H]˜Xİ]™HØÜ™Y[œÚİÈÚİÚ[™È[İ\ˆ\[ˆ\ÙBŒ‹ˆ
Š’Ù^]ÛÜ™ÊŠˆH[˜ÛYH™[]˜[Ù^]ÛÜ™È[ˆ[İ\ˆ\ØÜš\[Û‚ŒËˆ
Š”™\ÜÛ™È™]šY]ÜÊŠˆH[œİÙ\ˆ\Ù\ˆ]Y\İ[ÛœÈ›Û\Bˆ
Š•\]H™Yİ[\›JŠˆH]™[ˆÛX[\]\ÈÙY\[İ\ˆ\š\ÚX›BKˆ
Š”šXÙH\›ÜšX][JŠˆH	NKIKNHÛÜšÜÈÙ[›Üˆ›ÙXİ]š]H\Â‚‹KKB‚ˆÈÈ™YY[Â‚‹HĞPZ[\ˆØÜÎˆÎ‹ËÙØÜËœØXZ[\‹˜ÛÛB‹HØ\XÚ]ÜˆØÜÎˆÎ‹ËØØ\XÚ]ÜšœË˜ÛÛKÙØÜÂ‹HÛÛÙÛH^HÛÛœÛÛH[ˆÎ‹ËÜİ\Ü™ÛÛÙÛK˜ÛÛKÙÛÛÙÛ\^KØ[™›ÚYY]™[Ü\‚‹H\İÜ™HÛÛ›™Xİ[ˆÎ‹ËÚ[˜\K˜ÛÛKØ\\İÜ™KXÛÛ›™Xİ‚‘ÛÛÙXÚÈÚ][İ\ˆ\][˜ÚH<'æ 