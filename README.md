# bnarch

Instalador Arch Linux personalizado (eusouobn) com suporte a **Niri**, **Labwc** e **Hyprland**.

## Estrutura

```
bnarch/
├── install.sh           # Instalador base (live Arch ISO)
└── scripts/
    ├── niri.sh          # Pós-instalação do Niri (clona dotfiles de eusouobn/niri)
    ├── labwc.sh         # Pós-instalação do Labwc (clona dotfiles de eusouobn/labwc)
    ├── hyprland.sh      # Pós-instalação do Hyprland (clona dotfiles de eusouobn/hyprland)
    ├── github.sh        # Configuração de identidade git + login do GitHub CLI
    └── mangohud-config.sh  # Gera config do MangoHud (usado pelo Labwc)
```

Os dotfiles de cada WM ficam nos respectivos repos; o script de pós-instalação
escolhido clona o repo correto para `~/.config`.

## Como usar

No ambiente live do Arch ISO:

```bash
git clone https://github.com/eusouobn/bnarch.git
sudo bash bnarch/install.sh
```

Durante a instalação, selecione o ambiente em **8/12 — Interface Gráfica**:

- `10) Niri`
- `11) Labwc`
- `12) Hyprland`

O instalador baixa automaticamente para `~/scripts/` apenas o script de
pós-instalação correspondente ao ambiente escolhido (além de `github.sh` e
`mangohud-config.sh` quando aplicável).

## Após reiniciar

```bash
bash ~/scripts/niri.sh       # ou labwc.sh / hyprland.sh
bash ~/scripts/github.sh     # identidade git + login no GitHub
```
