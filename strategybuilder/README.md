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
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Atr, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "period": 10
}

```

### Bollinger Bands Lower
```yaml
{
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.BollingerBandsLower, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Close, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20,
    "factor": 2
}
```

### Bollinger Bands Upper
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.BollingerBandsUpper, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Close, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20,
    "factor": 2
}
```

### Exponential Moving Average
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Ema, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Close, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 10
}
```

### Is Max
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.IsMax, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.High, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20
}
```

### Is Min
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.IsMin, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Low, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20
}
```

### Is Time In Range
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.IsTimeInRange, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "startHour": 8,
    "startMinute": 30,
    "endHour": 15,
    "endMinute": 14,
}
```

### Open
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Open, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### High
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.High, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### Low
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Low, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### Close
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Close, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### Volume
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Volume, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### Hlc3
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Hlc3, FasterQuant.StrategyBuilder.Plugin.Indicators"
}
```

### Max
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Max, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.High, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20
}
```

### Min
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Min, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Low, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 20
}
```

### ParabolicSar
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.ParabolicSar, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "accelerationFactor": 0.02,
    "maxAcceleration": 0.2
}
```

### Relative Strength Index
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Rsi, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Close, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 10
}
```

### Simple Moving Average
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Sma, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "indicatorInfo": {
        "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.Low, FasterQuant.StrategyBuilder.Plugin.Indicators"
    },
    "period": 10
}
```

### Stochastic Fast D
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.StochasticFastD, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "periodsK": 8,
    "periodsD": 3
}
```

### Stochastic Fast K
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.StochasticFastK, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "periods": 8
}
```

### Stochastic Full D
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.StochasticFullD, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "periodsK": 8,
    "smoothPeriodsK": 3,
    "periodsD": 3
}
```

### Stochastic Full K
```yaml
{
    "$type": "FasterQuant.StrategyBuilder.Plugin.Indicators.StochasticFullK, FasterQuant.StrategyBuilder.Plugin.Indicators",
    "periods": 8,
    "smoothPeriods": 3
}
```
