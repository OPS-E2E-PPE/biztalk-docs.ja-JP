---
title: 手順 2:Salesforce システムのセットアップ |Microsoft Docs
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
ms.openlocfilehash: f6bd461605bbb9fbdedf1a83d005501b035af2ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392710"
---
# <a name="step-2-set-up-the-salesforce-system"></a>手順 2:Salesforce システムを設定します。
この手順では、営業案件が正常に閉じられたときに通知を送信する Salesforce を構成します。 通知を送信するには、次の手順を実行する必要があります。  
  
-   Salesforce でアカウントを作成します。 アカウントは、Northwind の顧客を表します。  
  
-   アカウントの営業案件を作成します。 営業案件は顧客に見込める販売機会を表します。 営業案件の一部として、また、顧客が興味を製品の詳細を追加します。  
  
-   Salesforce でワークフローを作成します。  
  
-   Salesforce の接続型アプリケーションの定義を作成します。  
  
> [!NOTE]
>  このトピックの手順では、既に Salesforce 開発者アカウントがあることを前提としています。 Salesforce で新しい開発者アカウントを作成するには[ http://go.microsoft.com/fwlink/?LinkId=296424](http://go.microsoft.com/fwlink/?LinkId=296424)します。  
  
### <a name="to-create-an-account-in-salesforce"></a>Salesforce でアカウントを作成するには  
  
1.  開発者の資格情報を使用して Salesforce.com ポータルにログオンします。  
  
2.  ポータルで、をクリックして、**アカウント**タブをクリックし、をクリックし、**新規**します。  
  
3.  **新しいアカウント** ページで、さまざまなフィールドの値を指定します。 値を指定する**アカウント名**は必須です。 このチュートリアルでは、指定のアカウント名に`Customer1`します。  
  
4.  **[保存]** をクリックします。  
  
### <a name="to-create-an-opportunity-for-the-customer"></a>顧客の営業案件を作成するには  
  
1. Salesforce.com ポータルで、**機会**タブ。  
  
2. **最近の営業案件**セクションで、**新規**します。  
  
3. 新しい営業案件 ページで、次の値を指定します。  
  
   1. 指定、**営業案件名**、たとえば、`Opportunity with Customer 1`します。  
  
   2. 指定、**アカウント名**します。 これは、この営業案件が関連付けられているアカウントを表します。 このチュートリアルでは、アカウントを設定`Customer1`します。 前の手順では、このアカウントを作成します。  
  
   3. 指定、**終了日**します。 これは、営業案件を閉じる必要があります、日付を表します。  
  
   4. 指定、**ステージ**します。 これは、営業案件の現在のステージを示します。 最初に、設定できます営業案件、たとえば、 **Needs Analysis**します。  
  
       ![Salesforce の営業案件を作成](../core/media/bts-sf-create-opp.jpg "BTS_SF_Create_Opp")  
  
      > [!NOTE]
      >  ステージ設定しないことを確認**Closed Won**で開始します。 ステージに設定するたびに、このチュートリアルでシナリオ**Closed Won**リレー エンドポイントに、通知が送信[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]します。 設定されていない、ソリューションの部分をまだにステージを設定する必要がありますいないように**Closed Won**します。  
  
   5. その他のオプションのフィールドの値を指定し、クリックして**保存**します。  
  
   6. 営業案件 ページ customer1 の 、**製品**セクションで、**追加製品**します。  
  
   7. 製品の一覧から顧客は、対象の製品を選択し、順にクリックします**選択**します。  
  
   8. 選択した製品ごとに、クリックして、顧客が、ある数量を指定**保存**します。  
  
       ![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
## <a name="create-a-salesforce-workflow"></a>Salesforce ワークフローを作成します。  
 この手順では、営業案件が正常にクローズするたびに通知を送信するワークフローを作成します。 通知は SOAP メッセージの形式し、でホストされるリレー エンドポイントに送信される[!INCLUDE[winazure](../includes/winazure-md.md)][!INCLUDE[sb](../includes/sb-md.md)]します。  
  
#### <a name="to-create-a-workflow-for-opportunities"></a>営業案件のワークフローを作成するには  
  
1. Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。  
  
2. 左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。  
  
   > [!NOTE]
   >  最初に、ワークフロー ルール ページを開いている場合は、Salesforce でのワークフローのしくみを理解するための情報が表示されます。 情報を確認し、クリックして**続行**します。  
  
3. **すべてのワークフロー ルール**] ページで [**新しいルール**します。  
  
4. **オブジェクトの選択**一覧で、**機会**、順にクリックします**次**します。  
  
5. 次のページで、次のように指定します。  
  
   1.  設定、**ルール名**として`Closed Opportunity`します。  
  
   2.  設定、**評価基準**として**を作成し、その後の条件を満たすには、編集、いつ**します。  
  
   3.  **ルールの条件**、設定、ルールを実行するときに、**条件が満たされた**します。  
  
   4.  設定**フィールド**に**営業案件。ステージ**、**演算子**に**equals**、および**値**に`Closed Won`します。  
  
        ![Salesforce ワークフローを作成する](../core/media/bts-sf-create-workflow.jpg "BTS_SF_Create_Workflow")  
  
   5.  クリックして**保存 (&) [次へ]** します。  
  
6. 新しいルールのワークフロー アクションを定義します。  
  
   1. **ワークフロー アクションの指定**] ページで [**ワークフロー アクションの追加**ボタンをクリックし、をクリックし、**新しい送信メッセージ**します。  
  
   2. 設定、**名前**と**一意の名前**フィールドを`NewOp1`します。  
  
   3. 次のように、説明を指定、`Message sent when an opportunity is successfully closed`します。  
  
   4. 指定、**エンドポイント URL**として`https://btssalesforce.servicebus.windows.net/notifications/opportunity`します。  
  
       ここでは、 **btssalesforce**は、[!INCLUDE[sb](../includes/sb-md.md)]前の手順で作成した名前空間。 **/notifications/** はこのチュートリアルの後の手順で作成するリレーを表します。  
  
      > [!NOTE]
      >  指定する必要があります、[!INCLUDE[sb](../includes/sb-md.md)]先ほど作成した名前空間。  
  
   5. 確認します、**保護されたコンポーネント**チェック ボックスがオフ、**セッション ID の送信**チェック ボックスをオンします。  
  
   6. **営業案件を送信するフィールド**から関連するフィールドを選択、**使用可能なフィールド**ボックスの一覧をクリックして、**追加**ボタンをクリックします。  
  
   7. クリックして**保存**順にクリックします**完了**します。  
  
   8. 左側のウィンドウで **アプリ セットアップ**、展開**作成**、展開**ワークフローおよび承認**、順にクリックします**ワークフロー ルール**します。 いることを確認、**クローズされた営業案件**ルールが表示されます。 、**アクション**の列、**クローズされた営業案件**ルールで、**アクティブ化**ルールを有効にします。  
  
## <a name="create-a-salesforce-connected-application"></a>Salesforce を作成するアプリケーションの接続  
 接続されているアプリケーション定義を作成するには、Salesforce に接続するための OAuth トークンを要求するために必要なキーのセットが生成されます。 このチュートリアルの後のステージで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接続されているアプリケーション定義を使用して Salesforce にクエリを接続しているアプリケーションになります。  
  
#### <a name="to-create-a-connected-application-for-salesforce"></a>Salesforce に接続されているアプリケーションを作成するには  
  
1. Salesforce のポータル ページの右上隅にあるログイン名をクリックします。 をクリック**セットアップ**します。  
  
2. 左側のウィンドウで **アプリ セットアップ**、展開**作成**、順に展開**アプリ**します。 **アプリ**ページの**接続アプリ**セクションで、**新規**します。  
  
3. **新しい接続アプリケーション** ページで、次を指定します。  
  
   1. **接続型アプリケーション名**、指定`BizTalk_Salesforce`します。  
  
   2. **開発者名**名前に、ログを指定します。  
  
   3. **Contact Email**電子メールを指定します。  
  
   4. **コールバック URL**、有効な URL を指定します。  
  
      > [!NOTE]
      >  このシナリオでは、Salesforce での認証方法、ためここで指定する値は使用されません。  
  
   5. **使用可能な OAuth スコープ**を選択します**フル アクセス**、 **、いつでも、あなたに代わって要求を実行**、および**アクセスデータと管理** をクリックし、**追加**に移動するボタン、 **OAuth スコープの選択**します。  
  
   6. **[保存]** をクリックします。 表示されるページに関する情報を格納する、**コンシューマー キー**と**コンシューマー シークレット**します。 これらの値をメモしてをおく必要があります。 これらの値から Salesforce に接続中に必要になります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。  
  
       ![Salesforce へのアクセスのキーを](../core/media/bts-sf-consumer-keys.jpg "BTS_SF_Consumer_Keys")  
  
4. 最後に、不明なネットワークの場所から Salesforce に接続するために必要なセキュリティ トークンを生成します。  
  
   1.  Salesforce ポータルの左側のウィンドウで **個人セットアップ**、展開**個人情報**、順にクリックします**Reset My Security Token**します。  
  
   2.  警告を確認し、クリックして**セキュリティ トークンのリセット**します。  
  
   3.  Salesforce アカウントを作成するときに指定した電子メール アドレスでセキュリティ トークンを受信する必要があります。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 6:BizTalk Server 2013 を Salesforce と統合します。](Tutorial:%20Integrating%20BizTalk%20Server%202013%20with%20Salesforce.md)