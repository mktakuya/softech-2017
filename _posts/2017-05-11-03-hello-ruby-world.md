---
layout: post
title:  "03 こんにちはRuby"
date:   2017-05-11 12:00:00 +0900

---

メモ: GWの話

自由課題部門志望2年生向けの講義では、新しいプログラミング言語として「Ruby」を扱います。

## とりあえずHello World!してみる

1年前、みなさんはC言語で以下のようなHello Worldプログラムを書きました。

{% highlight c linenos %}
// hello.c
#include <stdio.h>

int main(void) {
        printf("Hello World!\n");
        return 0;
}
{% endhighlight %}

初心にかえって、RubyでHello Worldプログラムを記述してみましょう。以下のプログラムを書いて保存してください。ファイル名は、hello.rbとします。

{% highlight ruby linenos %}
# hello.rb
puts "Hello World!"
{% endhighlight %}

テキストエディタで記述したRubyプログラムを実行するには、以下のようなコマンドを実行してください。

```
$ ruby hello.rb
```

どうでしょうか。うまくいきましたか？


## 対話的実行環境

Rubyプログラムを実行するもう一つの方法として、irbがあります。irbを用いると、その場で対話的にRubyプログラムを実行することができます。

以下のコマンドを実行してください。

```
$ irb
```

すると、

```
irb(main):001:0>
```

というような表示が現れます。これは、irbがあなたのコードを入力するのを待っている状態です。

何か式を入力すると、irbはその式を実行して、結果を表示します。

```
irb(main):001:0> 1 + 1
=> 2
irb(main):002:0> Time.now
=> 2017-05-10 16:23:08 +0900
```

if式のような制御構造を入力すると、対応するendを入力するまで待ってから実行されます。

```
irb(main):003:0> result = "OK"
=> "OK"
irb(main):004:0> if result == "OK"
irb(main):005:1>   puts "OK!"
irb(main):006:1> else
irb(main):007:1*   puts "NG!"
irb(main):008:1> end
OK!
=> nil
```

```
irb(main):009:0> 10.times do
irb(main):010:1*   puts "Hello"
irb(main):011:1> end
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
Hello
=> 10
```

irbを終了するには、quitと入力するから、キーボードのCtrl-dを入力します。

irbは、Rubyそのものの学習や、試行錯誤をするのに向いています。ぜひ活用していきましょう。

## プログラミング言語Ruby

### Rubyの特徴

コードを書いて疲れたと思うので、少しディスカッションしましょう。C言語のHello Worldプログラムと、RubyのHello Worldプログラムを書いて実行した上で、どのような違いがあったでしょうか。

#### Rubyはインタプリタ言語

プログラミング言語は、実行するためにコンパイルが必要なコンパイラ型言語と、コンパイルを必要としないインタプリタ言語に分類することができます。先ほど書いたhello.cを実行するためには、コンパイルが必要でした。Rubyはインタプリタ言語に属するので、我々人間が事前にコンパイルの作業をすることなく実行することができます。

一方、インタプリタ言語では、コンパイルという過程を挟まない分、コンパイラによるエラーチェックが行われません。C言語では、宣言していない変数を使おうとしたり、中括弧の対応が取れていなかったりするとコンパイル時にエラーとして教えてくれるますが、Rubyはコンパイルという作業が無いため、正しいプログラムが書けているかどうかは実行してみるまでわかりません。

### Rubyはオブジェクト指向言語である

Rubyは、オブジェクト指向（Object Oriented）言語です。オブジェクト指向とは、データと処理をオブジェクトとして表現することでプログラムを構成していく考え方のことです。

C言語は、「処理」に着目し、数値や文字列、配列といったかんたんなデータを受け渡しつつ処理が進んでいく、「手続き型」のプログラミングでした。一方、オブジェクト指向言語であるRubyでは、データと処理をひとまとめにした「オブジェクト(Object, モノ)」に着目し、プログラムをそれらオブジェクトたちの動きとして記述します。

また、Rubyでは、数値や文字列など基本的なデータ型を含め、すべてがオブジェクトして表現されます。

### Rubyは動的付けを行うな言語

プログラムでは、データを扱うために変数というものを定義していました。C言語では、変数を宣言する際には型を指定しなければいけませんし、一度型を決めて宣言した変数には別の方のデータを入れることができません。このような性質を、「静的型付け」といいます。

逆にRubyは、変数の型を予め宣言しておくことをせず、どの変数にどのような型のデータを入れてもかまわないようになっています。

### Rubyは簡潔に記述できる言語

先程軽くコードを書いて感じてもらったとおり、Rubyは、かんたんでわかりやすい記述ができる言語です。先程軽く書いたコードを見ただけでも、以下のような特徴を挙げることができます。

- 文末のセミコロン(;)がいらない
- 変数の宣言がいらない
- 変数の型宣言がいらない

まだまだ簡潔に記述できるポイントはありますが、ここでは省略します。