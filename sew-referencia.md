# Tabela de referência SEW (motores e motoredutores) — ProjectARK

Usada pelo módulo de seleção de acionamento do pré-dimensionamento.
**Valores nominais aproximados de catálogo SEW** — a seleção final deve ser
confirmada no configurador oficial da SEW (Drive Configurator / Workbench).

## Motores SEW DRN — 4 polos, 60 Hz (~1750 rpm)

| Potência (kW) | Designação (frame) |
|---|---|
| 0,12 | DRN63M4 |
| 0,18 | DRN63L4 |
| 0,25 | DRN71S4 |
| 0,37 | DRN71M4 |
| 0,55 | DRN80S4 |
| 0,75 | DRN80M4 |
| 1,1 | DRN90S4 |
| 1,5 | DRN90L4 |
| 2,2 | DRN100L4 |
| 3,0 | DRN100LC4 |
| 4,0 | DRN112M4 |
| 5,5 | DRN132S4 |
| 7,5 | DRN132M4 |
| 11 | DRN160M4 |
| 15 | DRN160L4 |
| 18,5 | DRN180M4 |
| 22 | DRN180L4 |
| 30 | DRN200L4 |
| 37 | DRN225S4 |
| 45 | DRN225M4 |

Rotação síncrona 4 polos / 60 Hz = 1800 rpm; nominal sob carga ≈ 1750 rpm.

## Redutores SEW série R (helicoidal coaxial) — torque nominal de saída

| Tamanho | Torque nominal Md (Nm) |
|---|---|
| R17 | 130 |
| R27 | 200 |
| R37 | 300 |
| R47 | 450 |
| R57 | 600 |
| R67 | 820 |
| R77 | 1300 |
| R87 | 2000 |
| R97 | 3300 |
| R107 | 4900 |
| R137 | 8000 |
| R147 | 13000 |
| R167 | 18000 |

Faixa de redução típica da série R: i ≈ 3,3 a 290 (multi-estágio).

## Lógica de seleção (transportador helicoidal)

1. Torque no eixo de saída: `T = 9550 · P_acionamento(kW) / n_saída(rpm)` [Nm].
2. Fator de serviço fB = 1,4 (transportador helicoidal, carga uniforme a moderada, ~10 h/dia).
3. Torque de seleção do redutor = `T · fB`.
4. Motor: menor potência padrão SEW ≥ P_acionamento.
5. Redutor série R: menor tamanho com Md ≥ torque de seleção.
6. Redução necessária: `i = n_motor / n_saída` (n_motor ≈ 1750 rpm).
7. Designação do motoredutor: `R{tamanho} DRN{frame}`.

Referências: SEW-EURODRIVE — Catálogo de Motoredutores série R; catálogo de motores DR/DRN.
Configurador oficial: https://www.sew-eurodrive.com
