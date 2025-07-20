# Enhanced Order Blocks (EOB) - Multi-Timeframe Indicator

A comprehensive Pine Script indicator for TradingView that identifies Enhanced Order Blocks (EOBs) across multiple timeframes with extensive customization options. EOBs are fractal patterns that can be identified across all timeframes and provide high-probability reversal zones.

## 🚀 Features

### Core EOB Identification
- **Bearish EOB**: Bullish setup candle with decent bottom wick + bearish engulfing confirmation
- **Bullish EOB**: Bearish setup candle with decent top wick + bullish engulfing confirmation
- **Fractal Nature**: EOBs work on all timeframes from 3-minute to weekly charts

### Confirmation Options
- ✅ **Wick Close Confirmation**: Confirmation candle must close beyond the entire setup candle (including wick)
- ✅ **Body Close Confirmation**: Confirmation candle must close beyond the setup candle body only
- 🔄 **Toggle On/Off**: Enable/disable each confirmation method independently

### Multi-Timeframe (MTF) Support
#### Higher Timeframe Overlays
- 📊 **1 Week EOB** - Toggle On/Off
- 📊 **1 Day EOB** - Toggle On/Off  
- 📊 **4 Hour EOB** - Toggle On/Off
- 📊 **2 Hour EOB** - Toggle On/Off

#### Lower Timeframe Options
- ⏰ **1 Hour EOB** - Toggle On/Off
- ⏰ **30 Minutes EOB** - Toggle On/Off
- ⏰ **15 Minutes EOB** - Toggle On/Off
- ⏰ **5 Minutes EOB** - Toggle On/Off
- ⏰ **3 Minutes EOB** - Toggle On/Off

### HTF EOB Display Features
- 🔄 **Show HTF Saved/Marked EOBs in Lower Timeframe** - Toggle On/Off
- 👁️ **LTF EOB Visibility** (within 1H chart only)
- 📏 **Customizable Width Option** for LTF EOBs

### Advanced EOB Features
- ⚡ **Equilibrium (EQ) Lines** - Toggle On/Off with extension options
- 📈 **Extended EOBs** - Toggle On/Off for right extension
- 🎯 **Mitigation Levels**: Customizable threshold (0.5 = 50% fill, 1.0 = full fill)
- 🗑️ **Delete Mitigated EOBs** - Toggle On/Off

### Visual Customization
- 🎨 **Bullish EOB Color** - Fully customizable
- 🎨 **Bearish EOB Color** - Fully customizable  
- 🎨 **Partially Mitigated Color** - Customizable
- 🎨 **EQ Line Color** - Customizable
- 📏 **Border Width** - Adjustable for better visibility

## 📋 How to Use

### Installation
1. Copy the code from `enhanced_order_blocks_eob.pine`
2. Open TradingView Pine Script Editor
3. Paste the code and save as "Enhanced Order Blocks (EOB)"
4. Apply to your chart

### Basic Setup
1. **Enable Confirmation Method**: Choose between wick close or body close confirmation
2. **Select Timeframes**: Enable the timeframes you want to monitor
3. **Customize Colors**: Set your preferred colors for bullish/bearish EOBs
4. **Configure Mitigation**: Set your preferred mitigation threshold (0.5 recommended)

### Trading the EOBs

#### Bearish EOB Setup
1. **Setup Candle**: Look for a bullish candle with a significant bottom wick (rejection of lower prices)
2. **Confirmation**: Next candle must be bearish and engulf the setup candle based on your confirmation settings
3. **Trade Zone**: The EOB zone spans from the low to the high of the setup candle
4. **Entry**: Look for price to return to this zone for shorting opportunities

#### Bullish EOB Setup  
1. **Setup Candle**: Look for a bearish candle with a significant top wick (rejection of higher prices)
2. **Confirmation**: Next candle must be bullish and engulf the setup candle based on your confirmation settings
3. **Trade Zone**: The EOB zone spans from the high to the low of the setup candle
4. **Entry**: Look for price to return to this zone for buying opportunities

### Multi-Timeframe Analysis
- **Higher Timeframe EOBs**: Provide stronger, more reliable zones
- **Lower Timeframe EOBs**: Offer more frequent but potentially less reliable signals
- **Confluence**: Look for alignment between multiple timeframe EOBs for highest probability setups

## ⚙️ Settings Guide

### 🔍 Confirmation Options
- **Wick Close Confirmation**: More conservative, requires full engulfment including wicks
- **Body Close Confirmation**: More aggressive, only requires body engulfment

### 📊 MTF Overlays (HTF)
Enable higher timeframe EOBs to see major zones on your current chart:
- Weekly EOBs: Major swing zones
- Daily EOBs: Significant daily levels  
- 4H/2H EOBs: Intraday major zones

### ⏰ LTF Options
Enable lower timeframe EOBs for more granular analysis:
- Useful for precise entries
- Higher frequency signals
- Good for scalping strategies

### ⚙️ EOB Features
- **EQ Lines**: Show the middle of each EOB for potential partial profit targets
- **Extended EOBs**: Keep zones visible as price moves away
- **Mitigation Threshold**: 
  - 0.5 = EOB considered mitigated when 50% filled
  - 1.0 = EOB only mitigated when completely filled
- **Delete Mitigated**: Automatically remove filled EOBs to keep chart clean

### 🎨 Color Settings
Customize colors to match your trading style:
- **Bullish EOB**: Default green with transparency
- **Bearish EOB**: Default red with transparency
- **Partially Mitigated**: Default orange to show touched zones
- **EQ Lines**: Default yellow dashed lines

## 🔔 Alerts

The indicator includes built-in alert conditions:
- **Bearish EOB Formed**: Triggers when a new bearish EOB is confirmed
- **Bullish EOB Formed**: Triggers when a new bullish EOB is confirmed

To set up alerts:
1. Right-click on the chart
2. Select "Add Alert"
3. Choose the EOB indicator
4. Select the desired alert condition
5. Configure your notification preferences

## 📊 Information Table

A small table in the top-right corner shows:
- Current count of bullish EOBs
- Current count of bearish EOBs  
- Current count of HTF EOBs
- Real-time statistics for active zones

## 🎯 Trading Tips

1. **Confluence**: Look for EOBs that align with other technical levels (support/resistance, Fibonacci, etc.)
2. **Volume**: Higher volume on the setup candle increases reliability
3. **Market Structure**: EOBs work best in trending markets as retracement zones
4. **Risk Management**: Always use proper stop losses above/below the EOB zone
5. **Multiple Timeframes**: Combine HTF EOBs for direction with LTF EOBs for entry timing

## ⚠️ Risk Disclaimer

This indicator is for educational and analytical purposes only. Always use proper risk management and never risk more than you can afford to lose. EOBs are not guaranteed to hold as support or resistance.

## 🔧 Technical Requirements

- TradingView Pine Script v5
- Works on all TradingView plans
- Optimized for real-time trading
- Maximum 500 boxes and lines supported

## 📞 Support

For questions, suggestions, or bug reports, please refer to the Pine Script documentation or TradingView community forums.

---

**Happy Trading! 📈**