# 更新履歴 / Changes

## v1.1.0 (2026-10-21)

- ダッシュボードに［▲ 上げる］［▼ 下げる］（押すたびに 次の高さへ：床 → 0.20 m → 0.90 m → いちばん上）と［ホーン］を追加しました。スマホでも フォークとホーンが使えます。
- ダッシュボードのキーが VRChat で押せないことがあったのを直しました。デスクトップは クリックした所のキーを確実に押します。VR は 指で押すか、手から出る線を キーに当てて トリガーで押せます（線と 光るキーで 狙いが分かります）。1 回の操作が 2 回 押されることは ありません。
- デスクトップのホーンは H か B になりました（クリックは キーを押すため）。VR は キーを狙っていない時の トリガーが ホーンです。
- 乗ったまま 長く操作がない時に 降ろすタイマーを追加しました（はじめは 5 分、1 分前に知らせます。0 で 降ろしません）。
- 入力欄に文字を打っている間は キー操作が効かないように できます（Typing Fields）。Ctrl を押している間は ホーンが鳴りません。
- ほかの人から届いた 壊れた数値（NaN など）で フォークリフトやパレットが おかしくならないようにしました。
- 壁に押しつけている間や、フォークリフト・パレットが多い時の 計算を軽くしました。
- 乗っている間は 自分のフォークリフトの 乗るための当たり判定と Interact を 切るようにしました。

v1.0.0 から: そのまま上書きで読み込めます。シーンに置いた RARA_Forklift には 新しいキーが 自動で付きます（Unpack したものだけは 置き直してください）。

- New dash keys: [▲ Up] / [▼ Down] (each press moves the forks to the next stop: floor, 0.20 m, 0.90 m, the top) and [Horn]. Phones can now lift and honk.
- The dash keys press reliably in VRChat. Desktop: the key under the click is pressed even when VRChat's own Interact does not arrive. VR: press with a finger, or aim the line from your hand (a beam, a dot and a lit key show where) and pull the trigger. One press is never taken twice.
- The desktop horn is H or B (the click presses keys). VR: the trigger is the horn when no key is aimed at.
- Idle driver timer: a driver who does nothing for 5 minutes (default; warning a minute before; 0 = never) is taken out of the seat.
- Optional typing guard (Typing Fields); Ctrl + H / B does not honk.
- Broken synced values (NaN and the like) from another client can no longer upset a forklift or a pallet.
- Less work per frame while pushing against a wall and with many forklifts and pallets.
- While seated, your own forklift's boarding box and Interact are off.

From v1.0.0: import it over the old one. The RARA_Forklift prefabs in your scenes get the new keys by themselves (an unpacked one has to be placed again).

## v1.0.0 (2026-10-09)

- 最初の公開 / First release.
