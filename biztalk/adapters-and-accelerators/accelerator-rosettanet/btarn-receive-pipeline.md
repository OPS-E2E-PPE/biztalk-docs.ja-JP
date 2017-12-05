---
title: "BTARN 受信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, receive pipelines
- RNMimeDecoder component
- ReceiveMessageNonRepudiate component
- RNDAsm component
- receive pipelines, message flow
- RNPartyRes component
- receive pipelines, BTARN
- MessageUpdater component
- messages, message flow
ms.assetid: 811f2a6a-ddd2-49cc-a00b-4c9d0110a0d1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4bc69348cfb99b5e7cebb07c65e05a0513cd0e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="btarn-receive-pipeline"></a>BTARN 受信パイプライン
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RosettaNet Implementation Framework (RNIF) メッセージの受信、RNIFReceive パイプライン (RNIFReceive.btp) を実行します。 受信パイプラインには、以下のコンポーネントが含まれます。  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (MIME プリプロセッサ/デコーダー)  
  
-   RNDAsm (XML 逆アセンブラ)  
  
-   RNPartyRes (Party Resolution コンポーネント)  
  
-   MessageUpdater  
  
## <a name="receivemessagenonrepudiate"></a>ReceiveMessageNonRepudiate  
 このコンポーネントは、受信メッセージを MessageStorageIn テーブルに保存します。 このコンポーネントは、RNIF 規格に必要な否認不可処理を実行します。  
  
## <a name="rnmimedecoder"></a>RNMimeDecoder  
 このコンポーネントは、上のネイティブ BizTalk Server MIME プリプロセッサ/デコーダーに基づいています。 RNMimeDecoder は、RNIF 処理のための以下の機能を備えています。  
  
-   RNIF 2.01 の場合、Service Content と添付ファイル (存在する場合) を暗号化解除します。  
  
-   RNIF 1.1 の場合、ペイロードの末尾にある 8 バイト ヘッダーとデタッチされた署名ヘッダーを処理します。  
  
 詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プリプロセッサ/デコーダー、BizTalk Server ヘルプの「MIME/SMIME デコーダー パイプライン コンポーネント」を参照してください。  
  
## <a name="rndasm"></a>RNDAsm  
 このコンポーネントは、ネイティブの BizTalk Server XML 逆アセンブラーに基づいています。 RNDAsm は、RNIF 処理のための以下の機能を備えています。  
  
-   受信ドキュメントに DOCTYPE ヘッダーがある場合、このコンポーネントはヘッダーから名前空間を生成し、受信ドキュメントのすべてのノードを名前空間に移動します。  
  
-   メッセージの相関を確認して、着信メッセージが重複しているかどうかを判断し、メッセージが重複している場合は、エラー メッセージを生成します。  
  
-   添付ファイルをメッセージの追加部分として保存します。  
  
-   メッセージ プロパティを昇格します。  
  
 詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]逆アセンブラー、BizTalk Server ヘルプの「XML 逆アセンブラー パイプライン コンポーネント」を参照してください。  
  
## <a name="rnpartyres"></a>RNPartyRes  
 このコンポーネントは、ネイティブの BizTalk Server パーティの解決コンポーネントに基づいています。 RNPartyRes は、RNIF 処理のための以下の機能を備えています。  
  
-   着信メッセージが BizTalk パーティに対して署名されている場合は、送信者の証明書をマップします。 着信メッセージに署名がなく、取引先アグリーメントでそれが許可されている場合、このコンポーネントは RNIF 2.01 については Delivery ヘッダーから、RNIF 1.1 については Service ヘッダーから送信者のパーティを取得します。  
  
-   送信者が存在し、送信者がホーム組織との取引先アグリーメントを持っているかどうかを検証します。  
  
 詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]party resolution コンポーネント、BizTalk Server ヘルプの「パーティの解決パイプライン コンポーネント」を参照してください。  
  
## <a name="messageupdater"></a>MessageUpdater  
 このコンポーネントは、RNIF 処理のための以下の機能を備えています。  
  
