- 👋 Hi, I’m @peterskinny03
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!50931959942---
peterskinny03/peterskinny03 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
const { default: makeWASocket } = require("@adiwajshing/baileys")

async function startBot() {
  const sock = makeWASocket()

  sock.ev.on("messages.upsert", async ({ messages }) => {
    const msg = messages[0]
    const text = msg.message?.conversation

    if (text === "Bonjou") {
      await sock.sendMessage(msg.key.remoteJid, { text: "Bonjou! Kijan m ka ede w?" })
    }
  })
}

startBot
