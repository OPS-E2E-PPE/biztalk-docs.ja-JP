---
title: BTARN 受信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a9b9dd410a6a136b37ef506c9bc975f563a11a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284922"
---
# <a name="btarn-receive-pipeline"></a>BTARN 受信パイプライン
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive パイプライン (RNIFReceive.btp) と RosettaNet Implementation Framework (RNIF) メッセージの受信を実行します。 受信パイプラインには、次のコンポーネントが含まれています。  
  
-   ReceiveMessageNonRepudiate  
  
-   RNMimeDecoder (MIME プリプロセッサ/デコーダー)  
  
-   RNDAsm (XML 逆アセンブラ)  
  
-   RNPartyRes (Party Resolution コンポーネント)  
  
-   MessageUpdater  
  
## <a name="receivemessagenonrepudiate"></a>ReceiveMessageNonRepudiate  
 このコンポーネントは、受信したメッセージを MessageStorageIn テーブルに格納します。 このコンポーネントは、RNIF 規格で必要な否認不可処理を実行します。  
  
## <a name="rnmimedecoder"></a>RNMimeDecoder  
 このコンポーネントは、上のネイティブ BizTalk Server MIME プリプロセッサ/デコーダーに基づいています。 RNMimeDecoder は、RNIF 処理のため、次の機能を追加します。  
  
- RNIF 2.01 では、存在する場合に、service content と添付ファイルを解読します。  
  
- RNIF 1.1 では、8 バイト ヘッダーとペイロードの末尾にデタッチされた署名ヘッダーを処理します。  
  
  詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プリプロセッサ/デコーダの場合、BizTalk Server ヘルプの「MIME/SMIME デコーダー パイプライン コンポーネント」を参照してください。  
  
## <a name="rndasm"></a>RNDAsm  
 このコンポーネントは、ネイティブの BizTalk Server XML 逆アセンブラーに基づいています。 RNDAsm は、RNIF 処理のため、次の機能を追加します。  
  
- 受信ドキュメントに DOCTYPE ヘッダーがある場合は、このコンポーネントはそこから、名前空間を生成し、受信ドキュメント内のすべてのノードをその名前空間に移動します。  
  
- 受信メッセージが、重複しているし、メッセージが重複している場合は、エラー メッセージを生成するかどうかを確認するメッセージの関連付けを実行します。  
  
- メッセージの追加部分として添付ファイルを格納します。  
  
- メッセージのプロパティを昇格させます。  
  
  詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]逆アセンブラー、BizTalk Server ヘルプの「XML 逆アセンブラー パイプライン コンポーネント」を参照してください。  
  
## <a name="rnpartyres"></a>RNPartyRes  
 このコンポーネントは、ネイティブの BizTalk Server パーティの解決コンポーネントに基づいています。 RNPartyRes は、RNIF 処理のため、次の機能を追加します。  
  
- 受信メッセージが BizTalk パーティに署名されている場合は、送信者の証明書をマップします。 受信メッセージが署名されていない、取引先アグリーメントが許可されている場合は、このコンポーネントを取得します、送信側パーティは Delivery header から RNIF 2.01 Service header について RNIF 1.1。  
  
- 送信者が存在して、送信者がホーム組織と取引先パートナー契約を持つことを検証します。  
  
  詳細については、ネイティブ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]party resolution コンポーネントを BizTalk Server ヘルプの「パーティの解決パイプライン コンポーネント」を参照してください。  
  
## <a name="messageupdater"></a>MessageUpdater  
 このコンポーネントは、RNIF 処理のため、次の機能を追加します。  
  
-   PIP コード、PIP バージョン、送信元パーティ、送信先パーティ、および Message Tracking ID、ReceiveMessageNonRepudiate コンポーネントによって保存されたワイヤ メッセージの詳細を含む MessageStorageIn テーブルを更新します。  
  
-   PIP に否認不可が必要としない場合は、削除、設定のレコードをマーク`ToBePurged = True`します。  
  
## <a name="message-flow"></a>メッセージ フロー  
 メッセージ フローは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプラインは、次のようにします。  
  
1. HTTP アダプターでは、RNIF 1.1 オブジェクトまたは HTTP POST を介して RNIF 2.01 ビジネス メッセージを受信します。  
  
2. アダプターが正常にメッセージを受け取る場合、アダプターは RosettaNet オブジェクトまたはビジネス メッセージを抽出し、受信パイプラインにルーティングします。  
  
3. オブジェクトまたはビジネス メッセージが署名されている場合、MIME プリプロセッサ/デコーダーは、署名を削除します。  
  
4. 署名が有効な場合、逆アセンブラーは preamble を読み取ります。  
  
5. メッセージがアクション メッセージで否認不可が必要な場合 (、**発信元とコンテンツの否認**プロセス構成設定の設定が`True`)、デコーダーを計算してダイジェストを維持します。  
  
6. 逆アセンブラーは、(メッセージ (MSG) ガイドラインとグローバル変数の preamble スキーマ) を持つ preamble を検証します。  
  
7. RNIF 2.01 では、逆アセンブラーは delivery header を読み取りし、ヘッダー、MSG ガイドラインと delivery header スキーマを使用して、グローバル変数を検証します。  
  
8. RNIF 2.01 では、逆アセンブラーは delivery header からパートナー情報を抽出し、パートナーに属していることを確認する署名します。  
  
9. RNIF 2.01 では、ペイロードが暗号化されている場合、デコーダーによってペイロード コンテナーが解読します。  
  
10. 逆アセンブラーでは、サービスのヘッダーを読み取りおよびグローバル変数で、MSG ガイドラインと、サービス ヘッダー スキーマを使用して、ヘッダーを検証します。  
  
11. RNIF 1.1 での逆アセンブラーは service header からパートナー情報を抽出し、パートナーに属していることを確認する署名します。  
  
12. 逆アセンブラーは、PIP のパートナーが承認されているかどうかを確認します。 いない場合は、逆アセンブラーは HTTP 403 ステータス メッセージでは、HTTP POST を返信する場合は、必要に応じて、エラーを送信します。  
  
13. メッセージが署名されたアクション メッセージの場合と**発信元とコンテンツの否認**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネントには、MessageStorageIn テーブルに元のメッセージが引き続き発生します。  
  
14. メッセージが署名されたシグナル メッセージの場合と**否認不可のために必要な**に設定されている`True`、ReceiveMessageNonRepudiate コンポーネントはシグナル メッセージを MessageStorageIn テーブルを永続化します。  
  
15. メッセージは、否認不可用 MessageStorageIn テーブルで永続化された、MessageUpdater はメッセージのプロセス構成のプロパティを持つ MessageStorageIn テーブルを更新します。  
  
16. メッセージのアクションが以前に処理されたメッセージの重複アクション メッセージでは場合[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]はエラーを送信します。  
  
17. RNIF 2.01 では、デコーダーは、アクション メッセージが暗号化され、HTTP 同期と PIP 同期の要件の間で一致がある場合に、ペイロードを解読します。  
  
18. 逆アセンブラーは、サービスのコンテンツを読み取って、MSG ガイドラインとスキーマを使用して検証します。  
  
19. RNIF 2.01 では、逆アセンブラーは、マニフェストが有効で、コンテンツ ID が存在することを確認します。  
  
20. RNIF 2.01 では、逆アセンブラーはすべての添付ファイルを読み取ります。  
  
21. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] RosettaNet ヘッダー、service content、およびパブリック プロセスへの添付ファイルをルーティングします。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)