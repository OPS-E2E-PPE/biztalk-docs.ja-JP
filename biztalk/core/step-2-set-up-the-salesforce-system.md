---
title: '手順 2: Salesforce システムのセットアップ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a4b09fb-70a7-4eec-b1e3-f05de0e84df1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65a1c741103b9c8f1e9493b7bd2aa56eef8cf18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279930"
---
# <a name="step-2-set-up-the-salesforce-system"></a>手順 2: Salesforce システムをセットアップします。
このステップでは、営業案件が正常にクローズされたときに通知を送信するように Salesforce を構成します。 通知を送信する前に、次の手順を実行する必要があります。  
  
-   Salesforce でアカウントを作成する。 アカウントは Northwind の顧客を表します。  
  
-   アカウントの営業案件を作成する。 営業案件は顧客に見込める販売機会を表します。 営業案件の一部として、顧客が興味を持っている製品詳細を追加します。  
  
-   Salesforce でワークフローを作成する。  
  
-   Salesforce の接続型アプリケーション定義を作成する。  
  
> [!NOTE]
>  このトピックでは、既に Salesforce 開発者アカウントを持っていることを前提として手順を示しています。 Salesforce で新しい開発者アカウントを作成するには[http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)です。  
  
### <a name="to-create-an-account-in-salesforce"></a>Salesforce でアカウントを作成するには  
  
1.  開発者資格情報を使用して Salesforce.com ポータルにログオンします。  
  
2.  ポータルで、をクリックして、**アカウント** タブをクリックして**新規**です。  
  
3.  **新しいアカウント** ページで、さまざまなフィールドの値を指定します。 値を指定する**アカウント名**は必須です。 このチュートリアルでは、指定のアカウント名に`Customer1`です。  
  
4.  **[保存]** をクリックします。  
  
### <a name="to-create-an-opportunity-for-the-customer"></a>顧客の営業案件を作成するには  
  
1.  Salesforce.com ポータルで、をクリックして、**機会**タブです。  
  
2.  **最近の営業案件**セクションで、**新規**です。  
  
