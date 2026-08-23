README.md


CAWELON — Provisional Draft
Status: Draft / Not audited / Not deployed
Intended network: Ethereum Mainnet
Maintainer: 0628DAO

CAWELONの再始動に向けた、ERC-20スマートコントラクトとdApp構成の暫定公開資料です。CAWELONは、0628DAOエコシステムにおける 0628DEX（Liquidity Layer／資産交換） の基盤トークンとして設計を進めています。

このリポジトリは、デプロイ前の設計・検証過程を透明化するために公開しています。現在掲載しているコードは監査前のドラフトであり、稼働中のトークンや販売中の商品を示すものではありません。

現在の暫定仕様
項目	内容
Token Name	CAWELON（予定）
Symbol	未確定（コンストラクタ引数）
規格	Ethereum ERC-20
初期発行量	420,000,000,000,000 tokens
Decimals	18
Transfer / Buy / Sell TAX	0%
Rewards / Reflection	なし
追加Mint	なし
Burn	保有者本人による自己Burnのみ
Permit	EIP-2612対応
Owner / Admin / Pause / Upgrade / Proxy	なし
Token NameはCAWELONを維持する方針です。Symbolと初期受取ウォレットはCAWから機械的に流用せず、デプロイ前に正式決定します。現在のコードでは最終確認に対応できるよう、Token NameとSymbolをコンストラクタ引数にしています。

0628DAOにおける位置付け
0628DAOはトークン名ではなく、複数の専門知性と人間の最終責任を組み合わせるガバナンス構想です。CAWELONはその統治対象の一つであり、0628DAOそのものではありません。

本リポジトリに含まれるのはCAWELONの基礎トークンとdApp接続方針です。0628DEX本体、流動性管理、フロントエンドおよびガバナンス執行機構は、別コントラクト・別工程として設計、検証、公開します。

設計方針
トークン本体は標準的で小さなERC-20実装に保つ

dApp固有の機能は別のプロトコルコントラクトへ分離する

dAppからは IERC20 / IERC20Permit として接続する

トークン移動にはOpenZeppelin SafeERC20 の利用を前提とする

TAX、Reflection、自動分配、DEXペア判定をトークン本体へ埋め込まない

後発Mint経路を設けない

この分離により、将来dAppを追加してもトークン本体を再発行せず、機能単位で検証・監査・更新方針を設計できます。

リポジトリの内容
CAWELON_Draft.sol — 暫定ERC-20スマートコントラクト

CAWELONDraft.txt — dApp対応方針とデプロイ前の検討事項

デプロイ前に確定・実施する事項
正式なToken NameとSymbol

初期発行分の受取ウォレット

制限機能を本体またはdApp側のどちらへ置くか

ERC20Votes 採用の要否

テストコードとテストネット検証

第三者によるセキュリティ監査

正式なデプロイアドレスの公開

重要事項
本コードは監査前・未デプロイです。

現時点で公式コントラクトアドレスはありません。

本リポジトリは、トークンの販売、投資勧誘、利益または価格上昇の保証を目的とするものではありません。

ウォレット接続や送金を行う前に、将来公式に告知されるネットワークとコントラクトアドレスを必ず照合してください。

仕様は検証・監査・法務確認の結果により変更される場合があります。

English summary
This repository contains a provisional Ethereum ERC-20 contract and a separated dApp architecture for CAWELON, intended as the base token for the 0628DEX Liquidity Layer. The draft uses a fixed initial supply, 18 decimals, 0% transfer/buy/sell tax, no rewards or reflection, no later minting, self-burn only, and EIP-2612 Permit. The CAWELON name is intended to remain; the symbol and initial recipient are not finalized. The code has not been audited or deployed and is not an offer or promise of returns.

© 0628DAO. Development record for technical review.
