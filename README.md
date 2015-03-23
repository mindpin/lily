lily
====

4ye.me 所使用的公共 javascript 和 css, 以 git submodule 的形式引用到其他工程之中。原始代码以 sass &amp; coffee 编写。美术设计风格偏向于扁平化。

----------------

### compile

```
scss --watch .
coffee --watch --compile */*.coffee
ruby watch_index_haml.rb .
```

----------------

### run sample

```
ruby -run -e httpd . -p 4000
```

### 依赖的 Gem

fssm, haml, haml-coderay


### 如何在 rails 工程里使用 lily

1. 以 submodule 形式引入工程：
```
git submodule add git@github.com:mindpin/lily.git vendor/assets/lily
```

2. 修改引用信息
修改 .gitmodules 中引用部分为
```
[submodule "vendor/assets/lily"]
  path = vendor/assets/lily
  url = git://github.com/mindpin/lily.git
```
主要是 url 要改成 git:// 开头

3. 修改 application.scss

  在开头增加：
  
  ```scss
  $fa-font-path: "fonts" !default;
  @import "css/lily.scss";
  ```
  
  如果要修改其他常量，在 @import 之前修改