# VECTOR
> `PROJECT: BLUE_PROTOCOL` — Internal Codename

Roguelike hack-and-slash isométrico no Roblox. Combina a sinergia de itens de *The Binding of Isaac* com o combate fluido de *Minecraft Dungeons*, em uma estética **Cybercore / Webcore Blue / Y2K Digital**.

---

## Stack Técnica

| Camada | Tecnologia |
|---|---|
| Engine | Roblox (Luau `--!strict`) |
| Sync | [Rojo](https://rojo.space/) — GitHub ↔ Studio |
| Packages | [Wally](https://wally.run/) |
| Servidor | `ServerScriptService` (autoridade total) |
| Cliente | `StarterPlayerScripts` (VFX + predição) |
| Shared | `ReplicatedStorage` (eventos + módulos) |

---

## Roadmap

### `FASE 0` — Lobby Completo
- [ ] Estrutura de ScreenGui (Main Menu, Character Select, Matchmaking, Settings)
- [ ] Navegação entre telas
- [ ] Estética Webcore/Y2K aplicada pelo Ítalo no Studio
- [ ] Scripts de wiring: abrir/fechar frames, matchmaking via RemoteEvents
- [ ] **Zero UI gerada por código** — tudo desenhado no Studio

### `FASE 1 & 2` — Gameplay Loop & Combate
- [ ] Câmera isométrica fixa (45°) com lag suave
- [ ] Movimentação WASD 8-direcional
- [ ] Dash **Glitch Step** (0.3s, i-frames, cooldown 1.5s)
- [ ] Ataque primário direcional (melee cone ou projétil)
- [ ] Ataque carregado AoE (limpa projéteis + dano em área)
- [ ] Estrutura de salas procedural com transição via pop-ups Hyperlink
- [ ] Progressão de rotas entre setores (estilo Slay the Spire)

### `FASE 3` — Itens, Augments & Sinergias
- [ ] Augments passivos (Vector Split, Data Leak etc.)
- [ ] Sistema de **Fusion** — combinação muda o ataque, não soma stats
- [ ] 3 slots de Programas Ativos (Firewall.exe, Lag Spike, Blue Screen Beam)
- [ ] Loot via pop-up de 3 opções ao fim de arenas
- [ ] Terminais de compra no mapa

### `FASE 4` — Inimigos, Bosses & Corrupção
- [ ] Inimigos geométricos puros (cubos, pirâmides, esferas)
- [ ] Inimigos corrompidos (manequins wireframe com glitch)
- [ ] Ataques telegrafados com linhas de vetor no chão
- [ ] Bosses Fase 1: Monolitos + estátuas greco-romano digital
- [ ] Bosses Fase 2: Antivírus + processos de SO

### `FASE 5` — UI, VFX & Som
- [ ] HUD diegética flutuante no personagem
- [ ] VFX de impacto (`CRIT_01 // 45 DMG`, `ERR_NULL`, explosão de polígonos)
- [ ] Mortes: desintegração em partículas de dados
- [ ] Trilha Breakcore / Glitch Ambient
- [ ] SFX bitcrushed + glitches de áudio

---

## Estrutura do Repositório

```
VECTOR-PROTOCOL/
├── src/
│   ├── ServerScriptService/
│   │   ├── CombatModule.luau
│   │   ├── SynergyEngine.luau
│   │   ├── DungeonGenerator.luau
│   │   └── SessionManager.luau
│   ├── StarterPlayerScripts/
│   │   ├── CameraController.luau
│   │   ├── MovementController.luau
│   │   ├── VFXController.luau
│   │   └── UIController.luau
│   └── ReplicatedStorage/
│       ├── Remotes/
│       ├── Shared/
│       └── Data/
├── default.project.json    ← config do Rojo
├── wally.toml              ← dependências
└── README.md
```

---

## Setup Local (Rojo)

```bash
# 1. Instala o Rojo CLI
aftman install

# 2. Clona o repo
git clone https://github.com/edu6767-svg/VECTOR-PROTOCOL.git

# 3. Inicia o servidor Rojo
rojo serve default.project.json

# 4. No Roblox Studio → Plugin Rojo → Connect
```

---

## Time

| Membro | Função |
|---|---|
| **Ítalo** | Modelagem 3D — cenários modulares, props, inimigos, bosses |
| **Miguel** | Animação — idle, run, dash, combos, hitstop |
| **Daniel** | QA — testes de sinergia, bug reports, feedback de game feel |

---

## Diretrizes de Código

- `--!strict` em todos os scripts
- `Task.spawn` / `Task.defer` / `Task.wait` — nunca `spawn()` / `wait()`
- **Nunca confiar no cliente** — dano, cooldowns e validações sempre no servidor
- UI nunca gerada por código — só wiring de elementos feitos no Studio
- Módulos separados por responsabilidade (`CombatModule`, `SynergyEngine` etc.)

---

> `// VECTOR — BUILD 0.0.1 — BLUE_PROTOCOL CONFIDENTIAL`
