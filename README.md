# PlainStorm

PlainStorm は、まだ形の決まっていない案や判断を、目的・制約・成功条件・次に確かめることへ整理するための会話スキルです。未解決の種類に応じて、Light、Deep Grill、Blindspot/Research、Options/Prototype、evidence-driven re-entry のいずれかを選びます。

## まず使う

インストール後の Codex CLI または IDE で `$plainstorm` を明示してから、相談内容を書きます。例えば次のように始めます。

```text
$plainstorm
この案を整理したいです。目的は利用者の継続利用で、対象と成功条件がまだ決まっていません。
```

スキル名を直接選べる環境では、`/skills` から PlainStorm を選ぶか、ChatGPT デスクトップでは `@` で選択できます。詳しい依頼例は [使い方ガイド](docs/usage.md) を参照してください。

## インストール

### 推奨：組み込みの skill-installer

組み込みの `$skill-installer` を呼び出し、次のスキル URL を渡します。

```text
$skill-installer https://github.com/rasokiwayami/plainstorm/tree/main/skills/plainstorm
```

このリポジトリのルートではなく、`skills/plainstorm/` フォルダーだけがインストール対象です。インストーラーが既存の同名フォルダーを検出したら、上書きせずに停止してください。

### 手動コピー

同じ名前のコピーを複数の場所へ置かず、利用するスキル領域を一つ選びます。公式のユーザー領域は `$HOME/.agents/skills`、リポジトリ単位の領域は対象リポジトリの `.agents/skills` です。`skill-installer` では `$CODEX_HOME/skills`（未設定なら通常 `~/.codex/skills`）も使用されます。

既存ターゲットを保護するため、コピー前に存在を確認します。

```sh
git clone https://github.com/rasokiwayami/plainstorm.git
cd plainstorm

SKILL_ROOT="$HOME/.agents/skills"
TARGET="$SKILL_ROOT/plainstorm"

if [ -e "$TARGET" ] || [ -L "$TARGET" ]; then
  printf '%s\n' "既存の $TARGET を保持します。新規コピーを中止しました。"
  exit 1
fi

mkdir -p "$SKILL_ROOT"
cp -R skills/plainstorm "$TARGET"
```

`$CODEX_HOME/skills` を選ぶ場合は、`SKILL_ROOT` をその場所へ変更してください。公式のローカルスキル探索場所と更新時の再起動については、[Build skills](https://learn.chatgpt.com/docs/build-skills) を参照してください。

## 更新と削除

### 更新

1. 現在使っているスキル領域を一つ特定し、`plainstorm` フォルダーが存在するか確認します。
2. 既存フォルダーがある場合は新規インストールを繰り返さず、そのフォルダーだけを更新対象にします。ローカル変更を残したい場合は先に別の場所へ退避し、リポジトリの `skills/plainstorm/` の内容で対象フォルダーを置き換えます。
3. 隣接するスキルや別の設定は変更しません。更新が表示されない場合は Codex を再起動します。

更新対象は選んだ `plainstorm` フォルダーだけです。別の場所にも同名コピーを作らないでください。

### 削除

使用中のスキル領域を確認してから、その領域にある `plainstorm` フォルダーだけを削除します。リポジトリや他のスキルは削除対象ではありません。

## 依頼の例

```text
PlainStormを使って、この案の重要な未決定事項と次に確かめることを短く整理して。
```

```text
PlainStormを使って、反対意見や代替案を含め、判断を変え得る分岐を掘り下げて。
```

```text
PlainStormを使って、確認できる事実を調べ、事実と私が決めることを分けて。
```

```text
PlainStormを使って、言葉にしにくい見た目の好みを比べたい。違いが分かる二つの方向性を提案して。
```

試作を頼むときは、対象・形式・個数・比較したい観察点を明示します。例えば「A案とB案を静的な画面1枚ずつ、ローカルに作り、情報の見つけやすさを比べる」と指定します。明示的に選んだ範囲だけを、ローカル・可逆・一時的に試します。

相談の進め方、途中で止める方法、試した結果からの再開は [使い方ガイド](docs/usage.md) にまとめています。

## 境界

PlainStorm は、デバッグ、コードレビュー、すでに確定した仕様の実装を自動的に引き受けるためのルートではありません。外部への送信、フォーム入力、認証情報、支払い、公開、デプロイなどの権限を追加せず、試作も選択されたローカル範囲に限ります。状態保存は任意で、会話または短い再開メモだけで続けることもできます。

このフォルダーにはランタイム、プラグイン、インストーラー、テレメトリー、テスト実行基盤は含まれません。

## ファイルと帰属

- [スキル本体](skills/plainstorm/SKILL.md)
- [スキルのライセンス通知](skills/plainstorm/LICENSE.superpowers)
- [第三者通知](THIRD_PARTY_NOTICES.md)
- [使い方ガイド](docs/usage.md)
- [GitHub リポジトリ](https://github.com/rasokiwayami/plainstorm)

Superpowers の MIT 通知と、概念上の参照元は [第三者通知](THIRD_PARTY_NOTICES.md) に記載しています。
