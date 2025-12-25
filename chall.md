---
title: CTFの作問歴
layout: default
---

<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-JFPTPL2QDM"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-JFPTPL2QDM');
</script>

<script>
document.addEventListener('DOMContentLoaded', () => {
  const tables = document.querySelectorAll('table');
  if (!tables.length) return;

  tables.forEach(table => {

    table.style.borderCollapse = 'collapse';
    table.style.width = '100%';

    const cells = table.querySelectorAll('th, td');
    cells.forEach(cell => {
      cell.style.borderTop = '1px solid #d0d7de';
      cell.style.borderBottom = '1px solid #d0d7de';
      cell.style.padding = '6px 10px';
      cell.style.textAlign = cell.tagName === 'TH' ? 'left' : '';
    });

    const headers = Array.from(table.querySelectorAll('tr:first-child th, thead th'));
    const targetCols = headers
      .map((th, i) => /^(concept|quality|intended)$/i.test(th.textContent.trim()) ? i : -1)
      .filter(i => i >= 0);

    const rows = Array.from(table.querySelectorAll('tbody tr')).length
      ? Array.from(table.querySelectorAll('tbody tr'))
      : Array.from(table.querySelectorAll('tr')).slice(1);

    rows.forEach(tr => {
      targetCols.forEach(idx => {
        const td = tr.cells[idx];
        if (!td) return;
        const n = parseInt(td.textContent.trim(), 10);
        if (Number.isFinite(n)) {
          const clamped = Math.max(0, Math.min(5, n));
          if (clamped === 0) {
            td.textContent = '▽';
            td.style.color = '#555';
            td.style.textAlign = 'center';
            td.style.fontSize = '1.1em';
          } else {
            td.textContent = '★'.repeat(clamped) + '☆'.repeat(5 - clamped);
            td.style.whiteSpace = 'nowrap';
          }
        }
      });
    });
  });
});
</script>

# 作問したCTF

- DifficultyはLiveで出したものはTSG CTF換算のものに変えています。
- Difficultyは事後評価のものに変更しています。
- Difficultyは非想定解の難易度を考慮しないものとしました。
- Conceptの▽は下の問題とのシリーズものを表し、下のコンセプトの問題から
逆算して作られた難易度の問題を意味します。

## TSG CTF

### [TSG CTF 2023](https://github.com/tsg-ut/tsgctf2023)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|beginners_rev_2023|Reversing|beginner med|2|4|5|exeファイル, RC4, safe-linking|
|mimetic_cycle|Reversing|med-hard|5|2|5|powershellのaliasを用いた難読化, コンセプトに自信あり|

### [TSG CTF 2024](https://github.com/tsg-ut/tsgctf2024)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|piercing_misty_mountain|Pwnable|med-hard|4|3|1|`ret n`ガジェットの問題, 非想定によってのみ解かれて泣く|
|FL_Support_Center|Pwnable|med-hard|5|4|2|C++のheap問, 作問ミスにより簡単になってしまったのが悔やまれるが、面白い問題|
|TSGDBinary|Reversing|med|3|3|4|gdbを難読化に用いてもおかしくないという発想から|
|prime shellcode|Misc|med|3|3|4|素数でシェルコードを縛るという単純なコンセプト|

### TSG CTF 2025

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|pryspace|Pwnable|med-hard|5|5|3|N*Mのノートででかいunsorted binを作れるかパズル, 発想の新規性はある|
|XMLTreeDump|Pwnable|hard|5|5|4|C++のUAF heap問, 想定解も面白い|
|TSG-Book|Web|easy|3|2|1|ThymeleafのSSTI, 作問ミスにより悔いしか残らない出来に|
|shadow_spider_network|Reversing|easy-med|5|3|2|SEGV handlerの問題, もっと凝るよちはあったが、簡単のまま出してしまった|
|ro_shellbox|Misc|med|4|5|5|read onlyな領域ばかりのshellcode jail|

## TSG Live CTF

### [TSG LIVE! 7 CTF](https://github.com/tsg-ut/tsg-live-ctf-7)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|Powered Evil Online|Reversing|beginner easy|2|2|4|初めてのCTFの作問, 半分黒歴史|

### [TSG LIVE! 8 CTF](https://github.com/tsg-ut/tsg-live-ctf-8)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|DNS ROPOB|Reversing|easy-med|5|4|1|独自アイデアを含むROPOBの問題, アンチ動的解析を入れず一瞬で解かれる, コンセプトは好き|

### [TSG LIVE! 10 CTF](https://github.com/tsg-ut/tsg-live-ctf-10)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|agent|Pwnable|beginner|0|4|5||
|renewal|Pwnable|easy|0|4|5||
|true_version|Pwnable|easy-med|4|5|5|canaryをスキップする面白問題|
|string_related|Reversing|beginner|2|3|5|powershellのテクの勉強|

### [TSG LIVE! 11 CTF](https://github.com/tsg-ut/tsg-live-ctf-11)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|mini_cyberchef|Pwnable|beginner|0|4|5||
|mini_cyberchef_production|Pwnable|med|5|5|5|FSBの自然な利用の面白問題|
|power_obfus_royalty|Reversing|beginner|2|3|5|powershellのテクの勉強2|

### [TSG LIVE! 14 CTF](https://github.com/tsg-ut/tsg-live-ctf-14)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|内容|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|:--------|
|traditional_fork_chall|Pwnable|beginner easy|0|4|5||
|traditional_fork_chall_v2|Pwnable|easy|0|4|5||
|traditional_fork_chall_v3|Pwnable|med|3|5|5|forkの問題にガチャガチャ要素を足した。よくまとまっていると思う|
|perling_perler|Web|beginner|1|3|5|perlのコマンドインジェクション|
|shornm|Web|beginner easy|2|3|2|redirectに着目してみた問題, 非想定がいっぱい|
|iwi_deco_demo|Web|easy|3|3|3|ThymeleafのSSTIのブログからほぼそのまま|
|string_related_js|Reversing|beginner|2|3|5|javascriptの難読化の勉強|
|process_hopping|Reversing|beginner easy|4|4|5|forkを入れ子にしてみた|
