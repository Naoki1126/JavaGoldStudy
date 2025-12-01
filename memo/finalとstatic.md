# final修飾子とstatic修飾子

## final概要

```java

public final class A {

    public final String AA = "AA"
    public final void testA(){
        final String AAA = "AAA"
    }

    final int num2;
    A(int i) {
        num2 = i;
    }
}

```

- finalで就職されたクラスやメソッドはオーバーライド出来ない
- メンバ変数にする場合、宣言時に初期化するかコンストラクタやイニシャライザで初期化する必要がある
- ローカル変数にも使用可能

## static概要

- メソッド、変数に適用できる
- クラス宣言やコンストラクタには適用できない
- staticメンバは各オブジェクトに保持されず、別の箇所に一箇所にまとめられている

### nullへの対応

- 下記のような場合もstaticメンバを利用可能
- staticメンバはクラスが読み込まれれば利用可能

```java

class B {
    public static String SV = "SValue";
}

class C {
    public static void main(String args[]){
        B b = new B();
        b = null;
        // nullであってもOK
        b.SV
    }
}

```