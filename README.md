```text
 ███╗   ██╗███████╗██╗   ██╗██████╗ ██╗  ██╗
 ████╗  ██║██╔════╝██║   ██║██╔══██╗╚██╗██╔╝
 ██╔██╗ ██║█████╗  ██║   ██║██████╔╝ ╚███╔╝
 ██║╚██╗██║██╔══╝  ██║   ██║██╔══██╗ ██╔██╗
 ██║ ╚████║███████╗╚██████╔╝██║  ██║██╔╝ ██╗
 ╚═╝  ╚═══╝╚══════╝ ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝
        ring-0 · edge agent · noc
```

# Vinicius Nascimento

Opero segurança em servidor de hospedagem. O que interessa é o que acontece **depois** do login: processo web virando shell, lateral SSH, arquivo plantado no `public_html`.

Construo o **[NeurX](https://neurx.online)** — NOC que mata isso no kernel (eBPF/Tetragon), bane IP no perímetro e cura arquivo no edge sem derrubar o site.

<p align="center">
  <a href="https://neurx.online"><img src="https://img.shields.io/badge/NOC-neurx.online-c4a35a?style=for-the-badge&labelColor=0a0c0e" alt="neurx.online" /></a>
  <img src="https://img.shields.io/badge/eBPF-Tetragon-6b8f71?style=for-the-badge&labelColor=0a0c0e" alt="eBPF" />
  <img src="https://img.shields.io/badge/edge-heal%20%2B%20ban-c45c4a?style=for-the-badge&labelColor=0a0c0e" alt="edge" />
</p>

---

### O que o NeurX faz de fato

| Camada | Função |
|--------|--------|
| **Ring 0** | Políticas Tetragon — Sigkill em reverse shell, memfd, miner, recon, destruição de disco… |
| **Edge** | Agente no VPS/WHM: scan, heal in-place, learn de FP, sync de blocklist |
| **Perímetro** | nftables / CrowdSec — ban com TTL, lista viva no painel |
| **NOC** | [neurx.online](https://neurx.online) — frota, eventos, MITRE, bloqueios |

Fluxo que importa: **evento → ban → cura → revisão humana**. Quarentena automática de site? Não. Só malware confirmado no painel.

---

### Dia a dia

- Shared, VPS e WHM/cPanel no sangue (Enhance, LiteSpeed, lsphp)
- PHP/Node em produção, Redis/BullMQ, Docker no core
- Automação de servidor, painéis, WHMCS, Gen3

```
Node · Bun · PHP · React · Redis · Docker · Linux · eBPF · nftables
```

---

### Contato

Quer falar de NeurX, hospedagem ou parceria de infra: issue neste perfil ou mensagem no GitHub.

`MonkeyHacker91` · Brasil