3.  [新しい営業案件] ページで、次の値を指定します。  
  
    1.  指定して、**営業案件名**など、`Opportunity with Customer 1`です。  
  
    2.  指定して、**アカウント名**です。 これは、この営業案件が関連付けられるアカウントを表します。 このチュートリアルでは、アカウントを設定`Customer1`です。 このアカウントは、前の手順で作成したアカウントです。  
  
    3.  指定して、**終了日**です。 これは営業案件をクローズする日付を表しています。  
  
    4.  指定して、**ステージ**です。 これは営業案件の現在のステージを示しています。 最初に、することができますに設定する営業案件、たとえば、 **Needs Analysis**です。  
  
         ![Salesforce で営業案件を作成](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")  
  
        > [!NOTE]
        >  ステージ設定しないことを確認**Closed Won**で開始します。 設定されているステージするたびに、このチュートリアルのシナリオの**Closed Won**リレー エンドポイントに通知が送信[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]です。 おをセットアップしていない、ソリューションの部分をまだにステージを設定する必要がありますいないように**Closed Won**です。  
  
    5.  その他のオプションのフィールドに値を指定し、クリックして**保存**です。  
  
    6.  営業案件 ページの Customer1 の 、**製品**セクションで、**製品の追加**です。  
  
    7.  製品の一覧から、顧客が興味を持っている製品を選択し、をクリックして**選択**です。  
  
    8.  選択した製品の指定、顧客が、数量をクリックして**保存**です。  
  
         ![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
## <a name="create-a-salesforce-workflow"></a>Salesforce ワークフローを作成する  
 このステップでは、営業案件が正常にクローズするたびに通知を送信するワークフローを作成します。 通知は、SOAP メッセージの形式し、でホストされるリレー エンドポイントに送信された[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]です。  
  
#### <a name="to-create-a-workflow-for-opportunities"></a>営業案件のワークフローを作成するには  
  
1.  Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。  
  
2.  左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。  
  
    > [!NOTE]
    >  [ワークフローのルール] ページを初めて開く場合は、Salesforce におけるワークフローを理解するための情報が表示されます。 情報を読み、をクリックして**続行**です。  
  
3.  **すべてのワークフロー ルール**] ページで [**新しいルール**です。  
  
4.  **オブジェクトの選択**一覧で、をクリックして**営業案件**、順にクリック**次**です。  
  
5.  次のページで、次の項目を指定します。  
  
    1.  設定、**ルール名**として`Closed Opportunity`です。  
  
    2.  設定、**評価基準**として**作成されると、し、いつでもは、その後の条件を満たす編集**です。  
  
    3.  **規則の条件**、設定をルールを実行するときに、**条件が満たされた**です。  
  
    4.  設定**フィールド**に**営業案件: ステージ**、**演算子**に**equals**、および**値**に`Closed Won`.  
  
         ![Salesforce ワークフローを作成する](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")  
  
    5.  をクリックして**保存 (&) 次へ**です。  
  
6.  新しいルールのワークフロー アクションを次のように定義します。  
  
    1.  **ワークフロー アクションの指定**] ページで [**ワークフロー アクションの追加**ボタンをクリックし、をクリックして**新しい送信メッセージ**です。  
  
    2.  設定、**名前**と**一意の名前**フィールドを`NewOp1`です。  
  
    3.  、のように、説明を指定、`Message sent when an opportunity is successfully closed`です。  
  
    4.  指定して、**エンドポイント URL**として`https://btssalesforce.servicebus.windows.net/notifications/opportunity`です。  
  
         ここでは、 **btssalesforce**は、[!INCLUDE[sb](../includes/sb-md.md)]前半の手順で作成した名前空間。 **/notifications/** リレーを作成するのには、このチュートリアルの後の手順を表します。  
  
        > [!NOTE]
        >  先に作成した [!INCLUDE[sb](../includes/sb-md.md)] 名前空間を指定する必要があります。  
  
    5.  確認してください、**保護されたコンポーネント**チェック ボックスがオフと**セッション ID の送信**のチェック ボックスをオンします。  
  
    6.  **を送信する機会がフィールド**から関連するフィールドを選択して、**利用可能なフィールド**を一覧表示し、をクリックして、**追加**ボタンをクリックします。  
  
    7.  をクリックして**保存** をクリックし、**完了**です。  
  
    8.  左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローと承認**、順にクリック**ワークフロー ルール**です。 いることを確認、**クローズされた営業案件**ルールが一覧表示します。 下にある、**アクション**の列、**クローズされた営業案件**ルール をクリックして**Activate**ルールを有効にします。  
  
## <a name="create-a-salesforce-connected-application"></a>Salesforce の接続型アプリケーションを作成する  
 接続型アプリケーションの定義を作成すると、Salesforce に接続するための OAuth トークンの要求に必要な一連のキーが生成されます。 このチュートリアルの後のステージでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が接続型アプリケーションとなり、接続型アプリケーションの定義を使用して Salesforce にクエリを送信します。  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a>Salesforce 向けの接続型アプリケーションを作成するには  
  
1.  Salesforce ポータル上で、ページの右上隅にあるログイン名をクリックし、をクリックして**セットアップ**です。  
  
2.  左側のウィンドウで **アプリ セットアップ**、展開**作成**、順に展開**アプリ**です。 **アプリ** ページの 、**接続型アプリケーション**セクションで、**新規**です。  
  
3.  **新しい接続アプリケーション** ページで、次を指定します。  
  
    1.  **アプリ名を接続している**、指定`BizTalk_Salesforce`です。  
  
    2.  **開発者名**名前に、ログを指定します。  
  
    3.  **Contact Email**電子メールを指定します。  
  
    4.  **コールバック URL**、有効な URL を指定します。  
  
        > [!NOTE]
        >  このシナリオで使用する Salesforce での認証方法では、ここで指定する値は使用しません。  
  
    5.  下にある**OAuth の使用可能なスコープ**を選択**フル アクセス**、 **、あなたに代わって要求をいつでも実行**、および**アクセスデータを管理および**をクリックし、**追加**に移動するボタン、 **OAuth スコープの選択**です。  
  
    6.  **[保存]** をクリックします。 表示されるページに関する情報を格納する、**コンシューマー キー**と**コンシューマー シークレット**です。 これらの値はメモしておく必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から Salesforce に接続する際には、これらの値が必要です。  
  
         ![Salesforce アクセス キー](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")  
  
4.  最後に、未知のネットワークの場所から Salesforce に接続する際に必要となるセキュリティ トークンを生成します。  
  
    1.  Salesforce ポータルの左側のウィンドウで **個人セットアップ**、展開**個人情報**、順にクリック**Reset My Security Token**です。  
  
    2.  警告を確認し、クリックして**Reset Security Token**です。  
  
    3.  Salesforce アカウントの作成の際に指定した電子メール アドレスに、セキュリティ トークンが送信されます。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 6: Salesforce との BizTalk Server 2013 の統合](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)