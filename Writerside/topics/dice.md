# ダイス機能
SimpleTimerには、副次的な機能としてこのダイス機能があります。

基本的なコマンド
: [/roll](cmd_roll.md)でダイスを振ることができます。

<procedure title="構文" collapsible="true">
<p>コマンドなどで使用するダイスは構文に沿って記述されます。</p>
<procedure title="xDy"  collapsible="true">
<p>最も基本的な構文で、ダイスの個数と面の数を表しています。</p>
<deflist style="narrow">
    <def title="x">ダイスの個数</def>
    <def title="y">面の数</def>
</deflist>
<p>例：</p>

| 内容    | 意味         |
|-------|------------|
| 1d100 | 100面ダイスを1個 |
| 2d10  | 10面ダイスを2個  |
</procedure>
<procedure title="加算" collapsible="true">
<p>数値やダイスの出目の加算できます。</p>

| 演算子 | 条件     |
|-----|--------|
| a+b | aとbを足す |
</procedure>
<procedure title="比較演算子" collapsible="true">
<p>条件が一致したとき、ダイスの結果が<code>成功</code>となります。</p>

| 演算子  | 条件       |
|------|----------|
| a=b  | aとbが同じ   |
| a>b  | aがbより大きい |
| a<b  | aがbより小さい |
| a>=b | aがb以上    |
| a<=b | aがb以下    |
</procedure>
<procedure title="コメント" collapsible="true">
<p>ダイスの構文の後にスペースを入れると、その後に書かれている文章は無視されます。</p>
</procedure>
<procedure title="シークレットダイス" collapsible="true">
<p>ダイスの構文の先頭に<code>s</code>を入れるか<code>||</code>で囲うと、結果が隠されてダイスが実行されます。</p>
<p>例：</p>
<list>
    <li>s1d100</li>
    <li>||1d100||</li>
</list>
</procedure>
</procedure>

<procedure title="ダイスシステムの種類" collapsible="true">
<p>ダイスシステムは<a href="cmd_dice-mode.md">/dice mode</a>で切り替えることができます。</p>
<procedure title="SimpleTimer標準ダイス">
<p>
SimpleTimerにて独自に実装されているダイスです。<br/>
BCDiceよりも早く実行されます。
</p>
</procedure>
<procedure title="BCDice">
<p>BCDiceは、ココフォリアなどでも使われているダイスシステムです。</p>
<deflist>
    <def title="BCDice">
        <a href="https://bcdice.org/">https://bcdice.org/</a>
    </def>
</deflist>
<p><a href="cmd-dice-bot.md">/dice bot</a>用いることで、BCDiceに実装されている100を超えるゲームシステムの中から使用するダイスを変更できます。</p>
</procedure>
</procedure>