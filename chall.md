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
    const headers = Array.from(table.querySelectorAll('tr:first-child th, thead th'));
    const targetCols = headers
      .map((th, i) => /^(difficulty|concept|quality)$/i.test(th.textContent.trim()) ? i : -1)
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
- Unintendedの項目は高いほどAs intendedだったとういうことです。

## TSG CTF

### [TSG CTF 2023](https://github.com/tsg-ut/tsgctf2023)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
|beginners_rev_2023|Reversing|beginner med|2|4|5|
- mimetic_cycle (Reversing)

### [TSG CTF 2024](https://github.com/tsg-ut/tsgctf2024)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
- piercing_misty_mountain (Pwnable)
- FL_Support_Center (Pwnable)
- TSGDBinary (Reversing)
- prime shellcode (Misc)

## TSG Live CTF

### [TSG LIVE! 7 CTF](https://github.com/tsg-ut/tsg-live-ctf-7)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
|Powered Evil Online|Reversing|beginner easy|2|2|4|

### [TSG LIVE! 8 CTF](https://github.com/tsg-ut/tsg-live-ctf-8)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
|DNS ROPOB|Reversing|easy-med|5|4|1|

### [TSG LIVE! 10 CTF](https://github.com/tsg-ut/tsg-live-ctf-10)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
- agent (Pwnable)
- renewal (Pwnable)
- true_version (Pwnable)
- string_related (Reversing)

### [TSG LIVE! 11 CTF](https://github.com/tsg-ut/tsg-live-ctf-11)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
- mini_cyberchef (Pwnable)
- mini_cyberchef_production (Pwnable)
- power_obfus_royalty (Reversing)

### [TSG LIVE! 14 CTF](https://github.com/tsg-ut/tsg-live-ctf-14)

|Challenge|Genre|Difficulty|Concept|Quality|Unintended|
|--------:|-----|:--------:|:-----:|:-----:|:--------:|
- traditional_fork_chall (Pwnable)
- traditional_fork_chall_v2 (Pwnable)
- traditional_fork_chall_v3 (Pwnable)
- perling_perler (Web)
- shornm (Web)
- iwi_deco_demo (Web)
- string_related_js (Reversing)
- process_hopping (Reversing)
