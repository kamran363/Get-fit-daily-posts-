# Get Fit — Daily Facebook Posts (automatic)

Yeh repo **Get Fit** Facebook page par rozana posts automatic karta hai:
**3 videos, 4 images, 3 text posts** — subah 7 baje se raat 10:45 tak, taqreeban 1.75 ghante ke waqfe se (har qism ke darmiyan 3–4+ ghante ka gap).

Koi approval tap nahi — GitHub Actions schedule par khud post karta hai.

## Setup (sirf ek dafa)

### 1. FB_PAGE_TOKEN secret add karo
1. Is repo me **Settings** → **Secrets and variables** → **Actions** kholo.
2. **New repository secret** dabao.
3. Name: `FB_PAGE_TOKEN`
4. Secret: apna **long-lived Page token** (Graph API Explorer se banaya hua) paste karo → **Add secret**.

> Token kabhi kisi ko mat bhejo — na assistant ko, na chat me. Sirf yahan paste karo.

### 2. Actions on karo
Pehli push ke baad **Actions** tab kholo — agar GitHub enable karne ko kahe to **Enable** dabao.

### 3. Test
**Actions** → **Get Fit daily posts** → **Run workflow** → **Run workflow**. Pehla ready item post ho jayega.

## Content kaise kaam karta hai

- `content/manifest.json` — posts ki queue (tarteeb me). Har item: `type` (text/image/video), `caption`, `file`, aur `ready`.
- `content/state.json` — queue me abhi kahan hain (har post ke baad khud update hota hai).
- `content/images/` aur `content/videos/` — media files.

Jab tak item `"ready": false` hai, us slot me kuch post nahi hoga. Muse rozana naya content (captions, images, videos) bana kar queue bharta rahega.
