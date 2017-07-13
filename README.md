# DST-Console
这里是存放饥荒联机版控制台代码的。大家都可以进行修改。

c_give("prefab",amount)    刷物品到包里
c_spawn("prefab",amount)   刷物品到地上

设置三维淘气值温度（0.90 = 90%.）
c_sethea?lth(percent)
c_setsanit?y(percent)
c_sethunger(pe?rcent)
c_setmoisture(pe?rcent)
c_settemperature(degrees)

无敌
c_godmode()                    c_godmode()
c_supergodmode()

加速（1.2两倍速，20穿水）
c_speedmult(multiplier)

创造模式
ThePlayer.components.builder:GiveAllRecipes()

改三围
ThePlayer.components.health:SetMaxHealth(value)
ThePlayer.components.sanity:SetMax(value)
ThePlayer.components.hunger:SetMax(value)

停止饥饿
ThePlayer.components.hunger:Pause(true)

设置攻击伤害倍数
ThePlayer.components.combat.damagemultiplier = value

吴迪变身（1是变回来）
ThePlayer.components.beaverness:SetPercent(.01)

列出玩家编号用于控制
c_listallplayers()

将玩家传送到鼠标位置
c_move(AllPlayers[number])

杀死某位玩家（编号/名字）
AllPlayers[number]:PushEvent('death')
UserToPlayer('PlayerA'):PushEvent('death')

复活某位玩家
AllPlayers[number]:PushEvent('respawnfromghost')

传送到某玩家旁
c_goto(AllPlayers[number])

掉落某玩家的所有物品
AllPlayers[number].components.inventory:DropEverything()

更改某玩家角色
c_despawn(AllPlayers[number])

删除指针物品（主机/服务器）
ConsoleWorldEntityUnderMouse():Remove()
c_select():Remove()
c_select()c_sel():Remove()   需要按一下Ctrl键

全地图
minimap = TheSim:FindFirstEntityWithTag("mini-map")
TheWorld.minimap.MiniMap:ShowArea (0,0,0,10000)

跳过一天
?TheWorld:PushEvent("ms_nextcycle")
LongUpdate(480)

跳过一个时期
TheWorld:PushEvent("ms_nextphase")

设置日夜构成
TheWorld:PushEvent("ms_setclocksegs", {day=14,dusk=1,night=1})

设置季节构成
TheWorld:PushEvent("ms_setseasonclocksegs", {summer={day=14,dusk=1,night=1}, winter={day=13,dusk=1,night=2}})

设置季节长度
TheWorld:PushEvent("ms_setseasonlength", {season="summer", length=15})

开始某个季节
TheWorld:PushEvent("ms_setseason", "summer")

下雨/停雨
TheWorld:PushEvent("ms_forceprecipitation")
TheWorld:PushEvent("ms_forceprecipitation", false)

指针处闪电
TheWorld:PushEvent("ms_sendlightningstrike", ConsoleWorldPosition())

指针处流星袭击
c_spawn("shadowmeteor", 1)

踢/禁止某用户
TheNet:Kick(userid)
TheNet:Ban(userid)
TheNet:BanForTime(userid,time_in_seconds)

地图重置
c_reset()

世界/区域重生
c_regenerateworld()
c_regenerateshard()

立刻保存进度
c_save()

保存/不保存退出
c_shutdown( true / false)

回档，空参数回档一天
c_rollback(count)

允许/禁止新玩家加入
TheNet:SetAllowIncomingConnections( true / false )

公告（服务器）
c_announce("announcement")

生成虫洞（按步骤）
worm1 = c_spawn("wormhole")
worm2 = c_spawn("wormhole")
worm1.components.teleporter.targetTeleporter = worm2
worm2.components.teleporter.targetTeleporter = worm1

