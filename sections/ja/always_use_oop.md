# 常にオブジェクト指向プログラミングを使うこと #

> オブジェクト指向言語の問題は、これらの暗黙の環境をすべて持ち歩いていることです。あなたはバナナを欲しましたが、あなたが得たものはバナナを抱えたゴリラとジャングル全体でした。
>
> -- ジョー・アームストロング in [Coders at work - Reflections on the Craft of Programming](http://codersatwork.com/)

> 抽象化は強力ですね。私が本当にアレルギーを持つもの、そして 90 年代に反応したのは、ありとあらゆる CORBA、COM、DCOM、オブジェクト指向ナンセンスでした。当時のスタートアップには、起動して "Hello world" を印刷するために 200,000 回のメソッド呼び出しが必要だといった、なんだか狂ったことがありました。残念です! その種のことに関わるプログラマーになりたくはないですよね。
>
> -- ブレンダン・アイク in [Coders at work - Reflections on the Craft of Programming](http://codersatwork.com/)

今日、多くのソフトウェア開発者や多くの企業は、オブジェクト指向プログラミングだけが、ソフトウェアを開発する合理的な方法だと感じています。オブジェクト指向プログラミングに反対する人は、彼らが業界の「伝統的な知性」に反対しているんじゃないかと、すぐに萎縮してしまいます。

プログラミングのブログやフォーラムでは、とても多くの人がオブジェクト指向プログラミングを擁護し、何について話しているか自分でわかっていると確信しています。標準の定義が不足しているにもかかわらずですよ!

実際のところ、オブジェクト指向プログラミングと呼ばれるようなものは、しばしば不必要な複雑さの重い負担を強います。

コンピュータ科学者やプログラマとして、私たちは、こだわりを脇において、与えられた問題に対する最良の解決策を見つける、ということを学ぶ必要があります。

今日、PHP の主な強みのひとつは、命令型、関数型、オブジェクト指向、手続き型、およびリフレクティブの全パラダイムのサポートです。PHP はさまざまなツールを備えた巨大なツールボックスであり、さまざまな方法で多くの問題を解決することができます - **たったひとつの方法ではなく!**

**アプリケーション内のさまざまな問題を単一の特定のプログラミングパラダイムに強制しようとすると、あっという間に、私たちは創造的に思考しなくなり、効率的に作業しなくなります !**

## ちょっと歴史の授業 ##

特定のプログラミングパラダイムを理解するのに良い方法のひとつは、それが最初にどのように進化したかに着目することです。その開発の理由は何? 新しい考え方が必要だった他のプログラミングパラダイムには、どんな問題があった? それは現実世界の問題か単に学問的な問題だったか? そして以来どのように進化してきたか?

X という人が何を言っているのか、Y という人が何を定義しているのかは関係ありません。パラダイムの中で重要なのは、それらを作った歴史です。

> ソフトウェア設計を構築するには、2 つの方法があります。ひとつの方法は、シンプルにすることで、明らかに欠点がないようにすることです。そしてもう一つの方法は、非常に複雑にして、明らかな欠陥がないようにすることです。
>
> -- [C.A.R. ホーア](https://en.wikiquote.org/wiki/C._A._R._Hoare)

かつて、オブジェクト指向プログラミングの登場以前、50 年代の終わり頃、多くのソフトウェアは、第 1 世代および第 2 世代の言語と呼ばれる、しいて言えば非構造化プログラミングと言われるプログラミング言語を使用して、開発されました。非構造化プログラミング (または構造化なしプログラミング) は、歴史上最も初期のプログラミングパラダイムです。それは「スパゲッティ」コードを作成すると強く批判されました。

非構造化プログラミングを使用する言語には、高レベルなものも低レベルなものもあります。これらには、初期バージョンの BASIC、COBOL、MUMPS、JOSS、FOCAL、TELCOMP、機械語、初期アセンブラシステム (プロシージャー疑似命令のないもの)、およびいくらかのスクリプト言語が含まれます。

非構造化言語のプログラムは、通常は各行に1つずつの順番に並んだ命令あるいはステートメントで、通常構成されます。行は通常、番号付けされるかラベルを持ち、実行フローがプログラム内の任意の行に (不人気な GOTO 文のように) ジャンプできるようになっています。

そして、60 年代には、構造化プログラミングが浮上しました - 主に、エドガー・W・ダイクストラ の有名な手紙 [Go To statements considered harmful](http://www.u.arizona.edu/~rubinson/copyright_violations/Go_To_Considered_Harmful.html) のおかげで。

後に、手続き型プログラミングが構造化プログラミングから派生しました。手続き型プログラミングは「プロシージャ呼び出し」という概念に基づいています。「プロシージャ呼び出し」は、単に「関数呼び出し」の別名です。プロシージャは、ルーチン、サブルーチンまたはメソッドとも呼ばれます。プロシージャは、一連の計算ステップを含んでいるにすぎません。定義された任意のプロシージャは、他のプロシージャまたはそれ自体を含み、プログラムの実行中の任意の時点で呼び出されます。

最初は、すべてのプロシージャがプログラムのどの部分でもグローバルデータとして利用可能でした。これは小さなプログラムでは問題はありませんが、状況が複雑になり、プログラムのサイズが成長すると、プログラムの一部の小さな変更が、他の多くの部分に大きく影響しました。

誰もプログラムの変更を計画しておらず、多くの依存関係が存在していました。ひとつのプロシージャへの小さな変更が、元のコードに依存する他の多くのプロシージャで、エラーのカスケードを発生させます。

新しい技術は、データを「オブジェクト」と呼ばれる分離したスコープに分割することができるよう進化させました。同じスコープに属する特定のプロシージャだけが同じデータにアクセスできます。これは、データ隠蔽またはカプセル化と呼ばれます。その結果、より整理されたコードが得られました。

最初はオブジェクトがオブジェクトと呼ばれず、それらは別のスコープと見られました。後で依存関係が縮小され、これらのスコープ内のプロシージャーと変数の間の接続が分離されたセグメントと見られるようになって、その結果が「オブジェクト」および「オブジェクト指向プログラミング」という概念を生み出しました。

後に、主に Java の開発のために、ある「バズワード」が発生し、「プロシージャ」または「関数」はもはや関数と呼ばれなくなり、分離スコープ内に存在するときは「メソッド」に改名されました。変数はもはや「変数」と呼ばれなくなり、分離スコープ内に存在するときは「属性」に名前が変更されました。

なので、オブジェクトは本質的に、単なる関数と変数の集合が現在「メソッドと属性」と呼ばれるようになっただけです。

メソッドと属性を分離スコープの中に隔離して保持する方法とは、「クラス」を使うことです。クラスは、インスタンス化されると、オブジェクトと呼ばれます。

オブジェクトはお互いを参照することができ、そのような参照によって、中にあるメソッド (関数) は互いに「通信」することができます。オブジェクトは他のオブジェクトからメソッドを「継承して」拡張することもでき、これは「インヘリタンス」と呼ばれます。これは、コードを再利用し、パブリッククラスとインタフェースを介して、ソフトウェアの独立した拡張を可能にする方法です。オブジェクトの関係によって階層が生じます。継承は 1967 年にプログラミング言語 [Simula 67](http://en.wikipedia.org/wiki/Simula) のために発明されました。

オブジェクトは、他のオブジェクトからメソッドを継承し、追加または変更された機能でこれらを「オーバーライド」することもできます。これは「ポリモーフィズム」と呼ばれます。

これらのさまざまなアイデアがどのように実装されているかは、プログラミング言語のピンからキリまでで大きく異なります。

オブジェクト指向プログラミングとは、これまでとは別の方法でコードを整理することです。それは手続き型プログラミングの拡張であり、データの隠蔽 (カプセル化) とグローバルスコープを回避することです。実際には元のコードに影響を与えずに青写真の「借用」によって機能を拡張すること (インヘリタンス) です。そして、元のコードに影響を与えずに関数をオーバーライドすること (ポリモーフィズム) です。

> オブジェクト指向モデルは付け加えによってプログラムの構築を簡単にします。実際には、多くの場合、スパゲッティコードを書くための構造的手法を提供するという意味なのですが。
>
> -- ポール・グレアム in [Ansi Common Lisp](https://openlibrary.org/works/OL7944696W/ANSI_Common_Lisp)

**間違った方法**: 常にオブジェクト指向プログラミングを使うこと。 ![だめ](/img/thumbs-down.png)