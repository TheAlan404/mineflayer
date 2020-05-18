# Mineflayer

[![NPM version](https://badge.fury.io/js/mineflayer.svg)](http://badge.fury.io/js/mineflayer)
[![Build Status](https://circleci.com/gh/PrismarineJS/mineflayer.svg?style=shield)](https://circleci.com/gh/PrismarineJS/mineflayer)
[![Discord](https://img.shields.io/badge/chat-on%20discord-brightgreen.svg)](https://discord.gg/GsEFRM8)
[![Gitter](https://img.shields.io/badge/chat-on%20gitter-brightgreen.svg)](https://gitter.im/PrismarineJS/general)
[![Irc](https://img.shields.io/badge/chat-on%20irc-brightgreen.svg)](https://irc.gitter.im/)

[![Try it on gitpod](https://img.shields.io/badge/try-on%20gitpod-brightgreen.svg)](https://gitpod.io/#https://github.com/PrismarineJS/mineflayer)

| US [English](README.md) | RU [Russian](README_RU.md) |
|---------------------------|---------------------------|

Güçlü, sabit ve yüksek seviye JavaScript API'ı ile Minecraft Botları oluşturun.

## Özellikler

 * 1.8, 1.9, 1.10, 1.11, 1.12, 1.13, 1.14 ve 1.15'i destekler.
 * Entity bilgisi ve takip etme.
 * Blok bilgisi, etrafındaki dünyayı gör.
 * Basit fizik ve hareket - şu anlık bloklar "katı" veya "boş".
 * Entitylere saldırmak ve araçlara binebilmek
 * Envanter düzenleme
 * Eşya üretme, sandıklar, fırlatıcılar, büyü masaları.
 * Kazma ve inşa etme.
 * Can surumunu ve yağmurun yağdığını bilme gibi diğer özellikler.
 * Blokları aktifleştirme ve eşyaları kullanma.
 * Sohbet.

### Yol Haritası

 * İksir masaları ve Örsler.
 * Daha iyi fizik (kapılar, merdivenler, su vb.).
 * PrismarineJS için büyük bir projeye katkıda bulunmak ister misin? Buraya git: https://github.com/PrismarineJS/mineflayer/wiki/Big-Prismarine-projects

## Kullanım

Version yazılmazsa sunucunun versiyonu otomatik olarak tahmin edilir. Bunun yerine bir versiyon belirtebilirsin.
Örnek olarak `version:"1.8"`.

### Echo Örneği
```js
var mineflayer = require('mineflayer');
var bot = mineflayer.createBot({
  host: "localhost", // isteğe bağlı
  port: 25565,       // isteğe bağlı
  username: "email@example.com", // email ve şifre sadece
  password: "12345678",          // online-mode=true sunucular için gereklidir
  version: false                 // false = otomatik tahmin etme, belirleyebilirsiniz
});
bot.on('chat', function(username, message) {
  if (username === bot.username) return;
  bot.chat(message);
});
bot.on('error', err => console.log(err))
```

### Debug

You can enable some protocol debugging output using `DEBUG` environment variable:

```bash
DEBUG="minecraft-protocol" node [...]
```

On windows :
```
set DEBUG=minecraft-protocol
node your_script.js
```

#### Daha fazla Örnek

 * [Örnekler](https://github.com/PrismarineJS/mineflayer/tree/master/examples) klasöründe.
 * [vogonistic's REPL bot](https://gist.github.com/vogonistic/4631678)

## Üçüncü Parti Pluginler

Mineflayer'a plugin eklenebilir; isteyen herkez Mineflayer'in üstüne daha yüksek seviyde
API yazabilir.

 * [navigate](https://github.com/andrewrk/mineflayer-navigate/) - A* yol bulma ile dünyada dolaş [YouTube Demo](https://www.youtube.com/watch?v=O6lQdmRz8eE)
 * [radar](https://github.com/andrewrk/mineflayer-radar/) - socket.io ve canvas kullanan web arayüz [YouTube Demo](https://www.youtube.com/watch?v=FjDmAfcVulQ)
 * [blockfinder](https://github.com/Darthfett/mineflayer-blockFinder) - find blocks in the 3D world
 * [scaffold](https://github.com/andrewrk/mineflayer-scaffold) - dünyada dolaş, blokları kırman ve koyman gerekse bile.
   [YouTube Demo](http://youtu.be/jkg6psMUSE0)
 * [auto-auth](https://github.com/G07cha/MineflayerAutoAuth) - sohbette kullanılan giriş sistemi
 * [Armor Manager](https://github.com/G07cha/MineflayerArmorManager) - otomatik zırh değiştirme
 * [Bloodhound](https://github.com/Nixes/mineflayer-bloodhound) - bir entitye kimin hasar verdiğini bul
 * [tps](https://github.com/SiebeDW/mineflayer-tps) - tps'i bulma (processed tps)

## Projects Using Mineflayer

 * [rom1504/rbot](https://github.com/rom1504/rbot)
   - [YouTube - building a spiral staircase](https://www.youtube.com/watch?v=UM1ZV5200S0)
   - [YouTube - replicating a building](https://www.youtube.com/watch?v=0cQxg9uDnzA)
 * [Darthfett/Helperbot](https://github.com/Darthfett/Helperbot)
 * [vogonistic/voxel](https://github.com/vogonistic/mineflayer-voxel) - visualize what
   the bot is up to using voxel.js
 * [JonnyD/Skynet](https://github.com/JonnyD/Skynet) -  log player activity onto an online API
 * [MinecraftChat](https://github.com/rom1504/MinecraftChat) (last open source version, built by AlexKvazos) -  Minecraft web based chat client <https://minecraftchat.net/>
 * [Cheese Bot](https://github.com/Minecheesecraft/Cheese-Bot) - Plugin based bot with a clean GUI. Made with Node-Webkit. http://bot.ezcha.net/
 * [Chaoscraft](https://github.com/schematical/chaoscraft) - Minecraft bot using genetic algorithms, see [its youtube videos](https://www.youtube.com/playlist?list=PLLkpLgU9B5xJ7Qy4kOyBJl5J6zsDIMceH)

## Installation

`npm install mineflayer`

## Documentation

 * See [docs/api.md](api.md).
 * See [docs/history.md](history.md).
 * See [examples/](https://github.com/PrismarineJS/mineflayer/tree/master/examples).
 * See [docs/unstable_api.md](unstable_api.md).
 * See [docs/contribute.md](contribute.md).

## Contribute

Please read https://github.com/PrismarineJS/prismarine-contribute

## Testing

Some setup is required after first cloning the project but after that is done it's very easy to run them.

### Setup

In order to get all tests to run successfully you must first:

1. create a new folder in which to store minecraft server jars
2. set the MC_SERVER_JAR_DIR to this folder

Example:

1. `mkdir server_jars`
2. `export MC_SERVER_JAR_DIR=/full/path/to/server_jars`

Where the "/full/path/to/" is the fully qualified path name.

### Testing everything

Simply run: `npm test`

### Testing specific version
Run `npm test -g <version>`, where `<version>` is a minecraft version like `1.12`, `1.15.2`...

### Testing specific test
Run `npm test -g <test_name>`, where `<test_name>` is a name of the test like `bed`, `useChests`, `rayTrace`...

## Updating to a newer protocol version

1. Wait for a new version of
   [node-minecraft-protocol](https://github.com/PrismarineJS/node-minecraft-protocol)
   to be released which supports the new Minecraft version.
2. `npm install --save minecraft-protocol@latest`
3. Apply the [protocol changes](http://wiki.vg/Protocol_History) where necessary.
4. Run the test suite. See Testing above.

## Licence

[MIT](LICENCE)
