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
      });
    });
  });
});
</script>

# 作問したCTF

- DifficultyはLiveで出したものはTSG CTF換算のものに変えています。
- Difficultyは事後評価のものに変更しています。
- Difficultyは非想定解の難易度を考慮しないものとしました。

## TSG CTF

### [TSG CTF 2023](https://github.com/tsg-ut/tsgctf2023)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|beginners_rev_2023|Reversing|beginner med|2|4|5|
|mimetic_cycle|Reversing|med-hard|5|2|5|

### [TSG CTF 2024](https://github.com/tsg-ut/tsgctf2024)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|piercing_misty_mountain|Pwnable|med|4|3|1|
|FL_Support_Center|Pwnable|med-hard|5|4|2|
|TSGDBinary|Reversing|med|3|3|4|
|prime shellcode|Misc|med|3|3|4|

## TSG Live CTF

### [TSG LIVE! 7 CTF](https://github.com/tsg-ut/tsg-live-ctf-7)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|Powered Evil Online|Reversing|beginner easy|2|2|4|

### [TSG LIVE! 8 CTF](https://github.com/tsg-ut/tsg-live-ctf-8)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|DNS ROPOB|Reversing|easy-med|5|4|1|

### [TSG LIVE! 10 CTF](https://github.com/tsg-ut/tsg-live-ctf-10)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|agent|Pwnable|beginner|0|4|5|
|renewal|Pwnable|easy|0|4|5|
|true_version|Pwnable|easy-med|4|5|5|
|string_related|Reversing|beginner|2|3|5|

### [TSG LIVE! 11 CTF](https://github.com/tsg-ut/tsg-live-ctf-11)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|mini_cyberchef|Pwnable|beginner|0|4|5|
|mini_cyberchef_production|Pwnable|med|5|5|5|
|power_obfus_royalty|Reversing|beginner|2|3|5|

### [TSG LIVE! 14 CTF](https://github.com/tsg-ut/tsg-live-ctf-14)

|Challenge|Genre|Difficulty|Concept|Quality|Intended|
|:--------|-----|:--------:|:-----:|:-----:|:--------:|
|traditional_fork_chall|Pwnable|beginner easy|0|4|5|
|traditional_fork_chall_v2|Pwnable|easy|0|4|5|
|traditional_fork_chall_v3|Pwnable|med|3|5|5|
|perling_perler|Web|beginner|1|3|5|
|shornm|Web|beginner easy|2|3|2|
|iwi_deco_demo|Web|easy|3|3|3|
|string_related_js|Reversing|beginner|2|3|5|
|process_hopping|Reversing|beginner easy|4|4|5|
