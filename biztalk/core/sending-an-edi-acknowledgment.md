---
title: "EDI 受信確認を送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a036d08-8a65-43ad-b72c-2a246d302792
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a47a3fbe13f4cf054b6114050b8777231c4b217
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sending-an-edi-acknowledgment"></a>EDI 受信確認を送信します。
受信確認は、EDI メッセージ送信の状態を示します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が EDI インターチェンジを受信すると、どの受信確認が有効になっているかに応じて、1 つ以上の受信確認が EDI インターチェンジの送信者に返されます。  
  
 検証のレベルに基づき、EDI メッセージ確認は 2 つの種類に分類されます。  
  
-   A**技術確認**ヘッダーの検証の結果として生成します。 技術確認では、アドレス受信者によるインターチェンジ ヘッダーおよびトレーラの処理状態が報告されます。  
  
-   A**機能確認**本文の検証の結果として生成します。 機能確認では、受信したドキュメントの処理中に発生した各エラーが報告されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]1 つのインターチェンジへの応答で技術と機能の両方の受信確認を返すことができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各インターチェンジで 1 つの技術確認を返します。 X12 インターチェンジの場合は、受信したグループごとに 1 つの機能確認が返されます。 EDIFACT インターチェンジの場合は、インターチェンジに含まれるグループの数に関係なく、インターチェンジごとに 1 つの機能確認が返されます。  
  
## <a name="x12-acknowledgments"></a>X12 受信確認  
 **X12 技術確認**  
  
 X12 メッセージの ISA ヘッダーおよび IEA トレーラが有効な場合 (他のコンテンツに関係なく)、成功を通知する TA1 受信確認が送信されます。 TA1 受信確認の内容の詳細については、次を参照してください。 [X12 TA1 受信確認](../core/x12-ta1-acknowledgment.md)です。  
  
 **X12 機能確認**  
  
 インターチェンジまたは機能グループの受信を確認するため、1 つ以上の機能グループまたは 1 つ以上のトランザクションを受理または拒否するため、および標準に準拠していることを検証して報告するために、997 受信確認が使用されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信したインターチェンジに複数のグループが含まれている場合は、グループごとに 1 つの受信確認が返されます。 1 つのグループに複数のトランザクション セットが含まれている場合は、そのグループに対する受信確認に複数の AK2 ループ (トランザクション セットごとに 1 つずつ) が含まれます (受理されたトランザクション セットに対して AK2 ループが生成されるように設定されている場合)。 997 受信確認の内容の詳細については、次を参照してください。 [X12 997 受信確認](../core/x12-997-acknowledgment.md)です。  
  
> [!NOTE]
>  EDI 受信パイプラインは、X12 機能確認の機能グループ ヘッダー (GS) セグメントを構築するとき、アプリケーション送信者コード (GS02) とアプリケーション受信者コード (GS03) を、確認対象の機能グループから取得します。 ただし、受信メッセージの GS02 は確認の GS03 にマップされ、受信メッセージの GS03 は確認の GS02 にマップされます。  
  
## <a name="edifact-acknowledgments"></a>EDIFACT 確認  
 **EDIFACT 技術確認**  
  
 EDIFACT では、個別の技術確認は使用されませんが、受信確認に対し機能確認または CONTRL 確認のセクション (以下を参照) が再使用されます。 これにより、技術確認がエミュレートされます。  
  
 技術 CONTRL 確認の詳細については、次を参照してください。[技術確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-technical-acknowledgment.md)です。  
  
 **EDIFACT 機能確認**  
  
 EDIFACT では、受信したインターチェンジ、グループ、およびメッセージを確認するため、受信したインターチェンジ、グループ、およびメッセージを受理または拒否するため、および受信したインターチェンジ、グループ、およびメッセージに含まれている構文エラーまたはサポートされていない機能を一覧表示するために、機能 CONTRL 確認が使用されます。 CONTRL 確認では、受信した完全なインターチェンジの構文チェックの結果が報告されます。  
  
 機能 CONTRL 確認の詳細については、次を参照してください。[機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)です。  
  
## <a name="when-an-acknowledgment-is-generated"></a>確認が生成される場合  
 EDI 受信パイプラインは、次のいずれかの条件が満たされた場合に確認を生成します。  
  
-   受信したインターチェンジのデータ要素が確認を要求した場合。 X12 エンコード メッセージのため、受信パイプラインは、ISA14 データ要素が 1 に設定されている場合に技術 TA1 確認を生成します。 EDIFACT エンコード メッセージのため、受信パイプラインは、UNB9 データ要素が 2 に設定および、UNB9 データ要素が 1 に設定されている場合は機能 CONTRL 確認で生成する場合に技術 CONTRL 確認を生成します。  
  
-   確認を要求するようにアグリーメントのプロパティが設定されている場合。 これらのプロパティは、X12 インターチェンジの場合、 **TA1 が必要**と**997 が必要**プロパティで、**受信確認**の双方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックス。 EDIFACT インターチェンジの場合は、これらのプロパティは、**メッセージの受信 (CONTRL が必要です)**と**確認 (CONTRL) が必要です**で、**受信確認**のページ双方向アグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス。 特定種類の確認を有効にすると、その種類の確認をバッチ処理するかどうかを指定することもできます。  
  
