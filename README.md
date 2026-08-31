# Allumeria-zh_CN
基于GPT制作的Allumeria简体中文字体注入包

适用游戏版本：0.15+

本包包含物品、方块与游戏内文本的简体中文，以及主菜单、角色与世界选择、设置页面、暂停菜单和加载提示的中文翻译。

原理
----
Allumeria 使用固定的 512x512 PNG 字模，并直接以字符码位定位字形。
本包用 Noto Sans SC 将当前简体中文翻译实际使用的汉字生成到原字模空闲区，
再把运行时翻译文本映射到这些字形位置。原英文、数字和符号字形保持不变。

安装
----
1. 退出 Allumeria。
2. 将本包内的 mods 文件夹复制到 Allumeria 游戏根目录。
3. 出现同名文件提示时，选择覆盖。
4. 在游戏语言设置中选择 Chinese (Simplified)。

游戏根目录通常为：
\SteamLibrary\steamapps\common\Allumeria

注意
----
- 游戏使用的是PNG字模，AI根据游戏自带文本风格制作，所以字体仅限能看。
- 游戏内容文本也由AI翻译，非精翻，凑合使用。
- 由于游戏内容未经测试，可能会有问题。
- 不影响解锁成就。

文本说明
----
- 若要修改或添加文本可直接编辑下面的文件：
\mods\Allumeria-zhCN-fontpack\res\translations\zh-CN\keys.txt
- 文件为 UTF-8 编码的正常简体中文。每行格式为“文本键 + 空格 + 中文内容”，只需修改空格后的翻译内容。请不要手动将文本改为乱码或字形编码。
- 游戏启动时，Loader.dll 会自动把可读中文转换为游戏 PNG 字库需要的运行时字形编码。因此，模组内保留的 `keys.txt` 始终方便后续维护。
- 现有翻译使用的全部中文字符和标点均已包含。若新增目前未收录的汉字、中文标点或其他非 ASCII 字符，还需要扩展字体图集，并在 glyph-zh-CN.map 中加入对应映射；否则该字符会在游戏中显示为 "?"。

文件说明
----
- mods\Loader.dll：菜单文本替换和可读中文转换加载器。
- mods\Allumeria-zhCN-fontpack\ui-zh-CN.map：主菜单、子菜单、暂停菜单和加载提示翻译。
- mods\Allumeria-zhCN-fontpack\glyph-zh-CN.map：可读中文与游戏字形编码的映射。
- mods\Allumeria-zhCN-fontpack\res\textures\font： PNG 字体图集。