材料： 
cutgrass（草）
twigs（树枝）
log（木头）
charcoal（木炭）
ash（灰）
cutreeds（采下的芦苇）
lightbulb（荧光果）
petals（花瓣）
petals_evil（噩梦花瓣）
pinecone（松果）
foliage（叶子）
cutlichen（摘下的苔藓）
wormlight（虫子果）
lureplantbulb（食人花种子）
flint（燧石）
nitre（硝石）
redgem （红宝石）
bluegem（蓝宝石）
purplegem（紫宝石）
greengem（绿宝石）
orangegem（橙宝石）
yellowgem（黄宝石）
rocks（岩石）
goldnugget（黄金）
thulecite（铥矿石）
thulecite_pieces（铥矿碎片）
rope（绳子）
boards（木板）
cutstone（石砖）
papyrus（纸）
houndstooth（犬牙）
pigskin（猪皮）
manrabbit_tail（兔人尾巴）
silk（蜘蛛丝）
spidergland（蜘蛛腺体）
spidereggsack（蜘蛛卵）
beardhair（胡子）
beefalowool（牛毛）
honeycomb（蜂巢）
stinger（蜂刺）
walrus_tusk（海象牙）
feather_crow（乌鸦羽毛）
feather_robin（红雀羽毛）
feather_robin_winter（雪雀羽毛）
horn（牛角）
tentaclespots（触手皮）
trunk_summer（夏象鼻）
trunk_winter（冬象鼻）
slurtleslime（蜗牛龟粘液）
slurtle_shellpieces（蜗牛龟壳片）
butterflywings（蝴蝶翅膀）
mosquitosack（蚊子血囊）
slurper_pelt（啜食者皮）
minotaurhorn（远古守护者角）
deerclops_eyeball（巨鹿眼球）
lightninggoathorn（闪电羊角）
glommerwings（格罗门翅膀）
glommerflower（格罗门花）
glommerfuel（格罗门燃料）
livinglog（活木头）
nightmarefuel（噩梦燃料）
gears（齿轮）
transistor（晶体管）
marble（大理石）
boneshard（硬骨头）
ice（冰）
poop（便便）
guano（鸟粪）
dragon_scales（蜻蜓鳞片）
goose_feather（鹿鸭羽毛）
coontail（浣熊尾巴）
bearger_fur（熊皮）
townportaltalisman（砂石）
shroom_skin（毒蟾蜍皮）
Deer_Antler（无眼鹿茸）
KlausSackKey（克劳斯的鹿茸）
atrium_key（远古钥匙）
fossil_piece（化石）
shadowheart（暗影之心）
 

工具/武器：
 
axe（斧子）
goldenaxe（黄金斧头）
lucy（露西斧子）
hammer（锤子）
pickaxe（镐）
goldenpickaxe（黄金镐）
shovel（铲子）
goldenshovel（黄金铲子）
pitchfork（草叉）
razor（剃刀）
bugnet（捕虫网）
fishingrod（鱼竿）
multitool_axe_pickaxe（多功能工具）
cane（行走手杖）
trap（陷阱）
birdtrap（鸟陷阱）
trap_teeth（牙齿陷阱）
trap_teeth_maxwell（麦斯威尔的牙齿陷阱）
backpack（背包）
piggyback（猪皮包）
krampus_sack（坎普斯背包）
umbrella（雨伞）
grass_umbrella（草伞）
heatrock（保温石）
bedroll_straw（草席卷）
bedroll_furry（毛皮铺盖）
torch（火炬）
lantern（提灯）
pumpkin_lantern（南瓜灯）
compass（指南针）
fertilizer（化肥）
firesuppressor（灭火器）
sewing_kit（缝纫工具包）
spear（矛）
boomerang（回旋镖）
tentaclespike（狼牙棒）
blowdart_pipe（吹箭）
blowdart_sleep（麻醉吹箭）
blowdart_fire（燃烧吹箭）
hambat（火腿短棍）
nightsword（暗影剑）
batbat（蝙蝠棒）
ruins_bat（远古短棒）
spear_wathgrithr（瓦丝格雷斯矛）
panflute（排箫）
onemanband（独奏乐器）
gunpowder（火药）
beemine（蜜蜂地雷）
bell（铃）
amulet（红色护身符）
blueamulet（蓝色护身符）
purpleamulet（紫色护身符）
yellowamulet（黄色护身符）
orangeamulet（橙色护身符） 
greenamulet（绿色护身符）
nightmare_timepiece（铥矿奖章）
icestaff（冰魔杖）
firestaff（火魔杖）
telestaff（传送魔杖）
orangestaff（橙色魔杖）
greenstaff（绿色魔杖）
yellowstaff（黄色魔杖）
diviningrod（探矿杖）
book_birds（召唤鸟的书）
book_tentacles（召唤触手的书）
book_gardening（催生植物的书）
book_sleep（催眠的书）
book_brimstone（召唤闪电的书）
waxwelljournal（麦斯威尔的日志）
abigail_flower（阿比盖尔之花）
balloons_empty（空气球）
balloon（气球）
lighter（薇洛的打火机）
chester_eyebone（切斯特骨眼）
featherfan（羽毛扇）
staff_tornado（龙卷风魔杖）
nightstick（夜棍） 

