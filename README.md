```
  _____   ____       _      ____    ____
 |  ___| |  _ \     / \    / ___|  / ___|
 | |_    | |_) |   / _ \   \___ \  \___ \
 |  _|   |  __/   / ___ \   ___) |  ___) |
 |_|     |_|     /_/   \_\ |____/  |____/
```

[![GPL-3.0](https://img.shields.io/badge/license-GPL--3.0-blue.svg)](LICENSE)
[![Sync Gitee](https://img.shields.io/badge/sync-gitee-green.svg)](https://gitee.com/fpass/fpass)
[![Build Status](https://travis-ci.org/fpass/fpass.svg?branch=master)](https://travis-ci.org/fpass/fpass)
[![Greenkeeper badge](https://badges.greenkeeper.io/fpass/fpass.svg)](https://greenkeeper.io)

只需记住一个足够长的安全主密码，无需安装任何插件、应用，就可以安全管理所有网站的密码

https://fpass.github.io

## 功能

* [x] 防止黑客攻击，可生成符合网站密码长度限制的最长且包含大小写字母和数字的强密码
* [x] 防止社工撞库，不同网站生成的密码不同
* [x] 不可逆，即使其中一个网站的密码明文泄露也不会令你的主密码暴露

## 使用

访问 [FINAL PASS - 密码安全管理工具](https://fpass.github.io)，选择域名，输入安全主密码，点击确定即可生成

生成的密码将被复制到剪贴板，页面不做展示，可直接粘贴到网站的密码框中使用

如果您需要设置密码的网站不在列表之中，欢迎提 issue 或 pull request 添加

也可以选择列表第一项 `自定义` 来自由生成密码

> 私人设备，可使用浏览器或应用的记住密码功能保存密码，避免每次登录需要重新生成、输入

## 原理

我们将通过下列步骤为您生成密码

1.  将输入的密码拼接上网站域名，使用 SHA-512 对其进行 3 次计算
1.  依据网站对密码最大长度限制截取计算结果
1.  依据 ASCII 对截取结果的前 3 位字符做转换操作，第 1 位转大写字母，第 2 位转小写字母，第 3 位转数字

> 包含大小写字母和数字的密码，可以满足绝大多数网站对密码强度的要求
