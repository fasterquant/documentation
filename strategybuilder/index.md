# FasterQuant Strategy Builder

The FasterQuant Strategy Builder provides the ability to build strategies in Tickblaze via a JSON config file.

- [Conditional Operators](#Conditional-Operators)
- [Indicators](#Indicators)

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

## Indicators


- [ATR](#atr)
- [Bollinger Bands Lower](#bollinger-bands-lower)
- [Bollinger Bands Upper](#bollinger-bands-upper)
- [Exponential Moving Average](#exponential-moving-average)
- [Is Max](#is-max)
- [Is Min](#is-min)
- [Is Time In Range](#is-time-in-range)
- [Open](#open)
- [High](#high)
- [Low](#low)
- [Close](#close)
- [Volume](#volume)
- [HLC3](#hlcs)
- [Max](#max)
- [Min](#min)
- [ParabolicSar](#parabolicSar)
- [Relative Strength Index](#relative-strength-index)
- [Simple Moving Average](#simple-moving-average)
- [Stochastic Fast D](#stochastic-fast-d)
- [Stochastic Fast K](#stochastic-fast-k)
- [Stochastic Full D](#stochastic-full-d)
- [Stochastic Full K](#stochastic-full-k)


### ATR
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Atr, FasterQuant.IndicatorInformationsPlugin",
    "period": 10
}

```

### Bollinger Bands Lower
```yaml
{
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.BollingerBandsLower, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20,
    "factor": 2
}
```

### Bollinger Bands Upper
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.BollingerBandsUpper, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20,
    "factor": 2
}
```

### Exponential Moving Average
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Ema, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
```

### Is Max
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsMax, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.High, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
```

### Is Min
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsMin, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
```

### Is Time In Range
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.IsTimeInRange, FasterQuant.IndicatorInformationsPlugin",
    "startHour": 8,
    "startMinute": 30,
    "endHour": 15,
    "endMinute": 14,
}
```

### Open
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Open, FasterQuant.IndicatorInformationsPlugin"
}
```

### High
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.High, FasterQuant.IndicatorInformationsPlugin"
}
```

### Low
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
}
```

### Close
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
}
```

### Volume
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Volume, FasterQuant.IndicatorInformationsPlugin"
}
```

### Hlc3
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Hlc3, FasterQuant.IndicatorInformationsPlugin"
}
```

### Max
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Max, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.High, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
```

### Min
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Min, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 20
}
```

### ParabolicSar
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.ParabolicSar, FasterQuant.IndicatorInformationsPlugin",
    "accelerationFactor": 0.02,
    "maxAcceleration": 0.2
}
```

### Relative Strength Index
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Rsi, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Close, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
```

### Simple Moving Average
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.Sma, FasterQuant.IndicatorInformationsPlugin",
    "indicatorInfo": {
        "$type": "FasterQuant.IndicatorInformationsPlugin.Low, FasterQuant.IndicatorInformationsPlugin"
    },
    "period": 10
}
```

### Stochastic Fast D
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFastD, FasterQuant.IndicatorInformationsPlugin",
    "periodsK": 8,
    "periodsD": 3
}
```

### Stochastic Fast K
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFastK, FasterQuant.IndicatorInformationsPlugin",
    "periods": 8
}
```

### Stochastic Full D
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFullD, FasterQuant.IndicatorInformationsPlugin",
    "periodsK": 8,
    "smoothPeriodsK": 3,
    "periodsD": 3
}
```

### Stochastic Full K
```yaml
{
    "$type": "FasterQuant.IndicatorInformationsPlugin.StochasticFullK, FasterQuant.IndicatorInformationsPlugin",
    "periods": 8,
    "smoothPeriods": 3
}
```
