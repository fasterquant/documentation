# FasterQuant Application Documentation

The FasterQuant Application is a console application which uses the FasterQuant SDK and supporting projects.  The following documentation explains the various "Runners" in the application and what their configuration properties are.

- [Edge Test Runner](#Edge-Test-Runner)
- [Random Trade Backtest Runner](#Random-Trade-Backtest-Runner)
- [Order Optimization Runner](#Order-Optimization-Runner)
- [Portfolio Optimization Runner](#Portfolio-Optimization-Runner)
- [Portfolio Backtest Runner](#Portfolio-Backtest-Runner)
- [Portfolio Code Generator Runner](#Portfolio-Code-Generator-Runner)

## Edge Test Runner

The Edge Test Runner is designed to discover, test and filter strategies on in and out of sample data.  The output from this runner is later used by the Order Optimization Runner.

### Command Line Usage

```dotnet run yourEdgeTestConfigFile.json runedgetest```

### Edge Test Runner Configuration Properties

| Property Name | Type          | Description  |
| ------------- |-------------| ------------|
| TrainingSymbols | string array | The symbols in which the generated strategies are first tested on. |
| OutOfSampleSymbols | string array | The symbols in which the strategies generated from the training data are tested on. |
| TargetSymbol | string | The symbol in which the strategies are discovered on. |
| TargetTimeFrame | TimeFrameConfiguration | The timeframe in which trades are executued on. |
| HigherTimeFrames | TimeFrameConfiguration array | The higher timeframes used by the tested strategies. |
| TradeType | TradeType | Enumeration indicating the trade type ("Long" or "Short") |
| LimitTrades | bool | Setting true will prevent a strategy from having two concurrent positions for the same symbol. |
| StrategyConditionHandler | IStrategyConditionHandler | Set to the class that implements the IStrategyConditionHandler interface which returns the StrategyConditionConfiguration collection.  |
| RequiredKeys | int array | Indicates which keys are required from the StrategyConditionConfiguration collection when building StrategyConditionConfiguration combinations when generating the strategies from the TargetSymbol.  |
| OutputFolder | string | The relative path location to write the Edge Test output. |
| OrderBuilderHandlers | List of IOrderBuilderHandler arrays | Multiple collections of IOrderBuilderHandler can be used. |
| ExchangeTradingHoursType | ExchangeTradingHoursType | Enumeration indicating the exchange trading hours used by the strategies ("Regular" or "Extended"). |
| DateRangeConfigurations | DateRangeConfiguration array | Defines the date ranges and corresponding strategy filters to use to test the strategies. NOTE: The first DateRangeConfiguration is used on the TrainingSymbols.  Subsequent DateRangeConfigurations will be used on the OutOfSampleSymbols |

## Random Trade Backtest Runner

The Random Trade Backtest Runner will run N number of bactests against a defined array of symbols, date range and exit criteria where the entries are random.  This is useful for comparing edge test strategy results against random entry.

### Command Line Usage

```dotnet run yourRandomTradeBacktestConfigFile.json runrandomtradebacktests```

### Random Trade Backtest Runner Configuration Properties

| Property Name | Type          | Description  |
| ------------- |-------------| ------------|
| Symbols | string array | The symbols in which to generate the random trades for. |
| TradeQuantity | int | The number of trades for each backtest run. |
| QuantityPercentDistribution | string aray | Defines how to distribute the trades amongst the symbols being backtested. |
| TestIteration | int | The number of backtests to perform. |
| TargetTimeFrame | TimeFrameConfiguration | The timeframe in which trades are executued on. |
| TradeType | TradeType | Enumeration indicating the trade type ("Long" or "Short") |
| LimitTrades | bool | Setting true will prevent a strategy from having two concurrent positions for the same symbol. |
| OutputFolder | string | The relative path location to write the Edge Test output. |
| OrderBuilderHandlers | IOrderBuilderHandler array | Defines the exit criteria for the backtests. |
| ExchangeTradingHoursType | ExchangeTradingHoursType | Enumeration indicating the exchange trading hours used by the strategies ("Regular" or "Extended"). |
| DateRange | DateRange | Defines the date range to test the strategies on. |


## Order Optimization Runner

The Order Optimization Runner tests different Order Combinations on the strategies generated from the Edge Test Runner.  Output from this runner is used by the Portfolio Optimization Runner.

### Command Line Usage

```dotnet run yourOrderOptimizationConfigFile.json runorderoptimization```

### Order Optimization Runner Configuration Properties

| Property Name | Type | Description  |
| ------------- |-------------| ------------|
| Symbols | string array | The symbols in which the strategies are tested on. |
| TargetTimeFrame | TimeFrameConfiguration | The timeframe in which trades are executued on. |
| HigherTimeFrames | TimeFrameConfiguration array | The higher timeframes used by the tested strategies. |
| LimitTrades | bool | Setting true will prevent a strategy from having two concurrent positions for the same symbol. |
| DefinitionFolder | string | The relative path to the location of the corresponding Edge Test output. |
| OutputFolder | string | The relative path location to write the Order Optimization output. |
| OrderBuilderHandlers | List of IOrderBuilderHandler arrays | Multiple collections of IOrderBuilderHandler which are used to create IOrderBuilderHandler combinations. |
| RequiredKeys | int array | Indicates which keys are required from the IOrderBuilderHandler collections.|
| ExchangeTradingHoursType | ExchangeTradingHoursType | Enumeration indicating the exchange trading hours used by the strategies ("Regular" or "Extended"). |
| DateRange | DateRange | Defines the date range to test the strategies on. |
| StrategyFilters | IResultFilter array | Used to filter the strategies. |

## Portfolio Optimization Runner

The Portfolio Optimization Runner tests different strategy portfolios from the output of the Order Optimization Runner.  The result is a collection of strategy portfolios with AlgoTerminal strategy, portoflio and risk management code generated.

### Command Line Usage

```dotnet run yourPortfolioOptimizationConfigFile.json runportfoliooptimization```

### Portfolio Optimization Runner Configuration Properties

| Property Name | Type          | Description  |
| ------------- |-------------| ------------|
| BeginningBalance | double | The beginning account balance for each portfolio backtest. |
| BenchmarkSymbol | string | The symbol to compare the portfolio backtest to. |
| CommissionCalculator | ICommissionCalculator | Set to the class that implements the ICommissionCalculator interface which is used for calculating trade commissions. |
| PortfolioName | string | The name of the portfolio script that will be displayed in AlgoTerminal. The name will be appended by a numeric value indicating the portfolio number. |
| RiskName | string | The name of the risk management script that will be displayed in AlgoTerminal. The name will be appended by a numeric value indicating the portfolio number. |
| DefinitinFolders | string array | The relative base paths containing the Order Optimization output. |
| GenerateCode | bool | Setting true will generate AlgoTerminal source code. |
| LimitTrades | bool | Setting true will prevent a strategy from having two concurrent positions for the same symbol. |
| MaxRiskPercentagePerTrade | double | The maximum amount of the account balance to risk per trade. |
| StrategySameTradePercentageThreshold | double | Used to combine similar strategies in a collection where the best one will eventually be selected to add into the portfolio. |
| OutputFolder | string | The relative path location to write the Portfolio Optimization output. |
| ResultOutputCount | int | The number of portfolios to output. |
| PortfolioStrategyMaxPositions | PortfolioMaxPositions array | Used to set maximum positions for one or more strategies. |
| PortfolioStrategyGroupMaxPositions | PortfolioMaxPositions array | Used to set maximum positions for one or more strategy groups. |
| TradeAllocationPercentage | double | The maximum account percentage that can be allocated to a single trade. |
| DateRange | DateRange | Defines the date range to test the portfolio on. |
| PortfolioStrategyFilters | List of PortfolioStrategyFilters arrays | Multiple collections of PortfolioStrategyFilters which are used to create PortfolioStrategyFilters combinations.  Each combination is built with different strategy result filters resulting in different strategy portfolios.  |
| PortfolioFilters | IResultFilter array | Used to filter the portfolios.  |
| PortfolioStrategyScorers | List of PortfolioStrategyScorers arrays | Multiple collections of PortfolioStrategyScorers which are used to create PortfolioStrategyScorers combinations.  Each combination is built with different strategy result scorers resulting in different strategy candidate selection.  |
| PortfolioScorers | IResultScorer array | Used to score the portfolios that passed the PortfolioFilters.  The portfolios will be ranked and written to disk in ascending order.  |

## Portfolio Backtest Runner

The Portfolio Backtest Runner backtests a strategy portfolio generated from the Portfolio Optimization Runner.  The config file for the runner is generated by the Portfolio Optimization Runner and is named 'PortfolioBacktestConfig.json' and can be found in the portfolio output directory.

The only properties that have to be updated in the config file are the DefinitionFolder and OutputFolder properties.

### Command Line Usage

```dotnet run yourPortfolioBacktestConfigFile.json runportfoliobacktest```

### Portfolio Backtest Runner Configuration Properties

| Property Name | Type          | Description  |
| ------------- |-------------| ------------|
| BeginningBalance | double | The beginning account balance for each portfolio backtest. |
| BenchmarkSymbol | string | The symbol to compare the portfolio backtest to. |
| CommissionCalculator | ICommissionCalculator | Set to the class that implements the ICommissionCalculator interface which is used for calculating trade commissions. |
| DefinitinFolder | string | The relative path location containing the portfolio output. |
| LimitTrades | bool | Setting true will prevent a strategy from having two concurrent positions for the same symbol. |
| OutputFolder | string | The relative path location to write the portfolio backtest output. |
| StrategyConfigurations | StrategyConfiguration array | The strategies for the portfolio backtest. |
| StrategyGroupsMaxPositions | StrategyGroupMaxPositions array | Defines the max positions for groups of strategies. |
| PortfolioStrategyGroupMaxPositions | PortfolioMaxPositions array | Used to set maximum positions for one or more strategy groups. |
| DateRange | DateRange | Defines the date range to test the portfolio on. |

## Portfolio Code Generator Runner

The Portfolio Code Generator Runner generates AlgoTerminal code for an existing strategy portfolio.

### Command Line Usage

```dotnet run yourPortfolioCodeGeneratorConfigFile.json runportfoliocodegeneration```

### Portfolio Code Generator Runner Configuration Properties

| Property Name | Type          | Description  |
| ------------- |-------------| ------------|
| PortfolioName | string | The name of the portfolio script that will be displayed in AlgoTerminal. |
| RiskName | string | The name of the risk management script that will be displayed in AlgoTerminal. |
| DefinitinFolder | string | The relative path location containing the portfolio output. |

