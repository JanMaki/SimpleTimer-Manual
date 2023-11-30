# BCDice-Kt

[BCDice]( https://github.com/bcdice/BCDice )をKotlinやJavaなどで使うためのライブラリ

JanMaki/bcdice-kt
: [https://bcdice-kt.simpletimer.dev/](https://bcdice-kt.simpletimer.dev/)


<procedure title="Gradle・Maven">
<a href="https://jitpack.io/#dev.simpletimer/bcdice-kt">
    <img src="https://jitpack.io/v/dev.simpletimer/bcdice-kt.svg" alt="Alt text" width="450"/>
</a>
<tabs group="repos">

<tab title="Gradle" group-key="gradle">
<code-block lang="gradle">
<![CDATA[
repositories {
    maven { url 'https://jitpack.io' }
}
　
dependencies {
    implementation 'dev.simpletimer:bcdice-kt:VERSION'
}
]]>
</code-block>
</tab>

<tab title="Maven" group-key="maven">
<code-block lang="xml">
<![CDATA[
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
<repositories>
　
<dependency>
    <groupId>dev.simpletimer</groupId>
    <artifactId>bcdice-kt</artifactId>
    <version>VERSION</version>
</dependency>
]]>
</code-block>
</tab>

</tabs>
</procedure>

<procedure title="Document">
<deflist>
    <def title="KDoc">
        <a href="https://doc.bcdice-kt.simpletimer.dev/">https://doc.bcdice-kt.simpletimer.dev/</a>
    </def>
</deflist>
</procedure>

<procedure title="Examples">

<procedure title="実行時の下準備">
<tabs group="example">
<tab title="Kotlin" group-key="Kotlin">
<code-block lang="kotlin">
<![CDATA[
val bcdice = BCDice()

//動作に必要なファイルがインストールされているかを確認
if (!bcdice.wasInstalled()) {
    //インストール
    bcdice.install()
}

//ゲームシステム読み込みなどのセットアップを行う
bcdice.setup()
]]>
</code-block>
</tab>
<tab title="Java" group-key="java">
<code-block lang="java">
<![CDATA[
BCDice bcdice = new BCDice();

//動作に必要なファイルがインストールされているかを確認
if(!bcdice.wasInstalled()){
    //インストール
    bcdice.install();
}

//ゲームシステム読み込みなどのセットアップを行う
bcdice.setup();
]]>
</code-block>
</tab>
</tabs>
</procedure>

<procedure title="ダイスロール">
<tabs group="example">
<tab title="Kotlin" group-key="Kotlin">
<code-block lang="kotlin">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//ゲームシステムを取得
val gameSystem = bcdice.getGameSystem("Cthulhu7th")

val result = gameSystem.roll("CC+1")
println(result.text) //結果のテキスト
]]>
</code-block>
</tab>
<tab title="Java" group-key="java">
<code-block lang="java">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//ゲームシステムを取得
GameSystem gameSystem = bcdice.getGameSystem("Cthulhu7th");

GameSystem.DiceResult result = gameSystem.roll("CC+1");
System.out.println(result.getText()); //結果のテキスト
]]>
</code-block>
</tab>
</tabs>
</procedure>

<procedure title="オリジナル表">
<tabs group="example">
<tab title="Kotlin" group-key="Kotlin">
<code-block lang="kotlin">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//テーブルのデータをテキストで作成
val text = """
    飲み物表
    1D6
    1:水
    2:緑茶
    3:麦茶
    4:コーラ
    5:オレンジジュース
    6:選ばれし者の知的飲料
""".trimIndent()

val result = bcdice.rollOriginalTable(text)
println(result.text) //結果のテキスト
]]>
</code-block>
<br/>
<code-block lang="kotlin">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//テーブルのデータをTableDataとして作成
val tableData = OriginalTable.TableData(
    "飲み物表",
    "1D6",
    mapOf(
        1 to "水",
        2 to "緑茶",
        3 to "麦茶",
        4 to "コーラ",
        5 to "オレンジジュース",
        6 to "選ばれし者の知的飲料"
    )
)

val result = bcdice.rollOriginalTable(tableData)
println(result.text) //結果のテキスト
]]>
</code-block>
</tab>
<tab title="Java" group-key="java">
<code-block lang="java">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//テーブルのデータをテキストで作成
String text = """
    飲み物表
    1D6
    1:水
    2:緑茶
    3:麦茶
    4:コーラ
    5:オレンジジュース
    6:選ばれし者の知的飲料
""";

Result result = bcdice.rollOriginalTable(text);
System.out.println(result.getText()); //結果のテキスト
]]>
</code-block>
<br/>
<code-block lang="java">
<![CDATA[
/*
実行時の下準備をあらかじめ行う
 */


//テーブルのデータをTableDataとして作成
OriginalTable.TableData tableData = new OriginalTable.TableData(
    "飲み物表",
    "1D6",
    Map.of(
        1, "水",
        2, "緑茶",
        3, "麦茶",
        4, "コーラ",
        5, "オレンジジュース",
        6, "選ばれし者の知的飲料"
    )
);

//テーブルを作成
Result result = bcdice.rollOriginalTable(tableData);
System.out.println(result.getText()); //結果のテキスト
]]>
</code-block>
</tab>
</tabs>
</procedure>
</procedure>