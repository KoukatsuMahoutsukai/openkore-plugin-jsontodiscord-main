# openkore-plugin-jsontodiscord

Simple openkore plugin that makes use WebService::Discord::Webhook, to send a status update from openkore to your discord server.
Helpful for monitoring when you are running the bot from another pc/vps.

Below is a sample output when used as a standalone, it would be in json format and not nice to the eyes
`{"#Deaths":0,"CX":180,"CY":76,"Exp/hr":7969,"Hp":"93.81","Lockmap":"pay_fild08","Map":"pay_fild08","Name":"Lovel","Username":"username010","Weight":"23"}`

When used in tandem with a discord bot that receives the messages and deletes each incoming message so the server wont be flodded with messages.


![image](https://github.com/KoukatsuMahoutsukai/openkore-plugin-jsontodiscord/assets/123940777/964e5bc9-fdcf-46dc-9976-26a387f61dc9)


This adds complexity though and would need more setup so if you want the simple webhook message i suggest the code from sctnightcore which is where i copied most of the code.
https://github.com/sctnightcore/OpenKorePluginsByMe/blob/master/OpenkoreToDiscord


for those intereseted in the bot that organizes the messages i am working on it and a tutorial so i can share it with you in the following days. 
in the meantime you can use this plugin then maybe code your own discord bot too

## Requirements
-openSSL

-https://metacpan.org/pod/WebService::Discord::Webhook

-https://metacpan.org/pod/HTTP::Tiny

-https://metacpan.org/pod/JSON

-https://metacpan.org/pod/Net::SSLeay

-https://metacpan.org/pod/IO::Socket::SSL


Honestly i had difficulties installing the requirements on windows, i would provide a dockerfile/docker image later on that would make you not bother with the requirements.


## Usage
1.  Change the `my $url`, simply paste your webhook url from discord there
    
    https://support.discord.com/hc/en-us/articles/228383668-Intro-to-Webhooks

2.  paste the jsontodiscord folder inside the plugins folder of your openkore

3.  add the jsontodiscord plugin in the sys.txt inside control folder, the line is like below
    `loadPlugins_list raiseStat,raiseSkill,reconnect,item_weight_recorder,xconf,eventMacro,macro,jsontodiscord`

    It should work right away if the requirements are installed properly, but i suggest just using the docker that im about to upload if you are not familiar with installing the requirements,
    modifying the stats that you want to see can also be easy i would upload a tutorial for it later on.
