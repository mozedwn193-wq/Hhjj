# TDT (Time Dilation Theory) Pine Script Implementation

## Overview
This implementation provides a comprehensive Pine Script solution for the Time Dilation Theory candle counting methodology. The system consists of three main scripts that work together to provide candle counting, session filtering, and backtesting capabilities.

## Scripts Included

### 1. TDT Enhanced (`tdt_enhanced.pine`)
**Main candle counting script with advanced features**

#### Key Features:
- **Core Counting Logic**: Implements the 1,3,7,13,21 sequence with proper pivot detection
- **Sequence Mapping**: Supports contraction/expansion modes (7→9, 13→11/17, 21→17/25)
- **Multi-Timeframe Analysis**: Overlay higher timeframe counts for confluence
- **Session Filtering**: Trade only during specified sessions
- **Visual Indicators**: Clear markers for count levels and HTF overlays
- **CSV Export**: Export data for external analysis
- **Real-time Alerts**: Notifications when count levels are hit

#### Input Parameters:
- **Counting Direction**: Bullish/Bearish
- **Pivot Settings**: Left/Right bars for pivot confirmation
- **Distortion Filters**: Skip inside bars and doji candles
- **Sequence Mapping**: Enable contraction/expansion modes
- **Session Control**: Define trading hours and timezone
- **Multi-Timeframe**: Higher TF overlay settings
- **Levels**: Customizable count levels to mark
- **Visual Settings**: Marker sizes and display options

### 2. TDT Session Filters (`tdt_session_filters.pine`)
**Advanced filtering and market condition detection**

#### Key Features:
- **Multi-Session Support**: Primary, secondary, and overnight sessions
- **Volatility Detection**: ATR-based high/low volatility identification
- **Trend Analysis**: Market structure and trend strength detection
- **Liquidity Zones**: Recent highs/lows for liquidity detection
- **Day-of-Week Filters**: Trade only on specific days
- **News Integration**: Placeholder for economic calendar integration
- **Combined Filters**: Master filter combining all conditions

#### Input Parameters:
- **Sessions**: Three customizable trading sessions
- **Volatility**: ATR length, multiplier, and thresholds
- **Structure**: Trend length and strength thresholds
- **Liquidity**: Lookback period and tolerance settings
- **Time Filters**: Day-of-week restrictions
- **News**: Buffer time around news events

### 3. TDT Backtesting (`tdt_backtesting.pine`)
**Strategy backtesting with performance metrics**

#### Key Features:
- **Automated Trading**: Entry/exit based on count levels
- **Risk Management**: Position sizing based on risk percentage
- **Stop Loss/Take Profit**: Configurable SL/TP levels
- **Performance Metrics**: Win rate, profit factor, drawdown analysis
- **Trade Limits**: Maximum concurrent trades
- **Session Filtering**: Trade only during specified sessions
- **CSV Export**: Detailed trade data for analysis

#### Input Parameters:
- **TDT Settings**: Same as main script
- **Entry/Exit Levels**: Separate levels for entries and exits
- **Risk Management**: Risk per trade and position sizing
- **Trade Limits**: Maximum concurrent positions
- **SL/TP**: Stop loss and take profit in pips

## Usage Instructions

### Basic Setup
1. **Load the main script** (`tdt_enhanced.pine`) on your chart
2. **Configure basic settings**:
   - Set counting direction (Bullish/Bearish)
   - Adjust pivot left/right bars (default: 3)
   - Enable session filtering if desired
   - Set your trading session hours

### Advanced Configuration
1. **Enable sequence mapping** for contraction/expansion modes
2. **Add higher timeframe overlay** for confluence
3. **Customize levels** to mark specific count numbers
4. **Set up alerts** for automated notifications

### Session Filtering
1. **Load the session filters script** (`tdt_session_filters.pine`)
2. **Configure your trading sessions**:
   - Primary session (e.g., 0800-1600)
   - Secondary session (e.g., 1600-2000)
   - Overnight session (e.g., 2000-0800)
3. **Set timezone** to match your broker
4. **Enable volatility filters** for better trade selection

### Backtesting
1. **Load the backtesting script** (`tdt_backtesting.pine`)
2. **Configure strategy parameters**:
   - Entry levels (e.g., 7,13)
   - Exit levels (e.g., 21)
   - Risk per trade (e.g., 2%)
   - Stop loss/take profit in pips
3. **Run backtest** to analyze performance
4. **Review metrics** in the performance table

## Key Concepts

### Counting Rules
- **Start from confirmed pivots**: Use pivot left/right bars for confirmation
- **Skip opposite candles**: Ignore bearish candles in bullish counts and vice versa
- **Skip distortion candles**: Inside bars and doji candles are ignored
- **Session filtering**: Only count during specified trading hours

### Sequence Mapping
- **Standard Mode**: 1,3,7,13,21
- **Contraction Mode**: 7→9, 13→11/17, 21→17/25
- **Expansion Mode**: Standard sequence with additional levels

### Multi-Timeframe Analysis
- **Higher TF overlay**: Shows count from higher timeframe
- **Confluence detection**: When multiple TFs align on same levels
- **Bias determination**: Use HTF for overall market direction

## Best Practices

### For Live Trading
1. **Start with paper trading** to understand the system
2. **Use session filters** to avoid low-probability setups
3. **Combine with other analysis** (ICT concepts, price action)
4. **Set proper risk management** (2% risk per trade)
5. **Use alerts** for timely execution

### For Backtesting
1. **Test on multiple timeframes** to find optimal settings
2. **Use realistic slippage** and commission costs
3. **Test different session filters** for your trading style
4. **Analyze drawdown periods** to understand weaknesses
5. **Optimize parameters** but avoid overfitting

### For Analysis
1. **Export CSV data** for external analysis
2. **Use multiple scripts together** for comprehensive view
3. **Monitor performance metrics** regularly
4. **Adjust parameters** based on market conditions
5. **Keep detailed logs** of your observations

## Troubleshooting

### Common Issues
1. **No counts appearing**: Check pivot settings and session filters
2. **Too many false signals**: Increase pivot confirmation bars
3. **Missing HTF data**: Ensure higher timeframe is available
4. **Alerts not firing**: Check alert settings and conditions

### Performance Optimization
1. **Reduce calculation complexity** by limiting lookback periods
2. **Use session filters** to reduce unnecessary calculations
3. **Optimize pivot settings** for your trading style
4. **Monitor script performance** on lower timeframes

## Customization

### Adding New Levels
Modify the `levelsToMark` input to include additional count levels:
```
levelsToMark = input.string("7,13,21,31", "Levels (comma-separated)")
```

### Custom Session Times
Adjust session inputs for your trading schedule:
```
sessionStart = input.session("0900-1700", "Trading Session")
```

### Additional Filters
Extend the filtering logic in the session filters script:
```pine
// Add your custom filter
customFilter = your_condition_here
masterFilter = inSession1 and isAllowedDay and customFilter
```

## Support and Updates

This implementation provides a solid foundation for TDT candle counting in Pine Script. The modular design allows for easy customization and extension based on your specific trading needs.

For questions or improvements, refer to the Pine Script documentation and TradingView community resources.