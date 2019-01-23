---
permalink: "/docs"
layout: docs

title: xelA Settings Docs
description: Documenation over all settings the bot has to offer
keywords: xelA, bot, discord, 24/7, hot
favicon: assets/images/profile.png
---
# Getting started
To get started with the settings, please do the command `/settings template` to then get a file which you will be editing with whatever you desire.
If there are some settings you do not wish to have, you can simply just remove the JSON Object/Key in order to disable it completly.

# Example variables
{% include settings-details.html %}

{% include settings-title.html text="prefix" %}
If you have some other bots that have the `/` as a prefix or you want a different prefix regardless, you have the option to change it.
You can add as many as you want inside the `custom` tag with an **Array** list. Remember that if you want word prefix like `this is so sad, alexa ` please add a space in the end so you can actually type it without doing (example) `this is so sad, alexaplay despacito`. If you want to just add a meme prefix like the example displayed here and keep the slash prefix, make the `keep_default` to be on **true**, however if you want a prefix like `!` and want to disable the default one, place it on **false**
```json
"prefix": {
  "custom": ["multiple", "prefixes", "if needed"],
  "keep_default": true|false
}
```

{% include settings-title.html text="ban" %}
This will simply display who got banned for whatever reason.
```json
"ban": CHANNEL_ID
```

{% include settings-title.html text="unban" %}
This will simply display who got unbanned for whatever reason.
```json
"unban": CHANNEL_ID
```

{% include settings-title.html text="kick" %}
This will simply display who got kicked for whatever reason.
```json
"kick": CHANNEL_ID
```

{% include settings-title.html text="join" %}
Displays whoever joined the server and when the account was created to avoid possible raid or spam accounts.
```json
"join": CHANNEL_ID
```

{% include settings-title.html text="leave" %}
Displays whoever left the server and what roles the user left with, to prove that a user had roles if he/she joins back and wants it back.
```json
"leave": CHANNEL_ID
```

{% include settings-title.html text="edit" %}
Show whoever edited a message in the server.
```json
"edit": CHANNEL_ID
```

{% include settings-title.html text="delete" %}
Show whoever deleted a message in the server.
```json
"delete": CHANNEL_ID
```

{% include settings-title.html text="bulkdelete" %}
Dumps a large text file whenever you `/prune` any channel on the server.
```json
"bulkdelete": CHANNEL_ID
```

{% include settings-title.html text="report" %}
Have the ability for users to report anything in the server and let the moderators know anything.
```json
"report": CHANNEL_ID
```

{% include settings-title.html text="nsfw" %}
Let users choose if they want to see NSFW channels or not with a role you've set up.
```json
"nsfw": ROLE_ID
```

{% include settings-title.html text="saveroles" %}
Keep a track on what roles a user had before they leave to then recover when they join back again.
```json
"saveroles": true|false
```

{% include settings-title.html text="auto_dehoist" %}
Automatically dehoists people who are trying to be on top of the member list.
```json
"auto_dehoist": true|false
```

{% include settings-title.html text="auto_decancer" %}
Automatically decancer people who have a horrible or unreadable names, keep in mind that it's triggered with emojis too.
```json
"auto_decancer": true|false
```

{% include settings-title.html text="ignore_channels" %}
Makes xelA ignore all commands in one channel.
However, people with ban permissions bypass this rule and can continue to use commands in ignored channel.
```json
"ignore_channels": [CHANNEL_ID, CHANNEL_ID, ...]
```

{% include settings-title.html text="toggleroles" %}
Gives people the ability to give themselves a role, a perfect solution for users who've read the rules and accept by giving themselves a role to view all channels. The roleme command is toggable, so you can use this as well for people who want to subscribe to announcements/events and then letting them unsubscribe later in time.
```json
"toggleroles": [ROLE_ID, ROLE_ID, ...]
```

{% include settings-title.html text="music" %}
xelA is able to play music, as well as let you control the default settings it will use. The `volume` is with only numbers but any number is the %, so say if you put 75, then the bot will always start with 75% volume. Max volume you can go for is 150%, trying above will prompt that it changed to it, but won't go above it. The `foceskip_roles` is for you to let people inside specific role(s) to forcefully skip any song in the queue. This can be a DJ or whatever you desire.
```json
"music": {
  "volume": 100,
  "forceskip_roles": [ROLE_ID, ROLE_ID, ...]
}
```

{% include settings-title.html text="mute" %}
The mute object is the most important setting you will need to get every other settings that use a muted role to work. You can as well define something called a "Jail Channel" which is basically a channel on Discord that only muted people can see and possible talk to appeal in. Autoban makes it so if muted people leaves the server, they will automatically be banned by the bot for attempting to avoid punishment or just not bothering to appeal at all, up to you for the reasoning tbf.
```json
"mute": {
  "channel": CHANNEL_ID,
  "roleid": ROLE_ID,
  "autoban": true|false,
  "jailchannel": CHANNEL_ID,
  "jailmessage": "MESSAGE"
}
```

{% include settings-title.html text="voice_text" %}
This setting can be useful to make xelA give everyone who joins voice channels a new role for a temporarily time, to access a new channel where people who don't have a microphone can chat in to not make any other channels get confused over why the spesific person types a lot for himself/herself.
```json
"voice_text": {
  "channels": [CHANNEL_ID, CHANNEL_ID, ...],
  "roleid": ROLE_ID
}
```

{% include settings-title.html text="strict_mode" %}
Strict mode can be useful if you want to prevent people from making alts during a raid or just not accept early-made accounts overall to your Discord server by muting them as they join the server. Currently this setting don't have a lot of options due to low usage, but this might change.
```json
"strict_mode": {
  "days": DAYS_IN_NUMBER (Mute anyone with an account made earlier than DAYS_IN_NUMBER)
}
```

