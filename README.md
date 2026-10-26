# Naked Drums

Kit de bateria multi-mic **Naked Drums** (Wilkinson Audio), portado do formato SFZ para o **DrumGizmo**.

- **10 round-robins** por instrumento
- **Até 5 camadas de velocity**
- **16 canais** de mic independentes (kick in/sub, snare top/bot, toms, hats, OH, close room, far rooms, mid-side)
- **24-bit / 44.1 kHz** em WAV multicanal
- **Midimap pronto** para MIDI do **Superior Drummer 3**

> Baseado no [SFZ original](https://github.com/sfzinstruments/WilkinsonAudio.NakedDrums) de kinwie / Wilkinson Audio, sob CC BY 4.0.

---

## Download

**[⬇ Baixar a versão mais recente](https://github.com/realsigmamusic/nakeddrums/releases/latest)**

Pacote: `NakedDrums-DrumGizmo-vX.Y.Z.tar.zst` (~2,5 GB descompactado, ~1,2 GB comprimido).

Conteúdo após descompactar:

```
NakedDrums/
├── drumkit.xml
├── midimap1.xml
├── midimap2.xml
├── instruments/  ← XMLs por peça
└── Samples/      ← ~1500 WAVs multicanal, 24-bit
```

---

## Requisitos

| Item | Versão mínima |
|---|---|
| **DrumGizmo** | **0.9.20** ou mais novo |
| Espaço em disco | ~2,5 GB |
| RAM (kit completo) | ~4 GB |

> **Por que 0.9.20?** Esta versão corrige o problema de round-robin que afetava kits com 3 camadas (hi-hat, tons) e traz o `powermap`. Versões antigas causam mistura entre velocity e round-robin.

---

## Instalação

1. Descompacte o arquivo baixado em qualquer pasta, por exemplo `~/DrumKits/`.
2. Abra o DrumGizmo (standalone ou plugin).
3. **File → Open Kit** e selecione `~/DrumKits/NakedDrums/drumkit.xml`.
4. Pronto. O kit carrega em 16 canais.

### No Ardour / Reaper / Mixbus

Adicione o DrumGizmo como plugin de instrumento, abra o kit pela GUI do plugin, e roteie cada um dos **16 canais** para tracks individuais (o DrumGizmo expõe todos os outputs).

---

## Midimap para Superior Drummer 3

O SD3 usa MIDI Core com 122 articulações. Como o NakedDrums tem 23 instrumentos, algumas notas são reaproveitadas. Dois midimaps prontos:

| Arquivo | Caixa usada |
|---|---|
| `midimap-sd3-nakeddrums-snare1.xml` | Snare1 (Ayotte 14"x5" silver sparkle) |
| `midimap-sd3-nakeddrums-snare2.xml` | Snare2 (Pearl 13"x6,5" Joey Jordison) |

### Como carregar

1. Copie o midimap escolhido para `NakedDrums/`.
2. No DrumGizmo: **Configurações → Midimap → selecionar arquivo**.
3. Exporte o MIDI do SD3 como MIDI file normal e toque no DrumGizmo.

---

## Canais disponíveis (16)

1. KickIn
2. KickSub
3. SnareTop
4. SnareBot
5. Hats
6. Tom1
7. Tom2
8. Tom3
9. Tom4
10. Tom5
11. OHL
12. OHR
13. FarRoomsL
14. FarRoomsR
15. CloseRoom 
16. MidSide

Cada canal pode ser roteado para uma track separada e processado individualmente. O kit já vem com **hi-hat atenuado em −9 dB** e **MidSide em mono** para equilibrar o mix de fábrica — mas todos os canais estão intactos e você pode processar como quiser.

- Yamaha Recording Custom - Cherry
- Remo Heads
- 22" Kick Drum
- 10", 12", 13",  14", 16" Toms
- Ayotte 14" x 5" silver sparkle snare
- Pearl 13" x 6.5" Joey Jordison Signature Snare
- Mixture of Sabian HH/AA/AAX and some Zildjian A Series
    - 2 Splashes
    - 2 Crashes (bow and bell)
    - 2 Chinas
    - Ride (bow and bell)
    - Hi-Hats

---

## Dicas de uso

### Ajustando a dinâmica

Todos os samples usam `normalized="true"`, que faz o DrumGizmo escalar o volume pela velocity MIDI. Isso restaura a dinâmica em instrumentos com poucas camadas (hi-hat e tons têm 3; o sidestick tem apenas 1).

### Choke de pratos

O hi-hat tem choke automático: tocar hat fechado/meio/tight/pedal corta o hat aberto. **Cymbals não têm choke** — se você bater duas vezes no mesmo crash, os dois vão soar. Isso é intencional, porque choke em crash é raro em MIDI de bateria e mais frequentemente causava corte indesejado.

### Round-robins

10 variações por instrumento. Em velocidades altas, a diferença entre RRs é sutil (é o mesmo golpe, só com microvariação). A percepção principal vem da variação de velocity.

---

## Limitações conhecidas

- **Hi-hat variável por CC4** não é suportado no DrumGizmo (é uma limitação do engine, não do kit). Você toca notas fixas — Tight, Half, Open, Closed, Pedal — e escolhe qual no seu controlador.
- **Ride Edge** não existe no kit; mapeado para Ride Bow.
- **Brushes, swirls, flams** — o kit não tem amostras específicas; caem em Snare Center.
- **Afinação de tom individual** — não é controlável via DrumGizmo; ajuste no DAW se precisar.

---

## Créditos

- **Gravação e samples**: [Wilkinson Audio](https://www.wilkinsonaudio.com/) — Naked Drums
- **SFZ v2 original**: [kinwie](https://github.com/sfzinstruments/WilkinsonAudio.NakedDrums)
- **Conversão para DrumGizmo**: comunidade DrumGizmo BR
- **Engine**: [DrumGizmo](https://drumgizmo.org/)

## Licença

**[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)** — igual ao original. Use livremente em projetos comerciais e não-comerciais, modifique, redistribua, **desde que credite os autores originais** (Wilkinson Audio + kinwie + este port).

---

## Problemas?

Abra uma issue com:
- Versão do DrumGizmo (`drumgizmo --version`)
- DAW e versão
- Trecho de MIDI que está soando errado (nota + articulação SD3)

Se você só quer usar o kit e algo soa estranho, a primeira coisa a checar é se a **versão do DrumGizmo é 0.9.20+**.