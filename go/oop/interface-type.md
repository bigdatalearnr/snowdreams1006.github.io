# 再谈接口

接口是面向对象编程中继封装后的另一个重要概念,如果封装表达的是某一类现实事务的抽象共性,那么接口则是表示不同抽象概念之间的内在联系,这种联系可以跨域种族,跨域地区,并不是像是继承概念那样的强相关,而是一种更高层次的联系.

封装,继承和多态是面向对象编程风格中广为人知的重要特性,也常常被认为是衡量一种编程语言是否是面向对象语言的重要标准.

接口描述的是规范和实现的规则,接口定义了约束规范,至于如何实现这种规范则是接口的实现者必须关心的,从这点来看,接口就像是现实生活中的上级领导下达指令目标,下属则负责实现目标,至于如何实现,领导并不关心,正所谓条条大路通罗马,手底下的人自然是八仙过海各显神通.

领导关心结果,下属关心过程,这种模型就是编程语言中接口和实现类的关心.

如果站在领导者的角度上看问题,自然是希望下属规规矩矩按时完成自己布置的任务,千万不要出现任何差池,领导的威望和下属的恪尽职责才能换来大家的和平共处.

为了达到这个目标,领导者首先要在下属中树立足够高的威信,做到人人信服自己,手底下的人和自己统一战线才能一致对外,团结在一起才能好做事.

这种威信的树立要么靠的是能力上技高一筹实力碾压下属,要么是知人善任天下贤才皆为我所用,还可以狐假虎威绿叶衬红花思想上奴役统治.

最近重温神话,每每看到项羽兵败乌江就痛惜不已,李清照的至今思项羽,不肯过江东不自觉萦绕脑海.

项羽天生神力,力能扛鼎,兵败乌江时手底下只有18人亲信,却个个没有贪生怕死之辈,一直奋勇杀敌直到全部战死也无一人投降.

因为项羽自身能力值太过强悍,所以在古代崇武思想中自然有一大批追随者,仰慕强者自然愿意追随强者.

所以项羽是靠个人魅力逐步发家的,楚汉相争前期项羽更是占尽了先机,然而个人魅力太盛也不见得是一种好事,如果是大将军的话,那么自然没太大问题.

可是,项羽却不是大将军而是要成为帝王,个人英雄主义并不适合君王的身份.这一点倒是和三国时的关羽有些类似,自己能力太高则看不起不如自己的人.

内心的孤傲是掩饰不了,挤兑走了韩信,一意孤行气的叔父项梁摇头叹息,或许正是这种性格也暗示了最终的自刎结局.

虞兮虞兮奈若何

反观刘邦,只是沛县一个地痞无赖,人人都瞧不起,不管不顾世俗的眼光,坚信自己是做大事的人.

虽然自己没有武力值加持,但是手底下却有一大批的武将,前期只有挨打的份,丢盔弃甲,好不狼狈,如果故事到这里就戛然而止的话,那么一切似乎是理所当然.

论计策,我不如子房.

休养生息中善于笼络人心,知人善任天下英才仅为我所用,四年的楚汉相争中最终逼得项羽兵败乌江,赢得了最后的胜利.

或许正是刘邦的成功,激励着后来的造反者不论出身,皇帝再也不是贵族专有特权,人人都可以做皇帝,斩白蛇起义这种套路更是屡见不鲜.

没有技能,神仙来凑,在那个迷信的古代,但凡造反者起义前都要先鼓吹一番,笼络人心,做到出师有名,从气势上占据优势.

一旦成功,身份又变成了统治者,接下来就开始思考如何维持自身统治,四书五经,学习儒家思想等一系列手段用来维护统治.

上层建筑当政时一定会宣扬一种思想学说来稳定自己的统治,只有实现这种官方规范的天下人才能有一条出路,否则便是异类,不被世俗接受.

这种自上而下的规范是一种强约束,上层建筑也可以随时调整策略以求更好的维稳,下面的人不动乱,则上面的人就能坐得稳.

如果上层建筑的官方规范越来越严,底层人民不堪重负,无法按时交粮交税很容易再次爆发起义,此时又会诞生出千千万万个刘邦,重新建立新的规范制度.

滚滚长江东逝水,浪花淘尽英雄.

清朝科举之所以写八股文,是因为官方要求,不走科举这条路,穷苦人家没有上升的渠道.
上层建筑之所以考八股文,是因为能够筛选出志同道合的人,读书人安静了,世道也就安静了.

自古造反者一定是有学问的,什么文化都没有的人就连造反充其量也就是一群乌合之众,成不了气候!

站在上层建筑的角度看下层实现,我们自然是希望制定好规范后都要遵守,不要出什么幺蛾子.

上边的命令就是圣旨就是军令如山,下边的人一定要按照规章制度办事,不逾矩.

当这种限制发展到顶峰时,各种各样的限制越来越束缚下面的手脚,晋升无望,任人宰割乎?

北宋羸弱,军事上虽有名将但无实权,皇帝一声令下,也不得不班师回朝,战场战机变化莫测,瞬息万变但有上级指令在,却不得不按章办事.

规则已经制定,剩下的事情就去实现吧,怎么实现我不管,完完全全按照规则办事不逾矩,否则就是叛国贼子,居心叵测.

如果站在底层实现者的角度思考问题,这种上层建筑和下层实现的关心还是会存在的,不同之处是下层实现时拥有了一定的自主性.

既不希望圣旨的神圣性受到侵犯,也不希望唯命是从,在大原则不便的基础上拥有一定的自主权利,可以做到因地制,顺势而为.

将在外君令有所不受,战争的胜负不再一城一池的得失,攻心为上攻城次之.虽然上面有命令,但是实现者也可以因为情势不同,不按照这次的小命令办事,换一种自主的思路最终实现目标,完成根本目标也是胜利.

所以,这种接口和实现的关系中实现者可以不必随时向接口报告,只要总体上不违背接口的总体规划那么就是忠君爱国.

如果仅仅考虑接口和实现的关系,这种关系很容易推断,实现者要么一定上报接口,要么一定不上报接口,除此之外,很明显还有另外一种可能性,实现者可能报告也可能不报告接口.

那么,这种似乎而非的关系有什么不同,又该如何表示呢?

按照语义进行理解.报告给接口的一定是万分紧急重要的规范,大是大非面前不能有任何个人情感,一旦实现者无法实现,那么便不可饶恕,零容忍!

如果实现者不报告给接口,则表示这种规范是可选规范,如果满足的话,最好不过,如果有特殊情况一时没能实现也不是致命的问题,这类规范属于锦上添花的操作.

如果要描述这种可有可无规范和实现的关系,显而易见的是,理应由接口定义者来指明接口的优先级,不能由实现者定义,否则的话,你认为爱国是必选的,他认为是可选的,那么接口的存在还有什么意义?



