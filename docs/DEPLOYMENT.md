# Deployment & Operations Guide: OmniProduct

## 🚀 Live Access & URLs
- **Live Public Access URL:** [/preview/prod-omniproduct-ec3e8c/](/preview/prod-omniproduct-ec3e8c/)
- **Internal Port:** `0`
- **Runtime Engine:** `python_preview`
- **Deployment Status:** `DEPLOYED / ACTIVE`
- **Timestamp:** `2026-09-19T16:15:47.531072+00:00`

## 🛠️ Management & Service Control
### Launch Command
```bash
python3 app.py --port 0
```

### Health Check Probe
```bash
curl -I http://127.0.0.1:0/
```

### Systemd Service Template
```ini
[Unit]
Description=OmniProduct Service
After=network.target

[Service]
Type=simple
WorkingDirectory=/tmp/pytest-of-root/pytest-0/test_agent_chat_engine_with_fu0/workspaces/prod-omniproduct-ec3e8c
ExecStart=/usr/bin/python3 /tmp/pytest-of-root/pytest-0/test_agent_chat_engine_with_fu0/workspaces/prod-omniproduct-ec3e8c/app.py
Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
```

## 🔒 Production Security Protocols
- HTTP-only reverse proxy via Nexus Gateway.
- Dedicated port allocation with zero port conflict.
