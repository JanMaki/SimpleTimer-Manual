# FanboxSupporterApi-Kt

[pixivFANBOX](https://www.fanbox.cc/)の支援情報を取得するライブラリ

JanMaki/FanboxSupporterApi-Kt
: [https://github.com/JanMaki/FanboxSupporterApi-Kt](https://github.com/JanMaki/FanboxSupporterApi-Kt)


<procedure title="Gradle">
<a href="https://jitpack.io/#JanMaki/FanboxSupporterApi-Kt">
    <img src="https://jitpack.io/v/JanMaki/FanboxSupporterApi-Kt.svg" alt="Alt text" width="450"/>
</a>
<tabs group="repos">

<tab title="Gradle" group-key="gradle">
<code-block lang="gradle">
repositories {
    maven { url 'https://jitpack.io' }
}
　
dependencies {
    implementation 'com.github.JanMaki:FanboxSupporterApi-Kt:VERSION'
}
</code-block>
</tab>

<!--
<tab title="Maven" group-key="maven">
<code-block lang="xml">
&lt;repositories&gt;
    &lt;repository&gt;
        &lt;id>jitpack.io&lt;/id&gt;
        &lt;url>https://jitpack.io&lt;/url&gt;
    &lt;/repository&gt;
&lt;repositories&gt;
　
&lt;dependency&gt;
    &lt;groupId>com.github.JanMaki&lt;/groupId&gt;
    &lt;artifactId>FanboxSupporterApi-Kt&lt;/artifactId&gt;
    &lt;version>VERSION&lt;/version&gt;
&lt;/dependency&gt;
</code-block>
</tab>
-->

</tabs>
</procedure>

<procedure title="Examples">
<procedure title="現在支援中のユーザーを取得">
<code-block lang="kotlin">
//支援者を取得
val fans = ListFans.getListFans(StatusType.SUPPORTER)
<br/>
println(fans.joinToString(", ") { "${it.user.name}:${it.user.userId}" })
</code-block>
</procedure>
<procedure title="過去の月ごとの支援者を取得">
<code-block lang="kotlin">
//支援金管理の情報を取得する
val payoutRequest = PayoutRequest.getPayoutRequest()
<br/>
//各月の情報を取得
payoutRequest?.monthlyMaxPayoutRequestAmountHistory?.forEach {
    //"年-月"の文字列を取得
    val month = it.targetMonth.convertTo(FanboxDate.FormatType.MONTH)
    <br/>
    println(month)
    <br/>
    //月のデータの詳細を取得
    val monthlyData = Monthly.getMonthly(it.targetMonth) ?: return@forEach
    //支援者の一覧を取得
    val supporters = monthlyData.supportTransactions.map { monthly -> monthly.supporter }
    <br/>
    println(supporters.joinToString(", ") { supporter -> "${supporter.name}:${supporter.userId}" })
}
</code-block>
</procedure>
</procedure>