穿戴： 
strawhat（草帽）
flowerhat（花环）
beefalohat（牛毛帽）
featherhat（羽毛帽）
footballhat（猪皮帽）
tophat（高礼帽）
earmuffshat（兔耳罩）
winterhat（冬帽）
minerhat（矿工帽）
spiderhat（蜘蛛帽）
beehat（蜂帽）
walrushat（海象帽）
slurtlehat（蜗牛帽子）
bushhat（丛林帽）
ruinshat（远古王冠）
rainhat（防雨帽）
icehat（冰帽）
watermelonhat（西瓜帽）
catcoonhat（浣熊帽）
wathgrithrhat（瓦丝格雷斯帽）
armorwood（木盔甲）
armorgrass（草盔甲）
armormarble（大理石盔甲）
armor_sanity（夜魔盔甲）
armorsnurtleshell（蜗牛龟盔甲）
armorruins（远古盔甲）
sweatervest（小巧背心）
trunkvest_summer（夏日背心）
trunkvest_winter（寒冬背心）
armorslurper（饥饿腰带）
raincoat（雨衣）
webberskull（韦伯头骨）
molehat（鼹鼠帽）
armordragonfly（蜻蜓盔甲）
beargervest（熊背心）
eyebrellahat（眼睛帽）
reflectivevest（反射背心）
hawaiianshirt（夏威夷衬衫） 
goggleshat（时尚目镜）
deserthat（沙漠护目镜）
green_mushroomhat（绿蘑菇帽）
blue_mushroomhat（蓝蘑菇帽）
red_mushroomhat（红蘑菇帽）
thurible（暗影香炉）
armorskeleton（骨甲）


