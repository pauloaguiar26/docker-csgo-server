## Counter Strike Global Offensive + Docker

[![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/Gonzih/docker-csgo-server/blob/master/LICENSE.md)

CS:GO server in docker with 128 tick enabled by default.


### Details:
By default image is build with enabled autoupdate feature (take a look at `csgo.sh` file).
You can create new Dockerfile based on that image (FROM csgo) and customize it with plugins, configs, CMD and ENTRYPOINT instructions.

```shell
# Build image and tag it as csgo
docker build -t csgo github.com/pauloaguiar26/docker-csgo-server

# Run image with as Classic Casual server for 20 Players
docker run -d -p 27015:27015 -p 27015:27015/udp csgo -console -usercon +game_type 0 +game_mode 0 +mapgroup mg_active +map de_mirage -net_port_try 1 -maxplayers_override 20
```

### Running public server

To run public server you need to [Register Login Token](http://steamcommunity.com/dev/managegameservers) and adding `+sv_setsteamaccount THISGSLTHERE -net_port_try 1` to the server command.
Refer to [Docs](https://developer.valvesoftware.com/wiki/Counter-Strike:_Global_Offensive_Dedicated_Servers#Registering_Game_Server_Login_Token) for more details.
