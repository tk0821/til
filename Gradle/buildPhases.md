ビルドは以下の流れで行われる。

+ Initialization
+ Configuration
+ Execution

### Initialization
設定ファイルの検出、プロジェクトのインスタンス化を行う

### Configuration
プロジェクトにタスクやプロパティを追加する

### Execution
タスクを実行する

## 実行してみる

``` Groovy
// build.gradle
println 'A'

tasks.register('task') {
  doLast {
    println 'B'
  }
  doFirst {
    println 'C'
  }
  println 'D'
}
```
``` Groovy
// settings.gradle
println 'E'
```

```
> gradle task
E

> Configure project :
A
D

> Task :task
C
B
```

Initializationでsettings.gradleが呼び出されている

Configurationで各タスクのprintlnが実行

doFirst, doLastはタスク実行前後に呼び出されるため、Executionで実行される

# 参考
https://docs.gradle.org/current/userguide/build_lifecycle.html#sec:build_phases
