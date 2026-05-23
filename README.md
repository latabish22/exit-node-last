# Exit Node Relay for MasterHttpRelayVPN-RUST

This is an exit node relay service for MasterHttpRelayVPN-RUST. It allows bypassing Cloudflare-protected sites that block Google datacenter IPs.

## Deployment

### Deploy to Deno Deploy

1. Go to https://deno.deploy
2. Sign in with GitHub
3. Click "New Project"
4. Select "Deploy from GitHub"
5. Choose this repository (`latabish22/exit-node-last`)
6. Select `exit_node.ts` as the entry point
7. Click Deploy

### Get Your Deployment URL

After deployment, you'll get a URL like: `https://your-project-name.deno.dev`

## Configuration

Your PSK (Pre-Shared Key) is already set in `exit_node.ts`:
```
a7f2e9b1c4d6f8a3e5b7d9c1f3a5e7b9
```

Add this to your `mhrv-rs config.toml`:

```toml
[exit_node]
enabled = true
relay_url = "https://your-deployment-url.deno.dev"
psk = "a7f2e9b1c4d6f8a3e5b7d9c1f3a5e7b9"
mode = "selective"
hosts = ["chatgpt.com", "claude.ai", "x.com", "grok.com", "openai.com"]
```

## Security

⚠️ **Important**: The PSK is your only security. Treat it like a password:
- Do NOT commit it to public repositories
- Do NOT share it publicly
- Rotate it if you suspect it's leaked
- Change it to a new value if needed using: `openssl rand -hex 32`

## Support

For issues related to MasterHttpRelayVPN-RUST, visit: https://github.com/therealaleph/MasterHttpRelayVPN-RUST
