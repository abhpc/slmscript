# slmscript命令简介 <!-- omit in toc -->
slmscript是一个用于管理公共slurm脚本的工具，**<u>```slmscript```命令支持```Tab```键补全</u>。**
```bash
slmscript

slmscript usage:

        (1) slmscript ls : show available slurm scripts.

        (2) slmscript cp [script] : copy script to current directory.

        (3) slmscript cat [script] : show script content.

        (4) slmscript vi [script] : edit/create script content.

```

- [1 安装](#1-安装)
- [2 显示可用作业脚本模板](#2-显示可用作业脚本模板)
- [3 拷贝目标脚本模板到当前目录下](#3-拷贝目标脚本模板到当前目录下)
- [4 显示脚本模板内容](#4-显示脚本模板内容)
- [5 查看/编辑脚本模板内容(普通用户只读，root可编辑)](#5-查看编辑脚本模板内容普通用户只读root可编辑)

## 1 安装
```slmscript```需要预装```bash-completion```，安装建议如下操作：
```bash
yum localinstall ./slmscript-xxx.x86_64.rpm
```
安装好以后，修改文件```/etc/slmscript.conf```指定slurm脚本的公共存放目录(默认目录是```/opt/slmscripts```)：
```bash
# Define slurm scripts path
SLURM_SCRIPTS_PATH = /opt/slmscripts/
```

## 2 显示可用作业脚本模板
```bash
slmscript ls

abaqus_new.slm  anaconda.slm  comsol.slm  epoch.slm    g16.slm     lsdyna_mpp.slm  mscastep.slm   polygrpfc.slm  slm.lammps  slm.vasp      test.slm
abaqus.slm      castep.slm    cp2k.slm    g16-mem.slm  lammps.slm  lsdyna_smp.slm  orcatmpfs.slm  qe.slm         slm.orca    starccm+.slm  vasp.slm
```

## 3 拷贝目标脚本模板到当前目录下
注意这里```<xxx.slm>```可以按Tab键补全:
```bash
slmscript cp <xxx.slm>
```

## 4 显示脚本模板内容
注意这里```<xxx.slm>```可以按Tab键补全:
```bash
slmscript cat <xxx.slm>
```

## 5 查看/编辑脚本模板内容(普通用户只读，root可编辑)
```bash
slmscript vi <xxx.slm>  #注意这里xxx.slm可以按Tab键补全
```