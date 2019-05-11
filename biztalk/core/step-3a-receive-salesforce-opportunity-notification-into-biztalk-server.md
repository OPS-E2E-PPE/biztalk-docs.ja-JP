---
title: 手順 3 a:BizTalk Server に Salesforce の営業案件通知を受け取る |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be9de6e3-6bd9-4275-b2fb-0a756c51aabf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c323d7f7975eb20f78aba0c6259d9c998779b1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392580"
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a>手順 3 a:BizTalk Server に Salesforce の営業案件通知を受信します。
作成を開始この手順で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 まずことは、Salesforce から取得し、メッセージを処理するオーケストレーションの作成を開始しましたが、営業案件通知メッセージのメッセージ スキーマに含めるべきです。  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a>Salesforce の営業案件通知スキーマを含める  
  
1. Salesforce.com ポータルにログインします。 Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。  
  
2. 左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。  
  
3. **すべてのワークフロー ルール** ページで、をクリックして、**クローズされた営業案件**先ほど作成したワークフロー。  
  
4. **クローズされた営業案件**ワーフクロー ルール ページで、をクリックして**NewOp1**送信メッセージ ワークフロー アクション。  
  
5. **NewOp1**送信メッセージ ワークフロー アクション ページで、リンクを右クリックして**クリックして WSDL**、 をクリックして**として保存ターゲット**、し保存する場所を指定WSDL。  
  
   > [!NOTE]
   >  .Wsdl の拡張子を持つファイルを保存する必要があります。  
  
6. 作成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 このチュートリアルでは、名前としてプロジェクトをお知らせ`BtsSalesforceIntegration`します。  
  
7. 右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトをポイントして、**追加**、 をクリックし、**生成した項目の追加**します。  
  
8. **生成した項目の追加**ダイアログ ボックスで、をクリックして**Consume WCF サービス**、順にクリックします**追加**を起動する、 **BizTalk WCF サービス使用**ウィザード。 [ようこそ] ページで、次のようにクリックします。**次**します。  
  
9. **メタデータ ソース**] ページで、[、**メタデータ ファイル (WSDL と XSD)** オプションをクリックして**次**。  
  
10. **メタデータ ファイル**] ページで [**追加**、Salesforce ポータルからダウンロードした WSDL ファイルを保存した場所に移動します。 WSDL ファイルを選択し、クリックして**次**します。  
  
11. 次のページで設定と名前空間`NotificationService`し**インポート**します。 スキーマ ファイルとオーケストレーションが追加されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 Salesforce から営業案件通知を受信するためのメッセージ スキーマは**NotificationService_soap_sforce_com_2005_09_outbound.xsd**します。  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a>通知メッセージを受信するオーケストレーションを作成するには  
  
1. 完了した後、 **BizTalk WCF サービス使用**ウィザードは、オーケストレーション (**NotificationService.odx**、この例では) に追加されます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
2. オーケストレーション ファイルを開き、オーケストレーション ビューで 2 つの新しいメッセージ変数を追加します。 名前を付けます`NotificationMessage`と`NotificationAck`します。 次のように、これらのメッセージ変数のメッセージの種類を設定します。  
  
   1.  設定**NotificationMessage**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*します。 このメッセージ変数は、Salesforce から受信した営業案件通知メッセージを表します。  
  
   2.  設定**NotificationAck**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*します。 このメッセージ変数は、Salesforce に返信、営業案件通知の受信確認メッセージを表します。  
  
3. 受信図形をオーケストレーションに追加します。 図形に次のプロパティを設定します。  
  
   1.  設定**アクティブ**に**True**します。  
  
   2.  設定**名前**に*ReceiveNotificationMessage*します。  
  
   3.  設定**メッセージ**に*NotificationMessage*します。  
  
4. 受信図形の後に、メッセージの構築図形を追加します。 図形の名前はメッセージとして`ConstructNotificationResponse`設定と、**構築メッセージ**プロパティを`NotificationAck`します。 メッセージの構築の一環として、Salesforce に送信される通知の受信確認メッセージを生成するマップも作成します。  
  
   1.  メッセージの構築図形内には、変換図形を追加します。 変換図形をダブルクリックし、変換の構成 ダイアログ ボックスで、選択、**新しいマップ**オプション。  
  
   2.  マップ名として指定`BtsSalesforceIntegration.MapNotificationResponse`します。  
  
   3.  ソースとして設定**NotificationMessage**と変換先として**NotificationAck**します。  
  
   4.  チェック ボックスを必ず **[ok] をクリックしたら BizTalk マッパーを起動**が選択されています。  
  
   5.  **MapNotificationResponse.btm**Salesforce に送信する通知応答を作成します。 Salesforce では、通知を送信するたびに確認応答を期待します。 通知応答メッセージのスキーマを示していますが、 **Ack**応答内の要素は Boolean 型。 そのため、マップでは、削除する必要あります、**値のマッピング**functoid とセットの 2 つの入力値 (状態と結果) を`true`します。 クリックして**OK** functoid を保存します。  
  
   6.  接続、**値のマッピング**functoid を**Ack**送信先スキーマ内の要素。  
  
5. メッセージの構築図形の後、オーケストレーションでは、Salesforce に返信を返信するために使用する送信図形を追加します。  
  
   -   設定**名前**に*SendNotificationAck*します。  
  
   -   設定**メッセージ**に*NotificationAck*します。  
  
6. オーケストレーションでは、Salesforce の通知メッセージを受信し、応答の受信確認の送信ポートを追加します。 ポート構成ウィザードでは、次のオプションを選択します。  
  
   - ポート名を指定`SalesforceNotificationPort`します。  
  
   - 新しいポートの種類を作成するオプションを選択します。  
  
   - 設定**通信パターン**に*要求-応答*します。  
  
   - 設定**ポートの通信方向**に*要求の受信と送信の応答を行います*設定と**ポートのバインド**に*以降指定*.  
  
     接続、**要求**受信図形にポートの操作 (*ReceiveNotificationMessage*) および**応答**送信図形にポートの操作 (*SendNotificationAck*)。 次のスクリーン ショットは、Salesforce から営業案件通知を受信し、戻る受信確認を送信、オーケストレーションの一部を示しています。  
  
     ![営業案件通知を受信し、応答を送信](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")  
  
   ここまでで、Salesforce から営業案件通知を受信して、受信確認が返信される場所のソリューションを設定したします。 以降のトピックで使用可能な営業案件の種類の詳細を取得する営業案件通知の処理を開始するには、このソリューションをビルドします。  
  
## <a name="see-also"></a>参照  
 [ステップ 3:Visual Studio で BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)