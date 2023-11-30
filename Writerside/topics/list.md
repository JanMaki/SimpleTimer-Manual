# 一覧機能
あらかじめタイマー・ダイスの一覧を作成して、プルダウンのメニューからタイマーを選択・実行できるようにする機能です。
<procedure title="一覧の表示">
    <list type="decimal" start="1">
        <li>
            <p><a href="cmd_list-show.md">/list show</a>で一覧機能のメインの画面が表示します。</p>
        </li>
        <li>
            <p>一覧の下に設置されるプルダウンから要素名を選択することによってタイマーやダイスが実行されます。</p>
        </li>
    </list>
</procedure>
<procedure title="一覧へ要素を追加">
    <list>
        <li><a href="cmd_list-add-timer.md">/list addtimer</a>でタイマーを一覧に追加できます。</li>
        <li><a href="cmd_list-add-dice.md">/list adddice</a>でダイスを一覧に追加できます。</li>
    </list>
</procedure>
<procedure title="実行チャンネルの変更">
    <p><a href="cmd_list-target.md">/list target</a>で一覧を実行するチャンネルを変更できます。</p>
    <tip>
        <p>初期状態では、一覧と同じチャンネルでタイマー・ダイスが実行されます。</p>
    </tip>
</procedure>
<procedure title="一覧からタの削除">
    <list>
        <li><a href="cmd_list-remove.md">/list remove</a>で要素を指定して一覧から削除できます。</li>
        <li><a href="cmd_list-clear.md">/list clear</a>で一覧から要素をすべて削除します。</li>
    </list>
</procedure>
<procedure title="一覧の同期・コピー">

<procedure title="同期">
<p>
    同期は、サーバーの一覧を他のサーバーに同期させる機能です。<br/>
    <a href="cmd_list-sync.md">/list sync</a>を使うと、同期が開始されます。<br/>
    同期元のサーバーで一覧への追加や削除が行われると、同期されているサーバーの一覧も更新されます。<br/>
</p>
<warning>
    <p>同期元のサーバーが削除された場合、一覧も削除されます。</p>
</warning>
</procedure>

<procedure title="コピー">
<p>
    コピーは、サーバーの一覧を他のサーバーからコピーする機能です。<br/>
    <a href="cmd_list-copy.md">/list copy</a>を使うと、一覧がコピーされます。<br/>
    同期と違い、コピー元のサーバーで一覧への追加や削除が行われても、コピーしたサーバーには影響がありません。<br/>
</p>
</procedure>

<procedure title="IDの取得">
<p>同期やコピーに用いるIDは<a href="cmd_list-id.md">/list id</a>を行うことで取得できます。</p>
</procedure>

</procedure>
