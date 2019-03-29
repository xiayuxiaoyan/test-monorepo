# test-monorepo
test ourself's git flow
操作：
- 拉出A/B分支
master -》 A
master -》 B
- 编辑A/B，干掉不属于彼此的业务代码
- mster分别merge A/B
- 把AB内容手动都加到master里
- 编辑A/B
- master去mergeA/B
- base去merge master
指令处理特殊：
```
git merge --no-ff --no-commit branch
git reset HEAD xxfile/
git checkout xxfile
rm -rf xxfile
git commit -m'merge master'
```
处理的结果
base只有基础
A/B只有AB/代码和base
master 有 AB和base的代码，可以用来开发base在AB上测试
AB业务开发，代码清晰 历史干净
base去同步给A/B，分支也很干净
*看效果，是否master能集成A/B最新的代码*

