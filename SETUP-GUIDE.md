# katyakohn.com — Setup Guide

## Step 1: Buy the domain (~$9–11/year)

Go to one of these registrars and search for **katyakohn.com**:

- **Cloudflare Registrar** (cheapest long-term, ~$9.15/yr at cost): https://dash.cloudflare.com → Registrar → Register Domain
- **Porkbun** (great value, ~$11/yr, no renewal hikes): https://porkbun.com

Both include **free WHOIS privacy** (hides your personal info from public records).

> Avoid GoDaddy — low first-year prices but expensive renewals.

## Step 2: Set up free hosting on Cloudflare Pages

Cloudflare Pages is free, has unlimited bandwidth, and works perfectly with custom domains.

### Quick deploy (no coding tools needed):

1. Go to https://dash.cloudflare.com and create a free account (or use the one from Step 1)
2. In the dashboard, click **Workers & Pages** → **Create** → **Pages** → **Upload assets**
3. Name your project (e.g., `katyakohn`)
4. **Prepare your files:**
   - Create a folder on your computer called `katyakohn-site`
   - Put the `index.html` file inside it
   - Create a subfolder called `paintings/` inside it
   - Put all your painting image files (.jpg, .png) in the `paintings/` folder
5. Drag and drop the entire `katyakohn-site` folder contents into Cloudflare Pages
6. Click **Deploy site**

Your site will immediately be live at `katyakohn.pages.dev`

### Connect your custom domain:

1. In Cloudflare Pages, go to your project → **Custom domains**
2. Click **Set up a custom domain**
3. Enter `katyakohn.com`
4. If your domain is registered with Cloudflare, DNS is auto-configured
5. If registered elsewhere, Cloudflare will give you DNS records to add at your registrar
6. Also add `www.katyakohn.com` as a custom domain

SSL/HTTPS is automatic and free.

## Step 3: Add your paintings

1. Rename your painting image files clearly, e.g.:
   - `morning-light.jpg`
   - `golden-hour.jpg`
   - `coastal-fog.jpg`

2. Open `index.html` in a text editor (even Notepad works)

3. For each painting, find a placeholder block that looks like this:
   ```html
   <div class="gallery-item" data-category="landscape">
       <div class="placeholder" style="height:320px;background:#7a9e7e;">Your Painting</div>
       <!-- <img src="paintings/painting-01.jpg" alt="Morning Light on the Hills"> -->
       <div class="caption">
           <h3>Morning Light on the Hills</h3>
           <p>Oil on canvas, 2024</p>
       </div>
   </div>
   ```

4. Replace it with your real painting:
   ```html
   <div class="gallery-item" data-category="landscape">
       <img src="paintings/morning-light.jpg" alt="Morning Light on the Hills">
       <div class="caption">
           <h3>Morning Light on the Hills</h3>
           <p>Oil on canvas, 2024</p>
       </div>
   </div>
   ```

   Key changes:
   - Delete the `<div class="placeholder"...` line
   - Uncomment the `<img>` line and update the filename
   - Update the title and medium/year
   - Set `data-category` to: `landscape`, `abstract`, `still-life`, or `portrait`

5. To add more paintings beyond the 12 placeholders, just copy any gallery-item block and paste it before the closing `</div>` of the gallery grid.

6. Update the **About** section with Katya's actual bio.

## Step 4: Redeploy after changes

On Cloudflare Pages: go to your project → **Create new deployment** → upload your updated files.

## File structure

```
katyakohn-site/
├── index.html
└── paintings/
    ├── morning-light.jpg
    ├── golden-hour.jpg
    ├── coastal-fog.jpg
    └── ... (all your painting images)
```

## Total annual cost

| Item | Cost |
|------|------|
| Domain (katyakohn.com) | ~$9–11/year |
| Hosting (Cloudflare Pages) | Free |
| SSL certificate | Free |
| **Total** | **~$9–11/year** |