建筑： 
campfire（营火）
firepit（石头营火）
coldfire（冷火）
coldfirepit（石头冷火）
cookpot（锅）
icebox（冰箱）
winterometer（寒冰温度计）
rainometer（雨量计）
slow_farmplot（一般农田）
fast_farmplot（高级农田）
siestahut（午睡小屋）
tent（帐篷）
homesign（路牌）
birdcage（鸟笼）
meatrack（晾肉架）
lightning_rod（避雷针）
pottedfern（盆栽）
nightlight（暗夜照明灯）
nightmarelight（影灯）
researchlab（科学机器）
researchlab2（炼金术引擎）
researchlab3（阴影操纵者）
researchlab4（灵子分解器）
treasurechest（木箱）
skullchest（骷髅箱）
pandoraschest（华丽的箱子）
minotaurchest（大华丽的箱子）
wall_hay_item（草墙）
wall_wood_item（木墙）
wall_stone_item（石墙）
wall_ruins_item（铥墙）
wall_hay（地上的草墙）
wall_wood（地上的木墙）
wall_stone（地上的石墙）
wall_ruins（地上的铥墙）
pighouse（猪房）
rabbithole（兔房）
mermhouse（鱼人房）
resurrectionstatue（肉块雕像）
resurrectionstone（重生石）
ancient_altar （远古祭坛）
ancient_altar_broken （损坏的远古祭坛）
telebase（传送核心）
gemsocket（宝石看台）
eyeturret（固定在地上的眼睛炮塔）
eyeturret_item（可带走的眼睛炮塔）
cave_exit（洞穴出口）
turf_woodfloor（木地板）
turf_carpetfloor（地毯地板）
turf_checkerfloor（棋盘地板）
adventure_portal（冒险之门）
rock_light（火山坑）
gravestone（墓碑）
mound（坟墓土堆）
skeleton（人骨）
houndbone（狗骨头）
animal_track（动物足迹）
dirtpile（可疑的土堆）
pond（池塘）
pond_cave（洞穴池塘）
pighead（猪头棍）
mermhead（鱼头棍）
pigtorch（猪火炬）
rabbithole（兔子洞）
beebox（蜂箱）
beehive（野生蜂窝）
wasphive（杀人蜂窝）
spiderhole（洞穴蜘蛛洞）
walrus_camp（海象窝）
tallbirdnest（高鸟窝）
houndmound（猎犬丘）
slurtlehole（蜗牛窝）
batcave（蝙蝠洞）
monkeybarrel（猴子桶）
spiderden（蜘蛛巢穴）
molehill（鼹鼠丘）
catcoonden（浣熊洞）
rock1（带硝石的岩石）
rock2（带黄金的岩石）
rock_flintless（只有石头的岩石）
stalagmite_full（大圆洞穴石头）
stalagmite_med（中圆洞穴石头）
stalagmite_low（小圆洞穴石头）
stalagmite_tall_full（大高洞穴石头）
stalagmite_tall_med（中高洞穴石头）
stalagmite_tall_low（小高洞穴石头）
rock_ice（冰石）
ruins_statue_head（远古头像）
ruins_statue_mage（远古法师雕像）
marblepillar（大理石柱子）
marbletree（大理石树）
statueharp（竖琴雕像）
basalt（玄武岩）
basalt_pillar（高玄武岩）
insanityrock（猪王矮柱石）
sanityrock（猪王高柱石）
ruins_chair（远古椅子）
ruins_vase（远古花瓶）
ruins_table（远古桌子）
statuemaxwell（麦斯威尔雕像）
statueglommer（格罗门雕像）
relic（废墟）
ruins_rubble（损毁的废墟）
bishop_nightmare（损坏的雕像）
rook_nightmare（损坏的战车）
knight_nightmare（损坏的骑士）
chessjunk1（损坏的机械1）
chessjunk2（损坏的机械2）
chessjunk3（损坏的机械3）
teleportato_ring（环状传送机零件）
teleportato_box（盒状传送机零件）
teleportato_crank（曲柄状传送机零件）
teleportato_potato（球状传送机零件）
teleportato_base（传送机零件底座）
teleportato_checkmate（传送机零件底座）
wormhole（虫洞）
wormhole_limited_1（被限制的虫洞）
stafflight（小星星）
treasurechest_trap（箱子陷阱）
icepack（冰包）
dragonflychest（蜻蜓箱子） 
antlion_sinkhole（地陷）
cavein_boulder（落石）
townportal（慵懒的传送者）
succulent_potted（多肉植物盆栽）
glassspike_short（玻璃尖锥  小）
glassspike_med（玻璃尖锥  中）
glassspike_tall（玻璃尖锥  大）
glassblock(玻璃陈堡)
mushroom_light（蘑菇灯   单）
mushroom_light2（蘑菇灯   多重）
Klaus_sack（克劳斯的袋子）



