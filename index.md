---
layout: default
title: 刑法犯罪構成要件アーカイブ
---

<div style="position: sticky; top: 0; background: #fff; padding: 10px; border-bottom: 2px solid #364e6d; z-index: 100; margin-bottom: 20px; display: flex; gap: 10px; align-items: center;">
    <span style="font-weight: bold; font-size: 0.9rem;">学習ツール:</span>
    <button onclick="toggleMask()" style="cursor: pointer; padding: 5px 10px; background: #364e6d; color: #fff; border: none; border-radius: 3px;">暗記モード切替</button>
    <small style="color: #666;">※青いセルをクリックすると答えが表示されます</small>
</div>

<style>
    /* 暗記モード用のスタイル */
    .mask { 
        background-color: #364e6d !important; 
        color: #364e6d !important; 
        transition: all 0.2s; 
        cursor: pointer;
    }
    .mask:active, .mask.show { 
        background-color: transparent !important; 
        color: inherit !important; 
    }
    section { margin-bottom: 80px; }
    .point-box { 
        background: #fdf2f2; 
        border: 1px solid #eec; 
        padding: 15px; 
        border-radius: 5px; 
        margin-top: 15px;
    }
    .point-title { font-weight: bold; color: #c0392b; margin-bottom: 5px; display: block; }
</style>

<script>
    // 暗記モードの切り替え
    function toggleMask() {
        document.querySelectorAll('.spec-table td').forEach(td => {
            td.classList.toggle('mask');
        });
    }
    // 個別クリックで表示
    document.addEventListener('click', function(e) {
        if (e.target.classList.contains('mask')) {
            e.target.classList.toggle('show');
        }
    });
</script>

{% for crime in site.data.crimes %}
<section id="{{ crime.id }}">
    <div class="page-header">
        <div class="breadcrumb">{{ crime.category_main }} > {{ crime.category_sub }} > 第{{ crime.chapter }}章</div>
        <h1 style="margin: 0;">{{ crime.title }}</h1>
        <p style="font-size: 0.8rem; color: #72777d;">出典: <a href="{{ crime.source_url }}" target="_blank">Wikipedia</a></p>
    </div>

    <h3>1. 基本構成要件</h3>
    <div class="table-wrapper">
        <table class="spec-table">
            <tr><th>条文番号</th><td>刑法{{ crime.article }}</td></tr>
            <tr><th>保護法益</th><td>{{ crime.benefit }}</td></tr>
            <tr><th>主体</th><td>{{ crime.subject }}</td></tr>
            <tr><th>客体</th><td>{{ crime.object }}</td></tr>
            <tr><th>実行行為</th><td>{{ crime.act }}</td></tr>
            <tr><th>主観</th><td>{{ crime.intent }}（刑法38条参照）</td></tr>
            <tr><th>結果</th><td>{{ crime.result }}</td></tr>
        </table>
    </div>

    <h3>2. 実行のプロセス</h3>
    <div class="table-wrapper">
        <table class="spec-table">
            <tr><th>実行の着手</th><td>{{ crime.start }}</td></tr>
            <tr><th>既遂時期</th><td>{{ crime.completed }}</td></tr>
        </table>
    </div>

    <h3>3. 未遂・予備</h3>
    <div class="table-wrapper">
        <table class="spec-table">
            <tr><th>未遂罪</th><td><span class="status-tag">{{ crime.attempt }}</span></td></tr>
            <tr><th>予備罪</th><td><span class="status-tag">{{ crime.preparation }}</span></td></tr>
        </table>
    </div>

    {% if crime.points %}
    <div class="point-box">
        <span class="point-title">学習のポイント・重要論点</span>
        <ul style="font-size: 0.9rem; margin: 0; padding-left: 20px;">
            {% for point in crime.points %}
            <li>{{ point }}</li>
            {% endfor %}
        </ul>
    </div>
    {% endif %}
</section>
{% endfor %}

---
[Image of the structure of a criminal offense in Japanese law]
---
<footer>
    <p>参照: <a href="https://ja.wikipedia.org/wiki/%E6%AE%BA%E4%BA%BA%E7%BD%AA_(%E6%97%A5%E6%9C%AC)" target="_blank">Wikipedia 殺人罪 (日本)</a></p>
</footer>