-   確認を要求するようにグローバル プロパティが設定されている場合 (インターチェンジに対するアグリーメントを特定できないとき)。 このプロパティとは、次のとおりです。  
  
    -   **TA1 が必要**と**997 が必要**内のプロパティ、**受信確認**のアグリーメント タブのページ、 **X12 フォールバック設定** ダイアログ ボックス。  
  
    -   **メッセージの受信 (CONTRL が必要です)**と**確認 (CONTRL) が必要です**で、**受信確認**のアグリーメント タブのページ、 **EDIFACT フォールバック設定** ダイアログ ボックス。  
  
 EDIFACT では、EDI 受信パイプラインは、技術確認と機能確認の両方が要求された場合に 2 つの別々の CONTRL 確認を返します。 技術 CONTRL 確認には、受信確認情報のみが含まれます。 機能 CONTRL 確認には、受信情報と機能確認情報の両方が含まれます。 詳細については、次を参照してください。 [EDIFACT CONTRL 確認](../core/edifact-contrl-acknowledgment.md)です。  
  
## <a name="identifying-an-acknowledgment-with-a-control-number"></a>制御番号による受信確認の識別  
 X12 の場合はトランザクション セット制御番号 (ST2 データ要素) によって、EDIFACT の場合はトランザクション セット参照番号 (UNH1 データ要素) によって、各確認を識別する必要があります。 出力方向の受信確認では、アグリーメントが構成されている場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]トランザクション セット制御または参照番号を次に基づくアグリーメントの設定値に設定されます。  
  
-   **X12 受信確認**– (**ACK 制御番号 (ST02)**プロパティ**ローカル ホスト設定**ページ (**受信者の設定**セクション)、アグリーメントのタブの**アグリーメントのプロパティ** ダイアログ ボックス  
  
-   **EDIFACT 受信確認の**– (**Edifact Ack 制御番号**プロパティ**ローカル ホスト設定**ページ (**受信者の設定**セクション) のアグリーメント タブの**アグリーメントのプロパティ** ダイアログ ボックス  
  
 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントによって決定されない、受信確認には、同じプロパティとして使用が、上記のように、アグリーメント タブで使用可能な**X12 フォールバック設定**ad **EDIFACT フォールバック設定** ダイアログ ボックス。 この設定は、技術確認と機能確認の両方が構成されている場合は、技術確認と機能確認の両方に適用されます。 この整数は、受信確認またはインターチェンジが生成されるたびに 1 が加算されます。  
  
 確認のエンベロープは、確認管理スキーマに従い、受信したメッセージ内のデータから構築されます。  
  
## <a name="preparing-the-acknowledgment"></a>確認の準備  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が受信確認のエンベロープを作成する方法は、メッセージのエンベロープを作成する方法と同じです。つまり、インターチェンジ制御ヘッダーおよび機能グループ ヘッダーの定義を使用して作成されます。 詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。  
  
 生成された受信確認 (TA1、997、または CONTRL) がシームレスにルーティングされるようにするために、受信確認のプロパティ `DestinationPartyReceiverQualifier`、`DestinationPartyReceiverIdentifier`、`DestinationPartySenderQualifier`、および `DestinationPartySenderIdentifier` が EDI 逆アセンブラーによって設定されます。  
  
## <a name="synchronous-and-asynchronous-acknowledgments"></a>同期確認と非同期確認  
 EDI 確認を同期送信するか、または非同期送信するか選択できます。 場合、同期[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]受信ポートを双方向の要求-応答の送信パイプラインに直接受信確認をルーティングされます。 非同期の場合、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、メッセージ ボックスに、受信確認をルーティングし、送信ポートがそのメッセージをサブスクライブします。  
  
 指定する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信、受信確認を同期的に、選択**要求-応答で送信パイプラインに確認をルーティングの受信ポート**で、**ローカル ホスト設定**ページ (**受信者の設定**セクション) で**インターチェンジの設定**双方向アグリーメント タブ (X12 および EDIFACT アグリーメント用)。 このプロパティをオフにする場合は、EDI インターチェンジを返すように双方向の受信ポートの送信パイプラインを設定する必要があります。  
  
 シナリオで要求 - 応答の受信ポートを使用し、技術確認と機能確認の両方が有効になっている場合、技術確認は同期的に送り戻され、機能確認は非同期的に送り戻されます。  
  
 HTTP/HTTPS を介して EDIINT/AS2 でエンコードされたメッセージを受信したとき、MIME でラップされた EDI ペイロードに対する応答として MDN が (同じソケットで) 送り出されと、EDI 確認は同期的には送り出されません。 場合、この場合、**要求-応答で送信パイプラインに確認をルーティングの受信ポート**プロパティがオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロパティは無視されます。  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認構造](../core/edi-acknowledgment-structure.md)   
 [EDI サービスと管理スキーマ](../core/edi-service-and-control-schemas.md)   
 [X12 TA1 受信確認](../core/x12-ta1-acknowledgment.md)   
 [X12 997 受信確認](../core/x12-997-acknowledgment.md)   
 [EDIFACT CONTRL 受信確認](../core/edifact-contrl-acknowledgment.md)   
 [技術確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-technical-acknowledgment.md)   
 [機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)