食物： 
carrot（胡萝卜）
carrot_cooked（熟胡萝卜）
berries（浆果）
berries_cooked（熟浆果）
pumpkin（南瓜）
pumpkin_cooked（熟南瓜）
dragonfruit（火龙果）
dragonfruit_cooked（熟火龙果）
pomegranate（石榴）
pomegranate_cooked（熟石榴）
corn（玉米）
corn_cooked（熟玉米）
durian（榴莲）
durian_cooked（熟榴莲）
eggplant（茄子）
eggplant_cooked（熟茄子）
cave_banana（洞穴香蕉）
cave_banana_cooked（熟洞穴香蕉）
acorn（橡果）
acorn_cooked（熟橡果）
cactus_meat（仙人掌肉）
watermelon（西瓜）
red_cap（采摘的红蘑菇）
red_cap_cooked（煮熟的红蘑菇）
green_cap（采摘的绿蘑菇）
green_cap_cooked（煮熟的绿蘑菇）
blue_cap_cooked（煮熟的蓝蘑菇）
blue_cap（采摘的蓝蘑菇）
seeds（种子）
seeds_cooked（熟种子）
carrot_seeds（胡萝卜种子）
pumpkin_seeds（南瓜种子）
dragonfruit_seeds（火龙果种子）
pomegranate_seeds（石榴种子）
corn_seeds（玉米种子）
durian_seeds（榴莲种子）
eggplant_seeds（茄子种子）
smallmeat（小肉）
cookedsmallmeat（小熟肉）
smallmeat_dried（小干肉）
meat（大肉）
cookedmeat（大熟肉）
meat_dried（大干肉）
drumstick（鸡腿）
drumstick_cooked（熟鸡腿）
monstermeat（疯肉）
cookedmonstermeat（熟疯肉）
monstermeat_dried（干疯肉）
plantmeat（食人花肉）
plantmeat_cooked（熟食人花肉）
bird_egg（鸡蛋）
bird_egg_cooked（煮熟的鸡蛋）
rottenegg（烂鸡蛋）
tallbirdegg（高鸟蛋）
tallbirdegg_cooked（熟高鸟蛋）
tallbirdegg_cracked（孵化的高鸟蛋）
fish（鱼）
fish_cooked（熟鱼）
eel（鳗鱼）
eel_cooked（熟鳗鱼）
froglegs（蛙腿）
froglegs_cooked（熟蛙腿）
batwing（蝙蝠翅膀）
batwing_cooked（熟蝙蝠翅膀）
trunk_cooked（熟象鼻）
mandrake（曼德拉草）
cookedmandrake（熟曼特拉草）
honey（蜂蜜）
butter（黄油）
butterflymuffin（奶油松饼）
frogglebunwich（青蛙圆面包三明治）
honeyham（蜜汁火腿）
dragonpie（龙馅饼）
taffy（太妃糖）
pumpkincookie（南瓜饼）
kabobs（肉串）
powcake（芝士蛋糕）
mandrakesoup（曼德拉草汤）
baconeggs（鸡蛋火腿）
bonestew（肉汤）
perogies（半圆小酥饼）
wetgoop（湿腻焦糊）
ratatouille（蹩脚的炖菜）
fruitmedley（水果拼盘）
fishtacos （玉米饼包炸鱼）
waffles （华夫饼）
turkeydinner（火鸡正餐）
fishsticks（鱼肉条）
stuffedeggplant（香酥茄盒）
honeynuggets（甜蜜金砖）
meatballs（肉丸）
jammypreserves（果酱蜜饯）
monsterlasagna（怪物千层饼）
unagi（鳗鱼料理）
bandage（蜂蜜绷带）
healingsalve（治疗药膏）
spoiled_food（腐烂食物）
flowersalad（花沙拉）
icecream（冰激淋）
watermelonicle（西瓜冰）
trailmix（干果）
hotchili（咖喱）
guacamole（鳄梨酱）
goatmilk（羊奶）
 

