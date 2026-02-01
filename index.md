---
layout: default
title: 殺人罪 構成要件ノート
---

{% for crime in site.data.crimes %}
<section id="{{ crime.id }}">
    <div class="page-header">
        <div class="breadcrumb">{{ crime.category_main }} > {{ crime.category_sub }} > 第{{ crime.chapter }}章</div>
        <h1 style="margin: 0;">{{ crime.title }}</h1>
        <p style="font-size: 0.9rem; color: #72777d;">出典: <a href="{{ crime.source_url }}" target="_blank">Wikipedia</a></p>
    </div>

    <h3>基本構成要件</h3>
    <table class="spec-table">
        <tr><th>条文番号</th><td>刑法{{ crime.article }}</td></tr>
        <tr><th>保護法益</th><td>{{ crime.benefit }}</td></tr>
        <tr><th>主体</th><td>{{ crime.subject }}</td></tr>
        <tr><th>客体</th><td>{{ crime.object }}</td></tr>
        <tr><th>実行行為</th><td>{{ crime.act }}</td></tr>
        <tr><th>主観</th><td>{{ crime.intent }}</td></tr>
        <tr><th>結果</th><td>{{ crime.result }}</td></tr>
    </table>

    <h3>実行のプロセス</h3>
    <table class="spec-table">
        <tr><th>実行の着手</th><td>{{ crime.start }}</td></tr>
        <tr><th>既遂時期</th><td>{{ crime.completed }}</td></tr>
    </table>

    <h3>刑罰規定の有無</h3>
    <table class="spec-table">
        <tr><th>未遂罪</th><td><span class="status-tag">{{ crime.attempt }}</span></td></tr>
        <tr><th>予備罪</th><td><span class="status-tag">{{ crime.preparation }}</span></td></tr>
    </table>
</section>
{% endfor %}

<footer>
    <p>参照URL: <a href="https://ja.wikipedia.org/wiki/%E6%AE%BA%E4%BA%BA%E7%BD%AA_(%E6%97%A5%E6%9C%AC)" target="_blank">Wikipedia 殺人罪 (日本)</a></p>
</footer>