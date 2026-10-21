# Apartment Installment Calculator

**[▶ Open the app](https://claude.ai/artifact/RxyHRxzmSeF9c4jaEchhZ8)**

Work out how much an apartment really costs when you buy it in installments or on credit. Enter the price and your first payment, choose an interest rate and a term of up to 60 months, and the calculator shows your monthly payment, the total interest and the full amount you will pay.

The app works in **English, Russian and Uzbek** and supports the **Uzbek so'm (UZS)**.

---

## Features

### What you enter
| Input | What it does |
|---|---|
| **Total price** | The full price of the apartment. |
| **Area (m²)** | The size of the apartment. |
| **Price per 1 m²** | Connected to the price and area. Change one and the others update. |
| **Currency** | USD, UZS (so'm), EUR, GBP, RUB, KZT, AED, or no currency. |
| **Payment method** | Pay in installments or credit, or pay the full amount in cash. |
| **First payment** | Enter an amount or a percentage, use the slider, or tap 0% / 10% / 20% / 30% / 50%. |
| **Interest rate** | The yearly rate. Use 0% for an interest-free plan from the developer. |
| **Term** | From 1 to 60 months. |

### What you get
- **Monthly payment**, shown in large numbers.
- **First payment**, **amount financed**, **total interest** and **total you pay**.
- **Price per m²** both before and after interest.
- A colored bar showing how the total splits into first payment, financed amount and interest.
- **First payment comparison:** a table showing the monthly payment and total cost for first payments from 0% to 70%. Tap a row to use it.
- **Payment schedule:** month by month, showing how much of each payment goes to the loan and to interest, and how much you still owe.

### Interface
- Switch the language with the **EN / RU / UZ** buttons. Your choice of language and currency is remembered in your browser.
- A modern apartment complex is drawn in the background.
- Light and dark themes follow your device setting.
- Works on phones and desktop.

### Exchange rate
- Shows today's official **USD → UZS** rate from the Central Bank of Uzbekistan ([cbu.uz](https://cbu.uz)). You can also pick EUR, GBP, RUB, KZT or AED.
- Converts your monthly payment and total into so'm (or into dollars if you work in so'm).

### Part 2: Deposit income
Below the divider is a second calculator for a **so'm deposit**:
- Enter an amount in **US dollars**. It is converted to so'm automatically at the Central Bank rate. You can change the rate to your bank's rate.
- Choose the **yearly deposit rate** (around 20% is typical in Uzbekistan).
- See your **monthly income in so'm**, its dollar equivalent, and the yearly income.
- **How much to invest:** enter the monthly income you want in so'm, or tap the button to use your apartment's monthly payment, and it shows how many **US dollars** you need to deposit.

---

## How the payment is calculated

The calculator uses **equal monthly payments** (an annuity):

```
monthly payment = L × r / (1 − (1 + r)^−n)
```

- `L` = price − first payment (the amount financed)
- `r` = yearly interest rate ÷ 12 ÷ 100
- `n` = term in months

If the rate is 0%, the monthly payment is simply `L ÷ n`.

**Example:** a price of 120,000, a 20% first payment (24,000), 12% per year and 36 months give a monthly payment of about **3,188.57**.

**Deposit income** uses simple monthly interest:

```
monthly income (so'm) = dollars × exchange rate × yearly rate ÷ 12 ÷ 100
dollars needed        = wanted monthly income × 12 × 100 ÷ yearly rate ÷ exchange rate
```

**Example:** $50,000 at 12,012.30 so'm per dollar and 20% a year gives about **10,010,250 so'm per month**.

> Fees, insurance and taxes are not included. Check the final numbers with your bank or developer.

> **Live rates:** when you open `index.html` directly or from GitHub Pages, the app loads today's rate from cbu.uz. The claude.ai link cannot connect to other websites, so it shows the last saved rate and labels it with its date.

---

## Running it

- **Online:** open the [app link](https://claude.ai/artifact/RxyHRxzmSeF9c4jaEchhZ8). The link is private. To let someone else use it, share it from the **Share** menu on the page.
- **Locally:** open [`index.html`](index.html) in any modern browser. Nothing needs to be installed. An internet connection is needed only to load the fonts.

## Files

```
property_calculator/
├── index.html   # the whole app: layout, styles, translations and calculations
└── README.md    # this file
```
# property_calculator
