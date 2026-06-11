# Hosting & pairing — where your world runs

Every world picks a backend at creation (changeable later via *change provider*):

| Provider | What it means | Pairing |
|---|---|---|
| **Local Browser** | World state saves in your browser (localStorage). Zero setup. | none |
| **MERCURY Node** | Your own machine (Mac/Windows/Linux) joins the fabric. | code |
| **Remote VPS** | Any box you can SSH into. | code |
| **Cloud Server** | AWS / GCP / Azure instance. | code |
| **Fly.io** | A Fly app — the same rail the overworld rides. | code |
| **Render** | A Render web service. | code |

## Pairing a box

1. Create the world, pick the provider → you get a code like `MRCY-7K2M-Q4XN`.
2. On the box, run the link command shown on your world's hosting page:

```bash
curl -X POST https://world.mercury-hq.com/worlds/<world-id>/pair \
  -H 'content-type: application/json' \
  -d '{"code":"MRCY-XXXX-XXXX","node":"my-box"}'
```

3. The hosting page flips to **PAIRED · my-box**. The code is single-purpose — anyone holding it can claim the world's hosting slot, so treat it like a password.
4. Optional: run the MERCURY health agent on the box (`:8913/system/health`) so it reports live stats to the fabric.

Pairing **links** the box to your world. Workload distribution onto paired boxes rolls out with the node-fabric worker runtime.