{% include settings-title.html text="antiads" %}
This will prevent people from posting **discord.gg** links in your discord server. You can make it ignore channels like self promotions if that's something you got or roles like your staff members. Announce is to showcase in a secret channel what the person who advertised 100% said in case if it was done by mistake or not. `usernamejoin` means if a user joins with discord.gg in their name, the bot will automatically ban them for trying to advertise with their names. If you have welcome/farewell message, it will replace the link with something else to prevent ads.
```json
"antiads": {
  "announce": CHANNEL_ID,
  "roles": ROLES_AMOUNT_TO_IGNORE,
  "ignore_roles": [ROLE_ID, ROLE_ID, ...],
  "ignore_channels": [CHANNEL_ID, CHANNEL_ID, ...],
  "usernamejoin": true|false,
  "warning": WARNINGS_BEFORE_BAN
}
```

{% include settings-title.html text="antispam" %}
Whenever people spam your server, xelA will delete the attempted spam and mute the person who does it multiple times. You can manage it by setting who the bot will ignore with specific roles or a channel that is meant for spamming (for odd reasons I guess).
```json
"antispam": {
  "ignore_roles": [ROLE_ID, ROLE_ID, ...],
  "ignore_channels": [CHANNEL_ID, CHANNEL_ID, ...],
  "warning": WARNINGS_BEFORE_MUTE
}
```

{% include settings-title.html text="anticaps" %}
Anitcaps is a way for you to avoid people spamming **THINGS WITH EVERYTHING IN LOVELY CAPSLOCK**. You can set an announce channel where it posts what a user said and then the length of when it should start looking at messages, in case people type things like: LOL, WTF, LMAO, GTFO, etc. Percent is to define how much of the message needs to be in CAPS before it deletes, it's defined by the % amount (Example: 50%) divided by 100, that would make it 0.5 to define in the percent option.
```json
"anticaps": {
  "announce": CHANNEL_ID,
  "roles": ROLES_AMOUNT_TO_IGNORE,
  "percent": 0.1 to 1.0,
  "length": CHARACTER_LENGTH_BEFORE_DETECT,
  "warning": WARNINGS_BEFORE_BAN
}
```

{% include settings-title.html text="antinewline" %}
Antinewline is to prevent people from spamming everything in a new line, this could be in copypasta, long texts that takes the entire discord and so on, an example would be:
![](https://i.alexflipnote.xyz/157af2.png)

You can define how many lines is too much and how many roles a person can have to bypass this.
```json
"antinewline": {
  "announce": CHANNEL_ID,
  "roles": ROLES_AMOUNT_TO_IGNORE,
  "lines": AMOUNT_OF_LINES_BEFORE_DELETE,
  "warning": WARNINGS_BEFORE_MUTE
}
```

{% include settings-title.html text="images_only" %}
If you've ever wanted to have a channel where people can **only** post images and not chat in, then this will suit you quite well. You can define multiple channels it will check for images only and delete anyone trying to not follow such roles.
```json
"images_only": {
  "channels": [CHANNEL_ID, CHANNEL_ID, ...],
  "warning": WARNINGS_BEFORE_MUTE
}
```

{% include settings-title.html text="antimention" %}
Disabling the `@everyone` is one thing, but preventing people from mentioning multiple users/roles is another thing that you can't disable with Discord settings. This will allow you to prevent such and make xelA delete those who try to do. You can also define how many mentions in one message is basically too much. (Please do not make it less than 2, that would be too bad.)
```json
"antimention": {
  "announce": CHANNEL_ID,
  "roles": ROLES_AMOUNT_TO_IGNORE,
  "mentions": MENTION_LIMIT,
  "warning": WARNINGS_BEFORE_MUTE
}
```

{% include settings-title.html text="wordfilter" %}
This setting makes it so you can ban some words or links that you do not allow at all in your server. This could be things like the N word and pornhub links if that's what you're into censoring (Not going to blame you for that).
```json
"wordfilter": {
  "words": ["MULTIPLE", "WORDS", "HERE"],
  "warning": WARNINGS_BEFORE_MUTE,
  "announce": CHANNEL_ID
}
```

{% include settings-title.html text="family_friendly" %}
This will ensure that the chat stays friendly without swearing and everything. If you want to test the filter, try with the `/predict` command.
```json
"family_friendly": {
  "ignore_roles": [ROLE_ID, ROLE_ID, ...],
  "ignore_channels": [CHANNEL_ID, CHANNEL_ID, ...],
  "warning": WARNINGS_BEFORE_MUTE
}
```

{% include settings-title.html text="welcome" %}
Give someone a warm welcome when they join your server and give them a nice role if you really feel like you want to colour them to something else than the default, white colour. You can define which role a user and a bot gets if you plan to have that.

{% include welcomefarewell.md %}

```json
"welcome": {
  "channel": CHANNEL_ID,
  "roleid": ROLE_ID,
  "roleidbot": ROLE_ID,
  "message": "Welcome [USER (or) MENTION] to **[SERVER]**! :3"
}
```

{% include settings-title.html text="farewell" %}
This will tell in the channel you want when someone leaves the server. Kinda sad but not everyone stays forever you know.

{% include welcomefarewell.md %}
```json
"farewell": {
  "channel": CHANNEL_ID,
  "message": "Goodbye [USER (or) MENTION] :("
}
```

{% include settings-title.html text="banmessage" %}
Do you want to announce when people get banned in the public with a funny message? Now you can with this setting, define which channel it will post it on and what message it shall send.

{% include welcomefarewell.md %}
```json
"banmessage": {
  "channel": CHANNEL_ID,
  "message": "[USER (or) MENTION] was banned today from [SERVER] ;-;"
}
```
