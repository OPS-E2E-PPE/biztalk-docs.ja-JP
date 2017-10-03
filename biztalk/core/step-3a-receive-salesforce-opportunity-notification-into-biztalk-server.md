---
title: "手順 3: BizTalk Server に Salesforce の営業案件通知を受け取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be9de6e3-6bd9-4275-b2fb-0a756c51aabf
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76ab28e8e70c0b8a222f6772a763a93252f2c413
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-receive-salesforce-opportunity-notification-into-biztalk-server"></a>手順 3: BizTalk Server に Salesforce の営業案件通知を受信
このステップでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の作成を開始します。 メッセージを処理するオーケストレーションの作成を開始する前に、まず、Salesforce から受信する営業案件通知メッセージのメッセージ スキーマを含める必要があります。  
  
### <a name="to-include-the-salesforce-opportunities-notification-schema"></a>Salesforce の営業案件通知スキーマを含めるには  
  
1.  Salesforce.com ポータルにログインします。 Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。  
  
2.  左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。  
  
3.  **すべてのワークフロー ルール** ページで、をクリックして、**クローズされた営業案件**先ほど作成したワークフローです。  
  
4.  **クローズされた営業案件** ワーフクロー ルール ページをクリックして**NewOp1**送信メッセージ ワークフロー アクション。  
  
5.  **NewOp1**送信メッセージ ワークフロー アクション ページで、リンクを右クリックして**クリックして WSDL**、 をクリックして**として保存対象**、し保存する場所を指定WSDL です。  
  
    > [!NOTE]
    >  ファイルの拡張子は、.wsdl で保存する必要があります。  
  
6.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を作成します。 このチュートリアルでは、名前としてプロジェクトをお知らせ`BtsSalesforceIntegration`です。  
  
7.  右クリックし、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソリューション エクスプ ローラーでプロジェクトをポイントし、**追加**、クリックして**生成した項目の追加**です。  
  
8.  **生成した項目の追加**ダイアログ ボックスで、をクリックして**Consume WCF サービス**、クリックして**追加**を起動する、 **BizTalk WCF サービス使用**ウィザード。 [ようこそ] ページで、をクリックして**次**です。  
  
9. **メタデータ ソース**] ページで、[、**メタデータ ファイル (WSDL と XSD)**オプションをクリックして**次**です。  
  
10. **メタデータ ファイル**] ページで [**追加**、Salesforce ポータルからダウンロードした WSDL ファイルを保存した場所に移動します。 WSDL ファイルを選択し、クリックして**次**です。  
  
11. 次のページで設定と名前空間`NotificationService` をクリックし、**インポート**です。 ウィザードでスキーマ ファイルとオーケストレーションが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトに追加されます。 Salesforce から営業案件通知を受信するため、メッセージ スキーマは**NotificationService_soap_sforce_com_2005_09_outbound.xsd**です。  
  
### <a name="to-create-an-orchestration-to-receive-the-notification-message"></a>通知メッセージを受信するためのオーケストレーションを作成するには  
  
1.  完了した後、 **BizTalk WCF サービス使用**ウィザードは、オーケストレーション (**NotificationService.odx**、この例では) に追加、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
2.  オーケストレーション ファイルを開いて、オーケストレーション ビューで 2 つの新しいメッセージ変数を追加します。 名前を付けます`NotificationMessage`と`NotificationAck`です。 メッセージ変数のメッセージ種類を、次のように設定します。  
  
    1.  設定**NotificationMessage**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notifications*です。 このメッセージ変数は、Salesforce から受信する営業案件通知メッセージを表します。  
  
    2.  設定**NotificationAck**に*NotificationService.NotificationService_soap_sforce_com_2005_09_outbound.notificationsResponse*です。 このメッセージ変数は、Salesforce に返信される営業案件通知の確認メッセージを表します。  
  
3.  オーケストレーションへ受信図形を追加します。 図形に以下のプロパティを設定します。  
  
    1.  設定**アクティブ**に**True**です。  
  
    2.  設定**名前**に*ReceiveNotificationMessage*です。  
  
    3.  設定**メッセージ**に*NotificationMessage*です。  
  
4.  受信図形の後にメッセージの構築図形を追加します。 図形の名前はメッセージとして`ConstructNotificationResponse`設定と、**構築メッセージ**プロパティを`NotificationAck`です。 構築メッセージの一部として、マップを作成して Salesforce に返信する通知確認メッセージを生成します。  
  
    1.  [メッセージの構築] 図形に [変換] 図形を追加します。 変換図形をダブルクリックし、変換の構成 ダイアログ ボックスで選択、**新しいマップ**オプション。  
  
    2.  マップ名として指定`BtsSalesforceIntegration.MapNotificationResponse`です。  
  
    3.  ソースとして設定**NotificationMessage**と変換先として**NotificationAck**です。  
  
    4.  チェック ボックスを確認してください**[ok] をクリックしたら BizTalk マッパーを起動**が選択されています。  
  
    5.  **MapNotificationResponse.btm**Salesforce に送信する通知応答を作成します。 Salesforce が通知を送信するたびに、確認が返信されることが期待されます。 通知応答メッセージのスキーマことを示しています、 **Ack**応答内の要素は Boolean 型です。 そのため、マップでは、削除する必要あります、**値のマッピング**functoid とセット、2 つの入力値 (状態と結果) に`true`です。 をクリックして**OK** functoid を保存します。  
  
    6.  接続、**値のマッピング**functoid を**Ack**送信先スキーマ内の要素。  
  
5.  オーケストレーションで、メッセージの構築図形の後に、Salesforce に確認を返信する際に使用する送信図形を追加します。  
  
    -   設定**名前**に*SendNotificationAck*です。  
  
    -   設定**メッセージ**に*NotificationAck*です。  
  
6.  オーケストレーションで、Salesforce の通知メッセージを受信し、確認を返信するポートを追加します。 ポート構成ウィザードで、次のオプションを選択します。  
  
    -   ポート名を指定`SalesforceNotificationPort`です。  
  
    -   新しいポート種類を作成するオプションを選択します。  
  
    -   設定**通信パターン**に*要求-応答*です。  
  
    -   設定**ポートの通信方向**に*要求の受信と応答の送信を行います*設定と**ポートのバインド**に*以降を指定*.  
  
     接続、**要求**受信図形にポートの操作 (*ReceiveNotificationMessage*) および**応答**送信図形にポートの操作 (*SendNotificationAck*)。 次のスクリーンショットは、Salesforce からの営業案件通知を受信し、確認を返信するオーケストレーションの一部を示しています。  
  
     ![営業案件通知を受信し、応答を送信](../core/media/bts-sf-recvnotificationorch.jpg "BTS_SF_RecvNotificationOrch")  
  
 これで、Salesforce から営業案件通知を受信して、確認を返信するソリューションのセットアップが完了しました。 次のトピックでは、このソリューションに基づいて、営業案件通知の処理を開始し、その営業案件に関する詳細情報を入手する作業について説明します。  
  
## <a name="see-also"></a>参照  
 [手順 3: Visual Studio での BizTalk Server ソリューションを作成します。](../core/step-3-create-the-biztalk-server-solution-in-visual-studio.md)