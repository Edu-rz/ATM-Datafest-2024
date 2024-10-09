# Daily ATM Withdrawal Demand Prediction

## Initial Dataset

- **fecha_transaccion**: Transaction date
- **codigo_cajero**: ATM id
- **tipo_cajero**: Type A or B
- **saldo_inicial**: Quantity of money at start of the day
- **demanda**: Demand in Soles (PEN)
- **abastecimiento**: Amount of money supplied
- **saldo_final**: Quantity of money at end of the day

## Feature Engineering

### General
- **Weekday**: Day of the week (MONDAY, TUESDAY, ...)

### Holiday Sequence
- **Holiday Sequence**: Sequence of holidays and working days (e.g., WWW, WHW, HHH)
- **isYesterdayHoliday**: Was yesterday a holiday? (True/False)
- **isHoliday**: Is today a holiday? (True/False)
- **isTomorrowHoliday**: Is tomorrow a holiday? (True/False)

### Workday Sequence
- **isYesterdayWeekday**: Was yesterday a workday? Monday to Friday (True/False)
- **isWeekday**: Is today a workday? Monday to Friday (True/False)
- **isTomorrowWeekday**: Is tomorrow a workday? Monday to Friday (True/False)

### Payment Periods
> Based on holiday and workday criteria.
- **isPaymentDay**: Is it a payment day (end of the month or mid-month)? (True/False)
- **isPayweek**: Is it the payment week (mid-month or end of the month)? (True/False)

### More Metrics
- **rolling_mean_weekday**: The average demand for two days of the same past day of the week (e.g., on two Tuesdays, on two Wednesdays) (True/False)
- **rolling_max**: Maximum demand value for the week
- **lag_7**: The amount of demand seven days ago
- **rolling_max_weekday**: The maximum demand value for two of the same past day of the week (e.g., on two Tuesdays, on two Wednesdays)
- **rolling_std**: Weekly demand standard deviation
- **rolling_mean**: Average monthly demand value