-   PIP コード、PIP バージョン、送信元パーティ、送信先パーティ、ReceiveMessageNonRepudiate コンポーネントによって保存されたワイヤ メッセージの Message Tracking ID の詳細情報を使用して MessageStorageIn テーブルを更新します。  
  
-   PIP が否認不可を必要としない場合、`ToBePurged = True` を設定してレコードに削除のマークを付けます。  
  
## <a name="message-flow"></a>メッセージ フロー  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 受信パイプラインを経由するメッセージ フローは次のとおりです。  
  
1.  HTTP アダプターは HTTP POST を使用して RNIF 1.1 オブジェクトまたは RNIF 2.01 ビジネス メッセージを受信します。  
  
2.  メッセージを正常に受信すると、アダプターは RosettaNet オブジェクトまたはビジネス メッセージを抽出し、受信パイプラインにルーティングします。  
  
3.  オブジェクトまたはビジネス メッセージに署名がある場合、MIME プリプロセッサ/デコーダーが署名を削除します。  
  
4.  署名が有効な場合、逆アセンブラーは Preamble を読み取ります。  
  
5.  メッセージがアクション メッセージで否認不可が必要な場合 (、**発信元とコンテンツの否認**プロセス構成設定の設定が`True`)、デコーダーを計算し、ダイジェストが引き続き発生します。  
  
6.  逆アセンブラーは、メッセージ (MSG) ガイドラインとグローバル変数の Preamble スキーマを使用して Preamble を検証します。  
  
7.  RNIF 2.01 では、逆アセンブラーは Delivery Header を読み取り、メッセージ ガイドラインとグローバル変数の Delivery Header スキーマを使用してヘッダーを検証します。  
  
8.  RNIF 2.01 では、逆アセンブラーは Delivery Header からパートナー情報を抽出し、署名がパートナーに属しているかどうかを検証します。  
  
9. RNIF 2.01 でペイロードが暗号化されている場合、デコーダーによってペイロード コンテナーの暗号化が解除されます。  
  
10. 逆アセンブラーは Service Header を読み取り、MSG ガイドラインとグローバル変数の Service Header スキーマを使用してヘッダーを検証します。  
  
11. RNIF 1.1 では、逆アセンブラーは Service Header からパートナー情報を抽出し、署名がパートナーに属しているかどうかを検証します。  
  
12. 逆アセンブラーは、パートナーが PIP に承認されているかどうかを確認します。 承認されていない場合、逆アセンブラーは HTTP POST に HTTP 403 ステータス メッセージを返し、必要に応じてエラーを送信します。  
  
13. メッセージが署名されたアクション メッセージの場合と**発信元とコンテンツの否認**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネント MessageStorageIn テーブルに元のメッセージが引き続き発生します。  
  
14. メッセージが署名されたシグナル メッセージの場合と**否認不可のために必要な**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネント MessageStorageIn テーブルにシグナル メッセージが引き続き発生します。  
  
15. メッセージが否認不可の MessageStorageIn テーブルに保存されている場合、MessageUpdater はメッセージのプロセス構成のプロパティを使用して MessageStorageIn テーブルを更新します。  
  
16. メッセージが以前に処理されたアクション メッセージの重複アクション メッセージの場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はエラーを送信します。  
  
17. RNIF 2.01 では、アクション メッセージが暗号化され、HTTP 同期と PIP 同期の要件が一致している場合、デコーダーによってペイロードの暗号化が解除されます。  
  
18. 逆アセンブラーは Service Content を読み取り、MSG ガイドラインとスキーマを使用して検証します。  
  
19. RNIF 2.01 では、マニフェストが有効でコンテンツ ID が存在することが逆アセンブラーによって検証されます。  
  
20. RNIF 2.01 では、逆アセンブラーはすべての添付ファイルを読み取ります。  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は、RosettaNet ヘッダー、Service Content、およびパブリック プロセスへの添付ファイルをルーティングします。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)