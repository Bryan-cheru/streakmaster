# ⚡ StreakMaster - Fast Execution Trading Bot

A high-speed, browser-based automated trading bot for Deriv's Volatility 50 Index. Built for **instant execution** with **zero delays**.

## 🎯 Features

- **Real-time Streak Tracking** - Monitors last digit patterns from R_50 ticks
- **Fast Execution** - Minimal processing, instant trade execution (1-tick duration)
- **Simple Logic** - Only 3 metrics matter: Last Digit, Current Streak, Last Reset
- **Auto Trading** - Fully automated with emergency stop functionality
- **Clean UI** - Modern, responsive design with real-time updates
- **Zero Dependencies** - Pure HTML/CSS/JavaScript (no frameworks)

## 📊 How It Works

### Core Metrics

1. **Last Digit** - The last digit (0-9) of the current tick price
2. **Current Streak** - Increments when digit ≥ 4, resets to 0 when digit < 4
3. **Last Reset** - Stores the previous streak value before reset

### Trading Logic

**Trades ONLY when:**
- Last Reset = 0 **AND**
- Current Streak = 1 or 2

**Blocks trading when:**
- Current Streak > 2 (waits for reset)
- Last Reset ≠ 0 (waits for another reset cycle)

### Example Flow

```
Digit: 5 → Streak: 1, Last Reset: 0 ✅ TRADE!
Digit: 7 → Streak: 2, Last Reset: 0 ✅ TRADE!
Digit: 6 → Streak: 3, Last Reset: 0 🚫 BLOCKED (Streak > 2)
Digit: 8 → Streak: 4, Last Reset: 0 🚫 BLOCKED (Streak > 2)
Digit: 2 → Streak: 0, Last Reset: 4 🚫 BLOCKED (Last Reset ≠ 0)
Digit: 1 → Streak: 0, Last Reset: 0 ⏳ Waiting...
Digit: 6 → Streak: 1, Last Reset: 0 ✅ TRADE!
```

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended)

1. Visit the live deployment:
   ```
   https://bryan-cheru.github.io/streakmaster/
   ```

### Option 2: Local Development

1. Clone the repository:
   ```bash
   git clone https://github.com/Bryan-cheru/streakmaster.git
   cd streakmaster
   ```

2. Open `index.html` in your browser:
   ```bash
   # Windows
   start index.html
   
   # macOS
   open index.html
   
   # Linux
   xdg-open index.html
   ```

## 🔧 Configuration

### Getting Your API Token

1. Go to [Deriv.com](https://deriv.com)
2. Log in to your account
3. Navigate to **Settings** → **API Token**
4. Create a new token with **trading** permissions
5. Copy and paste the token into the bot

### Trading Settings

- **Stake Amount**: Minimum $0.35 (adjustable in the UI)
- **Contract Type**: DIGITUNDER
- **Barrier**: 4
- **Duration**: 1 tick (fastest execution)
- **Symbol**: R_50 (Volatility 50 Index)

## ⚙️ Controls

### Keyboard Shortcuts

- `Ctrl + Space` - Emergency Stop
- `Ctrl + T` - Toggle Auto Trading

### UI Controls

- **Connect/Disconnect** - Establish WebSocket connection
- **Start/Stop Auto Trading** - Enable/disable automated trading
- **Emergency Stop** - Immediately halt all trading activity
- **Stake Amount** - Set your trade stake (minimum $0.35)

## 📈 Performance Optimizations

This bot is optimized for **zero-delay execution**:

✅ **Streamlined code** - No complex calculations between ticks  
✅ **Minimal state management** - Only tracks essential metrics  
✅ **Immediate trade execution** - Trades execute as soon as conditions are met  
✅ **1-tick duration** - Fastest possible contract settlement  
✅ **Direct WebSocket** - No intermediate API layers  

## 🛡️ Risk Management

- Always test with a **demo account** first
- Start with minimum stake amounts ($0.35)
- Use the **Emergency Stop** if needed
- Monitor P&L and balance regularly
- Never risk more than you can afford to lose

## 📱 Browser Compatibility

- ✅ Chrome/Edge (Recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Mobile browsers (responsive design)

## 🐛 Troubleshooting

### Connection Issues

- Verify your API token is correct and has trading permissions
- Check your internet connection
- Ensure you're using a valid Deriv account
- Try refreshing the page

### Trading Not Executing

- Verify auto trading is enabled (green button)
- Check that conditions are met (Last Reset = 0, Streak = 1 or 2)
- Ensure sufficient balance for the stake amount
- Check the trading log for error messages

## 📄 License

MIT License - Feel free to use and modify

## ⚠️ Disclaimer

This bot is for educational and testing purposes only. Trading involves risk. Always use a demo account for testing. The authors are not responsible for any financial losses incurred through the use of this software.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Support

For issues or questions, please open an issue on GitHub.

---

**Made with ⚡ for fast, reliable trading execution**
