# Biblioteca de Equipamentos · Mineração e Beneficiamento

Catálogo técnico pesquisável de equipamentos para plantas de beneficiamento de minérios,
construído a partir de catálogos online de fornecedores. Foco em **dimensionamento**:
cada equipamento traz especificações técnicas, faixas de aplicação, dados comerciais
(fabricante, modelo, link do catálogo) e as fórmulas/critérios de dimensionamento.

## Categorias

- Britagem e moagem
- Transporte e classificação
- Separação e concentração

## Estrutura do projeto

```
.
├── index.html              # Site (busca + filtros + ficha técnica)
├── data/
│   └── equipamentos.json   # Banco de dados da biblioteca
├── .nojekyll               # Garante que o GitHub Pages sirva a pasta data/
└── README.md
```

## Como adicionar um equipamento

Edite `data/equipamentos.json` e acrescente um objeto ao array `equipamentos`:

```json
{
  "id": "fabricante-modelo",
  "categoria": "Britagem e moagem",
  "subtipo": "Britador de mandíbulas",
  "fabricante": "Metso",
  "modelo": "C120",
  "verificado": false,
  "specs": { "capacidade_t_h": {"min": 0, "max": 0}, "potencia_kw": null },
  "aplicacao": { "faixa": "", "material": "", "curva_desempenho_url": null },
  "comercial": { "catalogo_url": "", "contato": "", "preco_referencia": null },
  "dimensionamento": { "criterio": "", "formula_potencia": "", "variaveis": [] }
}
```

Use `verificado: true` somente quando os números forem conferidos na folha de dados
oficial do fabricante. Itens `false` aparecem no site com a tag **"A verificar"**.

## Publicar no GitHub Pages

```bash
git init
git add .
git commit -m "Biblioteca de equipamentos - versão inicial"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/SEU_REPO.git
git push -u origin main
```

Depois, no GitHub: **Settings → Pages → Branch: main / (root) → Save**.
Em ~1 minuto o site fica disponível em `https://SEU_USUARIO.github.io/SEU_REPO/`.

## Aviso

As especificações são referência de engenharia e **não substituem a folha de dados
oficial** do fabricante. Confirme capacidade, potência, pesos e dimensões no catálogo
antes de qualquer especificação de projeto.
