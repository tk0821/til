# 多態性
ある1つのメソッドを呼び出すときに、オブジェクトごとに振舞いが異なること。

Animalクラスにsleepメソッドがあり、そのクラスをDogクラスとCatクラスが継承し、それぞれsleepメソッドをオーバーライドした。

この時、Animal型配列にDogクラスとCatクラスを入れて、ループでsleepメソッドを呼び出せる。
``` Java
Animal[] a = new Character[2];
a[0] = new Dog();
a[1] = new Cat();

for (Animal e : a) {
  // DogのsleepとCatのsleepを呼び出せる
  e.sleep();
}

```
呼び出し側からはまとめて同じものとして扱って、異なる動作をするメソッドを呼び出せる。

