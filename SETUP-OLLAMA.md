# Connect EtelAI → Your PC's Ollama (Free)

## STEP 1 — Install Ollama on your PC
Download from: https://ollama.com/download/windows
(free, installs in 1 minute)

## STEP 2 — Download TinyLlama (and other free models)
Open PowerShell and run:

```powershell
ollama pull tinyllama      # 638 MB — ultra fast
ollama pull phi3           # 2.3 GB — smarter
ollama pull codellama      # 3.8 GB — code expert
ollama pull mistral        # 4.1 GB — best balance
ollama pull llama3         # 4.7 GB — most powerful
```

Test it works:
```powershell
ollama run tinyllama "Hello, are you working?"
```

## STEP 3 — Run EtelAI locally (simplest method)

Open PowerShell in your project folder and run:
```powershell
cd "C:\Users\dagianan\Downloads\etel-os\etel-os"
python -m http.server 8080
```
Then open: http://localhost:8080 in your browser.
EtelAI will talk to Ollama automatically — 100% free, no internet needed.

---

## STEP 4 — Connect your ethelmarket.com website to your PC Ollama (free tunnel)

Your website (ethelmarket.com) can't reach localhost directly.
Use a FREE Cloudflare Tunnel:

### One-time setup:
1. Download cloudflared: https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/
2. Run in PowerShell:
```powershell
cloudflared tunnel --url http://localhost:11434
```
3. You'll see a URL like: https://abc123.trycloudflare.com
4. Open config.js and replace:
```js
ollamaUrl: 'https://abc123.trycloudflare.com',
```
5. Upload config.js to your server. Done!

NOTE: The tunnel URL changes each time you restart cloudflared.
For a fixed URL, create a free Cloudflare account and use named tunnels.

---

## STEP 5 — Use the Agents from your Agents/ folder

Extract these zips into the Agents/ folder:
- Agents/OpenJarvis-main.zip → Agents/OpenJarvis-main/
- Agents/graphify-8.zip → Agents/graphify-8/

The config.js already registers them as skill sources.

## STEP 6 — Download more free skills from GitHub

Good free AI agent repos to add:
- https://github.com/BuilderIO/ai-shell
- https://github.com/Significant-Gravitas/AutoGPT
- https://github.com/AntonOsika/gpt-engineer

To add a skill: copy its system_prompt into skills/registry.json
following the same format as the existing skills.

---

## QUICK START (no internet)

1. Install Ollama
2. Run: ollama pull tinyllama
3. Run: python -m http.server 8080 (in project folder)
4. Open: http://localhost:8080
5. Start chatting — free forever!
