# Sphax的模组材质包
- [Baubles](https://bdcraft.net/community/viewtopic.php?t=3373&hilit=baubles)
- [Buildcraft](https://bdcraft.net/community/viewtopic.php?t=296&hilit=buildcraft)
- [Applied Energistics](https://bdcraft.net/community/viewtopic.php?t=308&hilit=appliedenergistics)
- [CoFHCore](https://bdcraft.net/community/viewtopic.php?t=3018&hilit=CoFHCore)
- [Pam's HarvestCraft](https://bdcraft.net/community/viewtopic.php?t=488&hilit=HarvestCraft)
- [Iron Chests](https://bdcraft.net/community/viewtopic.php?t=357&hilit=ironchest)
- [Just Enough Items](https://bdcraft.net/community/viewtopic.php?t=5122&hilit=justenoughitems)
- [Thermal Dynamics](https://bdcraft.net/community/viewtopic.php?p=24590&hilit=thermaldynamics#p24590)
- [Thermal Expansion](https://bdcraft.net/community/viewtopic.php?t=161&hilit=ThermalExpansion)
- [Thermal Foundation](https://bdcraft.net/community/viewtopic.php?t=3017&hilit=ThermalFoundation)
- [Immersive Engineering](https://bdcraft.net/community/viewtopic.php?t=4750)
- [Mekanism](https://bdcraft.net/community/viewtopic.php?t=446)
- [Botania](https://bdcraft.net/community/viewtopic.php?t=2626)
- [Cooking For Blockheads](https://bdcraft.net/community/viewtopic.php?t=5742)
- [Extra Utilities](https://bdcraft.net/community/viewtopic.php?t=1051)
- [Forestry](https://bdcraft.net/community/viewtopic.php?t=147)
- [Mr Crayfish's Furniture](https://bdcraft.net/community/viewtopic.php?t=5765)
- [Galacticraft](https://bdcraft.net/community/viewtopic.php?t=1131)
- [IndustrialCraft²](https://bdcraft.net/community/viewtopic.php?t=155)
- [Iron Backpacks](https://bdcraft.net/community/viewtopic.php?t=6367)
- [Tinkers' Construct](https://bdcraft.net/community/viewtopic.php?t=772)
- [Plus TiC](https://bdcraft.net/community/viewtopic.php?t=6350)
- [Thaumcraft](https://bdcraft.net/community/viewtopic.php?t=1114)
- [Actually Additions](https://bdcraft.net/community/viewtopic.php?t=6136)
- [Biomes O' Plenty](https://bdcraft.net/community/viewtopic.php?t=1098)
- [Quark](https://bdcraft.net/community/viewtopic.php?t=5946)
  
实际测试下来发现Pam's HarvestCraft会和其余材质包冲突


# 添加的mod
- Compact Machines 更多空间/压缩空间
- Wireless Crafting Terminal 无线合成终端
- p455w0rd's Library 无线合成终端的前置
- AE2 Wireless Terminal Library 无线合成终端的前置
- Akashic Tome 阿卡什宝典
- Thaumic Energistics Extended Life 神秘能源延续版
- Lazy AE2 懒人AE2
- LibNine 懒人AE2的前置


# 第三次更新
## 删除mods
- Compact Machines 更多空间/压缩空间 -- 没用
- theoneprobe  Mekanism通用机械的可选前置mod -- 和wawla重合

# 服务器启动指令
`java -Xmx7G -jar [.jar] nogui`

# 服务器安装[podman](https://podman.io/docs/installation#linux-distributions)
```
# Ubuntu 20.10 and newer
sudo apt-get update
sudo apt-get -y install podman
```
# 服务器安装[Podman Compose](https://github.com/containers/podman-compose)
```
apt-get -y install python3-pip
pip3 install podman-compose
```

## 修改源
Podman 配置文件（路径：/etc/containers/registries.conf）
```
# unqualified-search-registries = ["registry.fedoraproject.org", "registry.access.redhat.com", "registry.redhat.io", "docker.io"]
unqualified-search-registries = ["docker.io"]

[[registry]]
prefix = "docker.io"
location = "docker.m.daocloud.io"
[[registry.mirror]]
location = "docker.jianmuhub.com"
[[registry.mirror]]
location = "dockerhub.timeweb.cloud"
[[registry.mirror]]
location = "dockerhub1.beget.com"
[[registry.mirror]]
location = "huecker.io"
[[registry.mirror]]
location = "noohub.ru"
```

## bug
```
curl -O http://archive.ubuntu.com/ubuntu/pool/universe/g/golang-github-containernetworking-plugins/containernetworking-plugins_1.1.1+ds1-3build1_amd64.deb

dpkg -i container networking-plugins_1.1.1+ds1-3build1_amd64.deb
```

ic2 沉浸工程 rc bc 

## 20240702更新：mods_server/memorycleaner-1.4
https://www.curseforge.com/minecraft/mc-mods/memory-cleaner-mod

作者提示:

IMPORTANT:

THIS MOD IS NOT FOR EVERYONE!

Only use this if you are experiencing lag caused by high RAM usage (Which usually happens on very large modpacks) or experiencing crashes caused by OutOfMemoryError.

Otherwise this mod will negatively affect your game experience, because explicit gc takes time and it brings no benefit if your RAM is abundant.

For best experience I recommend using the suggested JVM arguments, see below.

>    CLIENT ONLY MOD
>
>This mod automatically calls System.gc() to free up your memory. Due to the fact that explicit gc can freeze your game for a short period, the mod watches the player movement and starts to clean up your RAM after the player stays idle for a while.
>
>The memory cleaning process also starts when your RAM usage goes above a certain percent (configurable) or after a long period if none of the above conditions are met (also configurable).
>
>Also you can use the /cleanmemory command to free up your RAM immediately.
>
>More options can be seen in the in-game mod settings.
>
>Note that do NOT include -XX:+DisableExplicitGC in your JVM arguments because the mod will not function at all with it.
>
> 
>If you don't want your game to freeze when cleaning memory, you should try these JVM arguments: (-Xmx and -Xms values are omitted)
>
>```
>-XX:+AggressiveOpts -XX:+UseConcMarkSweepGC -XX:+UseParNewGC -XX:+CMSConcurrentMTEnabled -XX:ParallelGCThreads=4 -Dsun.rmi.dgc.server.gcInterval=1800000
>-XX:+UnlockExperimentalVMOptions -XX:+ExplicitGCInvokesConcurrent -XX:MaxGCPauseMillis=50 -XX:+AlwaysPreTouch -XX:+UseStringDeduplication -Dfml.ignorePatchDiscrepancies=true
>-Dfml.ignoreInvalidMinecraftCertificates=true -XX:-OmitStackTraceInFastThrow -XX:+OptimizeStringConcat -XX:+UseAdaptiveGCBoundary -XX:NewRatio=3 -Dfml.readTimeout=90 -XX:+UseFastAccessorMethods
>```
>This enables concurrent explicit gc so that your game will not freeze during memory cleanings. The JVM arguments options should be found in your Minecraft launcher.

test