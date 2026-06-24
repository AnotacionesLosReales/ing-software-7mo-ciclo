# Semana 4: Ecuación equivalente del valor - Flujo de fondos 

## ¿Qué es el Flujo de Fondos?

Es el registro ordenado en el tiempo de todos los **ingresos (+)** y **egresos (−)** de dinero que genera un proyecto.

Se organiza en una **línea de tiempo** donde:

- **t = 0** → Momento de la inversión inicial
- **t = 1, 2, 3...n** → Periodos futuros (años, meses, etc.)

---

## 1. Valor del Dinero en el Tiempo

>  **Ejemplo:** $1,000 hoy vale MÁS que $1,000 dentro de un año, porque hoy los puedes invertir y ganar intereses.

### Capitalización → llevar dinero al FUTURO

$$FV = PV \times (1 + i)^n$$

### Descuento → traer dinero al PRESENTE

$$PV = \frac{FV}{(1 + i)^n}$$

---

###  Ejemplo 1 — Capitalización

> Tienes S/ 5,000 hoy. Los depositas al 10% anual. ¿Cuánto tendrás en 3 años?

$$FV = 5{,}000 \times (1 + 0.10)^3 = 5{,}000 \times 1.331 = \textbf{S/ 6,655}$$

---

###  Ejemplo 2 — Descuento

> Te prometen pagar S/ 8,000 dentro de 4 años. Si la tasa es 12% anual, ¿cuánto vale hoy ese dinero?

$$PV = \frac{8{,}000}{(1 + 0.12)^4} = \frac{8{,}000}{1.5735} = \textbf{S/ 5,084.19}$$

---

## 2. Tipos de Flujo de Caja

### Flujo Convencional 

Un solo cambio de signo (negativo al inicio, luego positivo).

```
  −10,000   +3,000   +3,000   +3,000   +3,000
     0          1        2        3        4
```

### Flujo No Convencional 

Más de un cambio de signo → la TIR puede tener múltiples valores.

```
  +5,000   −2,000   +4,000   −1,000
     0         1        2        3
```

---

## 3. Estructura del Flujo de Caja Libre (FCL)

|Concepto|Signo|
|---|---|
|Inversión inicial|−|
|Ingresos del periodo|+|
|Costos operativos|−|
|Mantenimiento|−|
|Valor de salvataje (último periodo)|+|
|Recuperación capital de trabajo (último periodo)|+|

### Fórmula por periodo:

$$FCL_t = \text{Ingresos}_t - \text{Egresos}_t$$

$$FCL_n = \text{Ingresos}_n - \text{Egresos}_n + \text{Salvataje}$$

---

###  Ejemplo 3 — Construir un FCL completo

> Una empresa invierte S/ 20,000 en una máquina. Genera ingresos de S/ 8,000 anuales y tiene costos operativos de S/ 2,000 anuales durante 4 años. Al final vende la máquina en S/ 3,000 (salvataje).

**Construcción del FCL:**

|Periodo|Ingresos|Egresos|Salvataje|FCL|
|---|---|---|---|---|
|0|—|−20,000|—|**−20,000**|
|1|+8,000|−2,000|—|**+6,000**|
|2|+8,000|−2,000|—|**+6,000**|
|3|+8,000|−2,000|—|**+6,000**|
|4|+8,000|−2,000|+3,000|**+9,000**|

**Línea de tiempo:**

```
        +6,000  +6,000  +6,000  +9,000
  |--------|--------|--------|--------|
  0        1        2        3        4
  |
−20,000
```

---

## 4. Valor Actual (VA) — Traer todos los flujos al presente

$$VA = \sum_{t=1}^{n} \frac{FC_t}{(1 + COK)^t}$$

---

###  Ejemplo 4 — Calcular el VA del Ejemplo 3 (COK = 10%)

$$VA = \frac{6{,}000}{1.10^1} + \frac{6{,}000}{1.10^2} + \frac{6{,}000}{1.10^3} + \frac{9{,}000}{1.10^4}$$

|Periodo|FCL|Factor $(1.10)^t$|FCL descontado|
|---|---|---|---|
|1|6,000|1.1000|5,454.55|
|2|6,000|1.2100|4,958.68|
|3|6,000|1.3310|4,507.89|
|4|9,000|1.4641|6,147.13|
|**TOTAL**|||**21,068.25**|

$$VA = \textbf{S/ 21,068.25}$$

---

## 5. VAN — Valor Actual Neto

> Mide cuánto más rico te haces al invertir en el proyecto vs. dejarlo en el banco al COK.

$$VAN = -\text{Inversión} + VA$$

**Criterio:**

|Resultado|Decisión|
|---|---|
|VAN > 0|Aceptar — el proyecto genera riqueza|
|VAN < 0| Rechazar — es mejor invertir al COK|
|VAN = 0| Indiferente|

---

###  Ejemplo 5 — VAN del Ejemplo 3

