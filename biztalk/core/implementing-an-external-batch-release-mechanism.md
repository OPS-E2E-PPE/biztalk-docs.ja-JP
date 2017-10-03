---
title: "外部バッチ リリース メカニズムを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5633a448-cc29-4931-a3ad-206ae25c989b
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88b6962cc0c83ab0ac4971f481b9ac1f185ca02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-an-external-batch-release-mechanism"></a>外部バッチ リリース メカニズムの実装
外部リリースのトリガーを使用すると、バッチのリリースをトリガーできます。 外部リリースのトリガーでは、バックエンドの基幹業務アプリケーションによって、特定のしきい値に到達したときに、リリースを自動的にトリガーできます。 このメカニズムは、自動的に、スケジュールまたはトランザクション セットや文字の数によってバッチのリリースをトリガーするかをクリックして、バッチを手動でトリガーするだけでなく、**オーバーライド**ボタンをクリックして、**バッチ構成**一方向アグリーメント タブのページです。  
  
 外部リリースのトリガーを実装するには、OverrideControlMessage を処理する受信ポートと受信場所を設定する必要があります。 受信場所では `Edi.BatchControlMessageRecvPipeline` 受信パイプラインを使用する必要があります。 このパイプラインは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が手動上書きメッセージを処理するために使用する BatchControlMessageRecvLoc 受信場所で使用されるパイプラインと同じです。 ただし、BatchControlMessageRecvLoc が SQL 型の受信場所であるのに対し、ここで外部リリースのトリガー用に設定する受信場所では、任意の種類のアダプターを使用できます。  
  
 外部バッチ リリースは、XML コントロール メッセージによってトリガーされます。 バッチをトリガーするには、バックエンド アプリケーションでコントロール メッセージを受信場所にルーティングします。 コントロール メッセージを変更することにより、バッチをアクティブ化、上書き、または終了できます。 コントロール メッセージの作成方法については、以下の手順を参照してください。  
  
 外部リリースのトリガーを有効にするを選択する必要があります、**外部リリースのトリガ**プロパティに、**バッチ構成**のページ、**アグリーメントのプロパティ**ダイアログX12 または EDIFACT のボックスです。 このプロパティは、バッチ リリースには外部リリース メッセージが必要であることを示します。 **オーバーライド**ボタン、**停止**ボタン、および**アクティブ化**の範囲 コントロールは有効なまま場合、**外部リリースのトリガー**プロパティには選択されています。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a>外部バッチ リリース トリガー メッセージ用の受信場所を作成するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、一方向受信ポートを作成します。 受信ポートを作成する方法については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。  
  
2.  この受信ポート内に一方向の受信場所を作成します。  
  
3.  トランスポートの種類を選択します。 この受信場所には、どの種類のトランスポートを選択してもかまいません。 一般的には、FILE を選択して、ファイルを受信するフォルダーを入力する方法が多く用いられます。  
  
4.  [受信パイプライン] で、[`BatchControlMessageRecvPipeline`] を選択します。  
  
5.  **[OK]**をクリックします。  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a>外部バッチ リリース トリガー メッセージを作成するには  
  
1.  メモ帳で新しいファイルを作成し、.xml 拡張子付きの名前を付けます。  
  
2.  次の内容をファイルに追加します。  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ControlMessage xmlns="http://SQLControlMessage.IssueSelect">  
      <PAM_Control xmlns="http://SQLControlMessage.IssueSelect">  
        <DestinationParty>[Party ID]</DestinationParty>  
        <EdiMessageType>[0 for X12\HIPAA|1 for Edifact]</EdiMessageType>  
        <ActionType>EdiBatchOverride</ActionType>  
        <ActionDateTime>[yyyy-mm-ddThh:mm:ss.sss]</ActionDateTime>  
        <UsedOnce>0</UsedOnce>  
        <BatchId>[Batch ID]</BatchId>  
        <BatchName>[Batch Name]</BatchName>  
        <DestinationPartyName>[Destination Party/Partner name]</DestinationPartyName>  
        <SenderPartyName>[Sender Party/Partner name]</SenderPartyName>  
        <AgreementName>[Agreement Name]</AgreementName>  
        <ReceiverPartyNameType>[Receiver Party/Partner name]</ReceiverPartyNameType>  
        <ToBeBatched>1</ToBeBatched>  
      </PAM_Control>  
    </ControlMessage>  
    ```  
  
     上記内容の値を次のように置換します。  
  
    -   アクションの種類を指定します。 通常、 **ActionType**に設定する必要があります**EdiBatchOverride**アグリーメントで行われたバッチ設定を上書きします。 設定することもできます**EdiBatchTerminate**外部トリガーを通じてバッチを終了します。  
  
        > [!NOTE]
        >  バッチをアクティブ化する外部リリースのトリガーを使用する必要がありますいないをお勧めします。 そのため、指定しないでください**ActionType**として**EdiBatchActivate**です。  
  
    -   バッチ ID およびバッチ名を特定します。 これを行うには、開く、**アグリーメントのプロパティ** ダイアログ ボックス、および一方向アグリーメント タブで、をクリックして**バッチ構成**です。 オーバーライドしての値を入力するバッチのタブをクリックして**バッチ名**と**バッチ ID**にフィールド、 **BatchName**と**BatchID**制御メッセージのノードです。  
  
    -   送信先パーティ名を指定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル** ページで、バッチを受信するパーティまたはパートナーの名前を取得インターチェンジの場合します。 名前を入力、 **ReceiverPartyNameType**制御メッセージのノードです。  
  
    -   送信元パーティ名を指定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル** ページで、バッチ インターチェンジを送信するパーティまたはパートナーの名前を取得. 名前を入力、 **SenderPartyName**制御メッセージのノードです。  
  
    -   アグリーメント名を指定します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル**] ページの [、**契約**] セクションで、必要がありますをオーバーライドするコントロール メッセージを使用して、[バッチ構成を持つアグリーメントを右クリックして**プロパティ**です。 **アグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、**全般プロパティ** ページから値をコピー、**名前**フィールドに、**アグリーメントのパラメーター**セクション、および貼り付けることで、 **AgreementName**制御メッセージのノードです。  
  
    > [!NOTE]
    >  インポート先のパーティ ID を指定する必要はありません。 要素は、下位互換性のためにのみ、コントロール メッセージで必要になります。  
  
3.  ファイルを保存します。  
  
### <a name="to-enable-the-external-release-trigger"></a>外部リリースのトリガーを有効にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして、**パーティ**ノードとの間、**パーティとビジネス プロファイル**] ページの [、**契約**] セクションで、必要がありますをオーバーライドするコントロール メッセージを使用して、[バッチ構成を持つアグリーメントを右クリックして**プロパティ**です。 **アグリーメントのプロパティ** ダイアログ ボックスの一方向アグリーメント タブのをクリックして**バッチ構成**です。  
  
2.  **バッチ構成**] ページで、外部リリースのトリガーを対象となるし [バッチのタブをクリックして、**リリース**セクションで、**外部リリースのトリガー**.  
  
3.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [EDI バッチの構成](../core/configuring-edi-batches.md)   
 [作成する方法、受信場所](../core/how-to-create-a-receive-location.md)