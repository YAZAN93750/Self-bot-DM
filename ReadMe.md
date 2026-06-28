/**
 * ---------------------------------------------------------
 * Project: Auto DM Reply Self-Bot
 * //Made By: 9.2u
 * ---------------------------------------------------------
 */

const { Client } = require('discord.js-selfbot-v13');
const client = new Client();

// //Made By: 9.2u - إعدادات البوت
const replyText = "هذا هو النص الثابت الذي سيتم إرساله";

// //Made By: 9.2u - تسجيل الدخول
client.on('ready', () => {
    console.log(`----------------------------------------`);
    console.log(`Bot Status: Online`);
    console.log(`Logged in as: ${client.user.tag}`);
    console.log(`//Made By: 9.2u`);
    console.log(`----------------------------------------`);
});

// //Made By: 9.2u - معالجة الرسائل
client.on('messageCreate', async (message) => {
    
    // التحقق من أن الرسالة في الخاص وليست مرسلة من حسابك
    if (message.channel.type === 'DM' && message.author.id !== client.user.id) {
        
        try {
            // إرسال النص الثابت
            await message.channel.send(replyText);
            
            console.log(`[Success] Replied to: ${message.author.tag}`);
            console.log(`//Made By: 9.2u`);
        } catch (error) {
            console.error(`[Error] Could not send message: ${error}`);
        }
    }
});

// //Made By: 9.2u - تشغيل البوت
client.login('YOUR_TOKEN_HERE');