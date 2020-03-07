# FasterQuant Strategy Builder

The FasterQuant Strategy Builder provides the ability to build strategies in AlgoTerminal via a JSON config file.

- [Conditional Operators](#Conditional-Operators)
- [Example Indicators](#Example-Indicators)

## Conditional Operators

```yaml
BearishCross

BullishCross

GreaterThan

LessThan

GreaterThanOrEqual

LessThanOrEqual

Equal
```

## Example Indicators

```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Open, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.High, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Volume, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Hlc3, FasterQuant.IndicatorInformationsPlugin"
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Atr, FasterQuant.IndicatorInformationsPlugin",
    "period": 10
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.BollingerBandsLower, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20,
    "factor": 2
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.BollingerBandsUpper, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20,
    "factor": 2
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsMax, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.High, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsMin, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsTimeInRange, FasterQuant.IndicatorInformationsPlugin",
    "startHour": 8,
    "startMinute": 30,
    "endHour": 15,
    "endMinute": 14,
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.ParabolicSar, FasterQuant.IndicatorInformationsPlugin",
    "accelerationFactor": 0.02,
    "maxAcceleration": 0.2
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Ema, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Rsi, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Sma, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFastD, FasterQuant.IndicatorInformationsPlugin",
    "periodsK": 8,
    "periodsD": 3
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFastK, FasterQuant.IndicatorInformationsPlugin",
    "periods": 8
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFullD, FasterQuant.IndicatorInformationsPlugin",
    "periodsK": 8,
    "smoothPeriodsK": 3,
    "periodsD": 3
}
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFullK, FasterQuant.IndicatorInformationsPlugin",
    "periods": 8,
    "smoothPeriods": 3
}

```
