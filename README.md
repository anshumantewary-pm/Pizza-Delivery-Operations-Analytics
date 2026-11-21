# Pizza Delivery Operations Analytics

This project is an Excel analysis of pizza delivery operations. It looks at how long deliveries take, what causes delays, and how order complexity and traffic affect delivery speed across five pizza chains and many US cities. The raw order log was enriched with derived operational metrics and then broken into focused workbooks, one each for restaurant efficiency, location coverage, pizza complexity and traffic impact. Each workbook has its own pivot tables and charts.

## Dataset

`Raw Data.xlsx` holds **1,004 delivery orders** (order IDs `ORD001` onward) from five chains: Domino's, Little Caesars, Marco's Pizza, Papa John's and Pizza Hut. The orders are spread across US cities. Each record contains:

- **Order details:** Order ID, restaurant, location, order time, delivery time, order month and hour
- **Product:** pizza size (Small / Medium / Large / XL), pizza type (12 types, e.g. Veg, Non-Veg, Vegan, Cheese Burst, Deep Dish, Thin Crust), toppings count
- **Logistics:** distance (km), traffic level (Low / Medium / High), peak-hour and weekend flags
- **Payment:** payment method (Card, UPI, Wallet, Cash and brand-specific options) and payment category (Online / Offline)
- **Derived metrics:** delivery duration (min), delivery efficiency (min/km), topping density, estimated duration, delay (min), delayed flag, pizza complexity score, traffic impact score, restaurant average time

## Approach

1. **Feature engineering:** turned the order timestamps and attributes into operational KPIs. These are duration, minutes per km, estimated vs actual time, delay, a complexity score based on size and toppings, and a traffic impact score from 1 to 3.
2. **Restaurant efficiency:** pivot of order counts by restaurant and pizza size, with each chain's average delivery time. A filter panel covers payment category, peak hour, weekend, pizza type, month, location and delay status.
3. **Location analysis:** order counts by city for each chain, to show where each brand's volume is concentrated.
4. **Pizza complexity:** topping density and complexity score by restaurant and size, to test whether more complex orders take longer.
5. **Traffic impact:** delay, estimated duration and min/km efficiency by location and restaurant at each traffic impact level.

## Key Findings

From the workbook outputs:

- **Average delivery time by chain:** Papa John's 28.2 min, Little Caesars 28.8 min, Pizza Hut 29.9 min, Domino's 30.3 min, Marco's Pizza 30.3 min. That is a spread of about two minutes between the fastest and slowest chain.
- **Order volume by chain:** Domino's 212, Papa John's 204, Little Caesars 199, Marco's Pizza 195, Pizza Hut 194, for a total of 1,004.
- **Location concentration:** Atlanta, GA has the most orders (78), followed by Milwaukee, WI (71), Louisville, KY (69) and Omaha, NE (68). Several cities are dominated by a single chain. For example, Little Caesars has 67 orders each in Milwaukee, Louisville and Omaha, and Domino's has 56 in Albuquerque.

## Tools & Tech

- **Microsoft Excel:** data cleaning, derived columns, pivot tables, slicer-style filter panels, charts

## Repository Structure

```
.
├── Raw Data.xlsx                        # Enriched order-level dataset (1,004 orders, 25 fields)
├── Efficiency & Total Pizza Store.xlsx  # Restaurant average time, size mix, orders by location
├── Pizza Complexity.xlsx                # Topping density and complexity score by restaurant and size
├── Traffic Impact.xlsx                  # Delay and efficiency by traffic impact level and location
├── LICENSE
└── README.md
```

## How to Open

1. Clone or download the repository.
2. Open any workbook in Microsoft Excel. Start with `Raw Data.xlsx` to see the fields.
3. In `Efficiency & Total Pizza Store.xlsx` and `Traffic Impact.xlsx`, use the **Filter** sheet to change the pivot filters, such as peak hour, weekend or payment category.

## License

Released under the [MIT License](LICENSE).

---

**Author:** Anshuman Tewary · [GitHub](https://github.com/anshumantewary-pm) · [LinkedIn](https://www.linkedin.com/in/tewary-anshuman/)
