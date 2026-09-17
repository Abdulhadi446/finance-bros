# Finance Bros

Investment scenario tools for comparing recurring contributions, growth, dividends, fees, taxes, and inflation.

## Files

### `investment_scenario_playground.xlsx`

The Excel workbook is the editable, spreadsheet-based version of the model. It contains three worksheets:

- **Inputs**: change the starting balance, monthly contribution, contribution increases, time horizon, growth, dividend, fee, tax, and inflation assumptions.
- **Summary**: review the headline results and scenario comparison.
- **Calculation**: inspect the month-by-month calculations behind the summary.

Open the workbook in Microsoft Excel, LibreOffice Calc, or another compatible spreadsheet application. Update the input cells, then recalculate the workbook if your application does not recalculate automatically. Keep the input units and percentages shown in the workbook when entering values.

### `index.html`

The HTML file is a standalone browser template called **Compound Ledger**. It provides:

- Presets for an S&P 500 average, bond fund, high-growth stock, and high-yield dividend scenario.
- Controls for starting balance, monthly contributions, annual contribution raises, time horizon, price growth, dividends, dividend growth, fees, taxes, and inflation.
- Three comparisons: no dividend, dividends paid as cash, and dividends reinvested.
- Nominal versus today's-dollar display, selectable currency labels, a results table, and charts.
- Local browser storage for the last-used inputs.

### `styles.css`

The shared visual layer for the calculator. It contains the paper/dark theme, controls, tables, chart frame, and FAQ layout. Keeping it outside the HTML makes visual changes easier to review without changing the model.

### `docs/USAGE.md`

Plain-language instructions for the main workflows: a one-month estimate, a long-term accumulation scenario, a portfolio blend, and a withdrawal test.

### `docs/FAQ.md`

Questions about the assumptions, taxes, volatility range, dividends, presets, and what the result does not predict.

To use it, double-click `index.html` or open it in a modern browser. The chart library is loaded from the jsDelivr CDN, so charts require an internet connection; the calculator controls and results still work without the chart library. No build step or server is required. For local development, `python3 -m http.server 8000` serves the project directory.

## Quick start

1. Choose a preset or enter your own assumptions.
2. Select `Months` for a short monthly estimate, or `Years` for a longer horizon.
3. Set the monthly contribution and optional stop date.
4. Compare no dividend, cash dividend, and reinvested dividend scenarios.
5. Use `Portfolio blend`, `±25% range`, or withdrawals when those questions match your planning case.

The browser saves the latest input values locally under `compound-ledger-inputs`. Nothing is sent to a project server.

## Model notes

The calculator compounds each month. Contributions are added at the start of each month, price growth is applied after contributions, and dividends are either reinvested or accumulated as cash depending on the selected scenario. Fees reduce monthly growth, dividend taxes reduce dividend income, and inflation converts nominal values into today's purchasing power.

These tools are scenario planners, not investment advice. They use simplified assumptions and do not predict market performance, brokerage costs, currency movements, or an individual's tax situation.

## License

No license has been specified yet. Add one before accepting external contributions or redistributing the project.