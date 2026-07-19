> 🧭 [📘本体](./body.md)｜[✏️演習](./exercises.md)｜[✅解答](./answers.md)｜[🏠目次](../INDEX.md)

# トピック3：演習（問題のみ）

対象：文字列 S が回文かどうかを、先頭と末尾を対にして判定する。

## ③トレース演習（i を 1 から n÷2 まで、S[i] と S[n−i+1] を比較）

第1問（基本） S = "LEVEL"（n = 5）

| i | S[i] | S[n−i+1] | 一致? | kaibun |
|---|------|----------|-------|--------|
| 1 |      |          |       |        |
| 2 |      |          |       |        |

第2問（境界値：偶数長＋非回文） S = "ABCA"（n = 4）

| i | S[i] | S[n−i+1] | 一致? | kaibun |
|---|------|----------|-------|--------|
| 1 |      |          |       |        |
| 2 |      |          |       |        |

🗣️ OUTPUT：トレース後、「この処理が何をしているか」を3文で説明せよ（どこで打ち切ってよいかにも触れる）。

## ④デバッグ演習

第1問（境界バグ）回文判定のつもり。実行するとどうなる？

    s = "LEVEL"
    n = len(s)
    kaibun = True
    for i in range(n):
        if s[i] != s[n - i]:
            kaibun = False
    print(kaibun)

第2問（照合バグ）text の中に pat があるか。なぜ常に True になる？

    text = "AAB"; pat = "XY"
    found = False
    for i in range(len(text) - len(pat) + 1):
        match = True
        for j in range(len(pat)):
            if text[i + j] != pat[j]:
                match = True
        if match:
            found = True
    print(found)
