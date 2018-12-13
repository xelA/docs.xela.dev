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

{% include settings-title.html text="prefix"%}
If you have some other bots that have the `/` as a prefix or you want a different prefix regardless, you have the option to change it.
You can add as many as you want inside the `custom` tag with an **Array** list. Remember that if you want word prefix like `this is so sad, alexa ` please add a space in the end so you can actually type it without doing (example) `this is so sad, alexaplay despacito`. If you want to just add a meme prefix like the example displayed here and keep the slash prefix, make the `keep_default` to be on **true**, however if you want a prefix like `!` and want to disable the default one, place it on **false**
```json
"prefix": {
  "custom": ["multiple", "prefixes", "if needed"],
  "keep_default": true|false
}
```

{% include settings-title.html text="ban"%}
This will simply display who got banned for whatever reason.
```json
"ban": CHANNEL_ID
```

{% include settings-title.html text="unban"%}
This will simply display who got unbanned for whatever reason.
```json
"unban": CHANNEL_ID
```

{% include settings-title.html text="kick"%}
This will simply display who got kicked for whatever reason.
```json
"kick": CHANNEL_ID
```

{% include settings-title.html text="join"%}
Displays whoever joined the server and when the account was created to avoid possible raid or spam accounts.
```json
"join": CHANNEL_ID
```

{% include settings-title.html text="leave"%}
Displays whoever left the server and what roles the user left with, to prove that a user had roles if he/she joins back and wants it back.
```json
"leave": CHANNEL_ID
```

{% include settings-title.html text="edit"%}
Show whoever edited a message in the server.
```json
"edit": CHANNEL_ID
```

{% include settings-title.html text="delete"%}
Show whoever deleted a message in the server.
```json
"delete": CHANNEL_ID
```

{% include settings-title.html text="bulkdelete"%}
Dumps a large text file whenever you `/prune` any channel on the server.
```json
"bulkdelete": CHANNEL_ID
```

{% include settings-title.html text="report"%}
Have the ability for users to report anything in the server and let the moderators know anything.
```json
"report": CHANNEL_ID
```

{% include settings-title.html text="nsfw" noimage=true%}
Let users choose if they want to see NSFW channels or not with a role you've set up.
```json
"nsfw": ROLE_ID
```

{% include settings-title.html text="saveroles"%}
Keep a track on what roles a user had before they leave to then recover when they join back again.
```json
"saveroles": true|false
```

{% include settings-title.html text="auto_dehoist"%}
Automatically dehoists people who are trying to be on top of the member list.
```json
"auto_dehoist": true|false
```

{% include settings-title.html text="auto_decancer"%}
Automatically decancer people who have a horrible or unreadable names, keep in mind that it's triggered with emojis too.
```json
"auto_decancer": true|false
```

{% include settings-title.html text="ignore_channels" noimage=true%}
Makes xelA ignore all commands in one channel.
However, people with ban permissions bypass this rule and can continue to use commands in ignored channel.
```json
"ignore_channels": [CHANNEL_ID, CHANNEL_ID, ...]
```

{% include settings-title.html text="toggleroles"%}
Gives people the ability to give themselves a role, a perfect solution for users who've read the rules and accept by giving themselves a role to view all channels. The roleme command is toggable, so you can use this as well for people who want to subscribe to announcements/events and then letting them unsubscribe later in time.
```json
"toggleroles": [ROLE_ID, ROLE_ID, ...]
```

{% include settings-title.html text="music" noimage=true%}
xelA is able to play music, as well as let you control the default settings it will use. The `volume` is with only numbers but any number is the %, so say if you put 75, then the bot will always start with 75% volume. Max volume you can go for is 150%, trying above will prompt that it changed to it, but won't go above it. The `foceskip_roles` is for you to let people inside specific role(s) to forcefully skip any song in the queue. This can be a DJ or whatever you desire.
```json
"music": {
  "volume": 100,
  "forceskip_roles": [ROLE_ID, ROLE_ID, ...]
}
```