$$VAN = -20{,}000 + 21{,}068.25 = \textbf{+S/ 1,068.25}$$

>  VAN > 0 → **Se acepta el proyecto.** Generas S/ 1,068.25 más que si hubieras puesto el dinero al 10%.

---

## 6. Anualidad — Flujos iguales cada periodo

Cuando el flujo es el mismo todos los periodos (R = cuota fija):

### Valor Presente de una Anualidad:

$$PV = R \times \frac{(1+i)^n - 1}{i \times (1+i)^n}$$

### Cuota desde un capital (CAUE):

$$R = PV \times \frac{i \times (1+i)^n}{(1+i)^n - 1}$$

---

###  Ejemplo 6 — Anualidad (Valor Presente)

> Un proyecto genera S/ 4,000 anuales durante 5 años. La tasa es 15%. ¿Cuánto vale hoy esa serie de pagos?

$$PV = 4{,}000 \times \frac{(1.15)^5 - 1}{0.15 \times (1.15)^5} = 4{,}000 \times \frac{2.0114 - 1}{0.15 \times 2.0114}$$

$$PV = 4{,}000 \times \frac{1.0114}{0.3017} = 4{,}000 \times 3.3522 = \textbf{S/ 13,408.80}$$

---

###  Ejemplo 7 — Calcular cuota CAUE

> Compraste una máquina en S/ 50,000 con vida útil de 6 años. TEA = 12%. ¿Cuánto deberías "cobrar" anualmente para recuperar tu inversión? (esto es el CAUE)

$$R = 50{,}000 \times \frac{0.12 \times (1.12)^6}{(1.12)^6 - 1} = 50{,}000 \times \frac{0.12 \times 1.9738}{1.9738 - 1}$$

$$R = 50{,}000 \times \frac{0.2369}{0.9738} = 50{,}000 \times 0.2432 = \textbf{S/ 12,161 anuales}$$

---

## 7. Perpetuidad — Flujo que dura para siempre

Cuando el flujo **nunca se detiene** (n → ∞):

$$PV = \frac{R}{i}$$

---

### Ejemplo 8 — Perpetuidad (Costo Capitalizado)

> Una obra requiere mantenimiento anual de S/ 5,000 para siempre. COK = 20%. ¿Cuánto debes apartar hoy para cubrir esos pagos eternamente?

$$PV = \frac{5{,}000}{0.20} = \textbf{S/ 25,000}$$

> Si depositas S/ 25,000 al 20%, generas exactamente S/ 5,000 anuales para siempre.

---

## 8. Conversión de Tasas

### TEA a tasa de periodo menor (mensual, bimestral, etc.):

$$i_{periodo} = (1 + TEA)^{1/m} - 1$$

Donde `m` = cuántos periodos hay en un año.

### TEA a tasa de n años:

$$TE_{nA} = (1 + TEA)^n - 1$$

---

### Ejemplo 9 — Conversión de tasas

> TEA = 24%. ¿Cuál es la tasa mensual equivalente?

$$i_{mensual} = (1 + 0.24)^{1/12} - 1 = 1.24^{0.0833} - 1 = 1.01813 - 1 = \textbf{1.813% \ mensual}$$

> TEA = 15%. ¿Cuál es la tasa equivalente para 8 años?

$$TE_{8A} = (1 + 0.15)^8 - 1 = 3.0590 - 1 = \textbf{205.9%}$$

---

## 9. Resumen Visual de Fórmulas

```
CAPITALIZAR (ir al futuro):     FV = PV × (1+i)ⁿ

DESCONTAR (volver al presente): PV = FV / (1+i)ⁿ

VALOR ACTUAL de flujos:         VA = Σ FCt / (1+COK)ᵗ

VAN:                            VAN = −Inversión + VA

ANUALIDAD (PV conocido→cuota): R = PV × [i(1+i)ⁿ / ((1+i)ⁿ−1)]

ANUALIDAD (cuota→PV):          PV = R × [(1+i)ⁿ−1 / i(1+i)ⁿ]

PERPETUIDAD:                    PV = R / i

CONVERSIÓN DE TASA:             i_periodo = (1+TEA)^(1/m) − 1
```

---

## 10. Tabla de Indicadores — Qué necesitan

|Indicador|Necesita|Fórmula rápida|
|---|---|---|
|**VAN**|FCL + COK|−Inversión + Σ FCt/(1+COK)ᵗ|
|**TIR**|FCL|Tasa donde VAN = 0|
|**B/C**|FCL + COK|VA / Inversión|
|**PRD**|FCL + COK|Periodos hasta VA acumulado = Inversión|
|**VAC**|Costos + COK|Inversión + Σ Costos/(1+COK)ᵗ|
|**CAUE**|VAC + n + i|VAC × [i(1+i)ⁿ / ((1+i)ⁿ−1)]|
|**CC**|CAUE + i|CAUE / i|
