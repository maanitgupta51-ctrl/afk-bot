const mineflayer = require('mineflayer')

const botPassword = "botpass123"   // create bot password here

function startBot() {

  const bot = mineflayer.createBot({
    host: 'TttloggyNetwork.aternos.me',
    port: 56298,
    username: 'ServerBot16',
    auth: 'offline'
  })

  bot.on('spawn', () => {
    console.log("Bot joined server")

    setTimeout(() => {
      bot.chat(/register ${botPassword} ${botPassword})
      bot.chat(/login ${botPassword})
    }, 4000)

    // anti AFK
    setInterval(() => {
      bot.setControlState('jump', true)
      setTimeout(() => bot.setControlState('jump', false), 500)
    }, 30000)
  })

  bot.on('end', () => {
    console.log("Disconnected. Reconnecting...")
    setTimeout(startBot, 15000)
  })

}

startBot()
