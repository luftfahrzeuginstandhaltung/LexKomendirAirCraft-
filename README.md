# LexKomendirAirCraft — KOM-AK-X1-ALPHA
**ATA 100 · RBAC 65 · NACA 2412 · Mach 0.72 · Brasil 2026**

OCULUS EXERCITUS · FIDES ET HONOR · MUITO ALTO, MUITO LONGE, SEMPRE

### 🚀 Site Oficial (GitHub Pages)
https://lexkomendiraircraft.github.io/luftfahrzeuginstandhaltung


### 📁 Estrutura
# LexKomendirAirCraft — KOM-AK-X1-ALPHA
**ATA 100 · RBAC 65 · NACA 2412 · Mach 0.72 · Brasil 2026**

OCULUS EXERCITUS · FIDES ET HONOR · MUITO ALTO, MUITO LONGE, SEMPRE

### 🚀 Site Oficial (GitHub Pages)
https://lexkomendiraircraft.github.io/luftfahrzeuginstandhaltung

### 📁 Estrutura kit t
# ==============================================================
#  LEXKOMENDIRAIRCRAFT · KOM-AK-X1-ALPHA
#  CÓDIGO ÚNICO COMPLETO — 34 Diagramas + HTML
#  ATA 100 · RBAC 65 · NACA 2412 · Mach 0.72 · Brasil 2026
# ==============================================================
#  pip install matplotlib
#  python LexKomendirAirCraft_Completo.py
# ==============================================================

import matplotlib.pyplot as plt
from matplotlib.patches import FancyBboxPatch
import os

AZUL='#0B3D91'; OURO='#C8A951'; CAIXA='#E8F0FE'; TEXTO='#1E293B'; CINZA='#64748B'

os.makedirs("assets/diagramas", exist_ok=True)
os.makedirs("assets/videos", exist_ok=True)

def gerar_diagrama(titulo, ata, blocos, arquivo):
    fig, ax = plt.subplots(figsize=(12, 8))
    ax.axis('off')
    fig.patch.set_facecolor('white')
    ax.text(0.02,0.96,f"{titulo} | {ata} | KOM-AK-X1-ALPHA",fontsize=11,weight='bold',color=AZUL,transform=ax.transAxes)
    ax.plot([0.02,0.98],[0.94,0.94],color=OURO,lw=3,transform=ax.transAxes)
    ax.text(0.02,0.91,"OCULUS EXERCITUS · NACA 2412 · Mach 0.72 · Material autoral — LexKomendirAirCraft",fontsize=7,color=CINZA,transform=ax.transAxes)
    for i,(nome,desc) in enumerate(blocos):
        x=0.05+(i%3)*0.32; y=0.62-(i//3)*0.30
        ax.add_patch(FancyBboxPatch((x,y),0.28,0.24,boxstyle="round,pad=0.02",facecolor=CAIXA,edgecolor=AZUL,lw=1.5,transform=ax.transAxes))
        ax.text(x+0.02,y+0.19,nome,fontsize=9,weight='bold',color=TEXTO,transform=ax.transAxes)
        ax.text(x+0.02,y+0.11,desc,fontsize=7.5,color=TEXTO,transform=ax.transAxes,va='top')
    plt.savefig(f"assets/diagramas/{arquivo}",dpi=240,bbox_inches='tight')
    plt.close()
    print(f"✅ GERADO: assets/diagramas/{arquivo}")

DIAGRAMAS = [
    {"titulo":"SISTEMA HIDRAULICO COMPLETO","ata":"ATA 29-00","blocos":[("29-11 Reservatorio 2,5L","MIL-H-5606\nCapacidade medida"),("29-21 Bomba Motor 3000 psi","Gera pressao · 5 GPM"),("29-22 Acumulador N2 1000 psi","Reserva · Emerg