植物： 
flower（花）
flower_evil（噩梦花）
carrot_planted（长在地上的胡萝卜）
grass（长在地上的草）
depleted_grass（草根）
dug_grass（长草簇）
sapling（树苗）
dug_sapling（可种的树苗）
berrybush（果树丛）
dug_berrybush（可种的果树丛）
berrybush2（果树丛2）
dug_berrybush2（可种的果树丛2）
marsh_bush（尖刺灌木）
dug_marsh_bush（可种的尖刺灌木）
reeds（芦苇）
lichen（洞穴苔藓）
cave_fern（蕨类植物）
evergreen（树）
evergreen_sparse（无松果的树）
marsh_tree（针叶树）
cave_banana_tree（洞穴香蕉树）
livingtree（活树）
deciduoustree（橡树）
deciduoustree_tall（高橡树）
deciduoustree_short（矮橡树）
red_mushroom（红蘑菇）
green_mushroom（绿蘑菇）
blue_mushroom（蓝蘑菇）
mushtree_tall（高蘑菇树）
mushtree_medium（中蘑菇树）
mushtree_small（小蘑菇树）
flower_cave（单朵洞穴花）
flower_cave_double（双朵洞穴花）
flower_cave_triple（三朵洞穴花）
tumbleweed（滚草）
cactus（仙人掌）
cactus_flower（仙人掌花）
marsh_plant（水塘边小草）
pond_algae（水藻）
mushroomsprout（毒蘑菇树）

动物： 
rabbit（兔子）
perd（火鸡）
crow（乌鸦）
robin（红雀）
robin_winter（雪雀）
butterfly（蝴蝶）
fireflies（萤火虫）
bee（蜜蜂）
killerbee（杀人蜂）
flies（苍蝇）
mosquito（蚊子）
frog（青蛙）
beefalo（牛）
babybeefalo（小牛）
lightninggoat（闪电羊）
pigman（猪人）
pigguard（猪守卫）
bunnyman（兔人）
merm（鱼人）
spider_hider（洞穴蜘蛛）
spider_spitter（喷射蜘蛛）
spider（地面小蜘蛛）
spider_warrior（地面绿蜘蛛）
spiderqueen（蜘蛛女王）
spider_dropper（白蜘蛛）
hound（猎狗）
firehound（红色猎狗）
icehound（冰狗）
tentacle（触手）
tentacle_garden（巨型触手）
leif（树精）
leif_sparse（稀有树精）
walrus（海象）
little_walrus（小海象）
smallbird（小高鸟）
teenbird（青年高鸟）
tallbird（高鸟）
koalefant_summer（夏象）
koalefant_winter（冬象）
penguin（企鹅）
slurtle（蜗牛龟）
snurtle（黏糊虫）
bat（蝙蝠）
rocky（龙虾）
monkey（猴子）
slurper（缀食者）
buzzard（秃鹫）
mole（鼹鼠）
catcoon（浣熊）
knight（发条骑士）
bishop（主教）
rook（战车）
crawlinghorror（爬行暗影怪）
terrorbeak（尖嘴暗影怪）
deerclops（巨鹿）
minotaur（远古守护者）
stalker_minion1（远古虫子1）
stalker_minion2（远古虫子2）
 
worm（远古虫子）
abigail（阿比盖尔）
ghost（幽灵）
shadowwaxwell（麦斯威尔黑影小人）
krampus（坎普斯）
glommer（格罗门）
chester（切斯特）
lureplant（食人花）
eyeplant（食人花眼睛）
bigfoot（大脚）
pigking（猪王）
moose（鹿鸭）
mossling（小鸭）
dragonfly（蜻蜓）
warg（座狼）
bearger（熊）
birchnutdrake（坚果鸭）
mooseegg（鹿鸭蛋）
antlion(蚁狮）
toadstool（蛤蟆）
klaus（克劳斯）
stalker_forest（森林狩猎者）
stalker（暗影狩猎者）
stalker_atrium（远古狩猎者）
