const TelegramBot = require('node-telegram-bot-api');
const token = '6758810828:AAFLSxU9hZ7itnB4Fvzwgb4X1b3bl_fdKu8'


const bot = new TelegramBot(token, {

    polling: true
})
const commands = [
    {
        command: `start`,
        description: `Запуск`
    },
    {
        command: `keyb`,
        description: `Клавиатура`
    },
    {
        command: `help`,
        description: `Помощь`
    }

]

bot.setMyCommands(commands)
bot.on('message', async (msg) => {
    switch (msg.text) {
        case `/start`:
            await bot.sendMessage(msg.chat.id, "Привет я бот Толик я ниче не умею")
            break;
        case `/help`:
            await bot.sendMessage(msg.chat.id, "я помогу")
            break;
        case "/keyb":
            await bot.sendMessage(msg.chat.id, "Клава", {
                reply_markup: {
                    keyboard: [
                        [`Первый`, `второй`],
                        [`Первый`, `второй`],
                        [`Close`]
                    ], resize_keyboard:true

                }
            })
            break;
    }
    const fmessage = await bot.sendMessage(msg.chat.id, "я слишком туп для этого дерьма")
    setTimeout(async () => {

        await bot.editMessageText(msg.text, {
            chat_id: fmessage.chat.id,
            message_id: fmessage.message_id
        })
    }, 3000)
    console.log(msg);
})
