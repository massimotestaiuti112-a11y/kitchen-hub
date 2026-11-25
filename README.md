# Kitchen Hub: setup (about 10 minutes, done once)

A single-page hub for your Meta Portal with a clock, the weather and a 5-day forecast, a kitchen timer, a family to-do board and Spotify controls. There's no server and no account apart from Spotify.

## Why it needs a free HTTPS address
Since November 2025, Spotify only lets you sign in from an **https://** address. The one exception is `127.0.0.1`, and that only works on the same computer the page runs on. The Portal is a separate device, so put the page on free static hosting:

**Easiest: Netlify Drop**
1. On a computer, go to https://app.netlify.com/drop (free account).
2. Drag the `kitchen-hub` folder onto the page.
3. You'll get an address like `https://cozy-kitchen-123.netlify.app`. You can rename it under Site settings.

(GitHub Pages or Cloudflare Pages work too. Any https static host is fine.)

## Create your Spotify app
1. Go to https://developer.spotify.com/dashboard and sign in with your **Spotify Premium** account. Spotify requires Premium for personal developer apps.
2. Click **Create app**.
   - Name: Kitchen Hub (any name works)
   - Redirect URI: your hub address **with the trailing slash**, e.g. `https://cozy-kitchen-123.netlify.app/`
   - Under APIs used, tick **Web API** and **Web Playback SDK**
3. Save, then copy the **Client ID**.
4. Optional: under **User Management**, add the email addresses of up to 5 family Spotify accounts that might sign in.

## On the Portal
1. Open the Portal's web browser and go to your hub address.
2. Tap ⚙ (top right). Paste the Client ID, set your city and your household name, then tap Save.
   - The settings screen also shows the exact Redirect URI to use. If sign-in fails with "invalid redirect URI", make your Spotify app's URI match it exactly.
3. Tap **Connect Spotify** and sign in.
4. Bookmark the page or add it to the home screen.

## Where the music plays
- **On the Portal itself:** if the Portal's browser supports Spotify's web player, a device called "<Household> Hub" appears and playlists play right there.
- **On any other speaker:** tap the speaker icon on the Now Playing card to choose an Echo, Sonos, TV, phone or computer. A speaker only shows up after Spotify has been opened on it recently.

## Good to know
- The timer, the board and your settings are saved on the device.
- After 5 minutes without a touch, the hub dims to a large clock with the current song. You can change this in settings.
- Weather comes from Open-Meteo, which doesn't need a key.
- To update the hub later, drag the folder onto Netlify again. Your settings stay on the Portal.
