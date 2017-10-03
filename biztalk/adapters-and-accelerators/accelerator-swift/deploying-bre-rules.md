---
title: "BRE のルールの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, BRE policies
- BRE policies, deploying
ms.assetid: 3a66aa57-e7f9-400f-963c-eda12fb1e659
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 195b63948f79ed5403c130048aae86f7e7422c96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-bre-rules"></a>BRE のルールの展開
使用される BRE 規則を展開する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT メッセージを処理するオーケストレーションです。  
  
 **概要**  
  
 次のボキャブラリを公開するには。  
  
-   A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリです。 これらに*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base Policies\ボキャブラリです。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  
  
 発行して、次のポリシーを展開します。  
  
-   SWIFT のメッセージ スキーマの基本ポリシーには、スキーマが展開されているの SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、およびネットワーク ルール ポリシー (SWIFT_NetworkRulexxx_Policy.xml) を含むです。 これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base ポリシー。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  
  
-   関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml と MTxxx_Validation_Policy.xml) を展開します。 これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category 1\MTxxx です。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  
  
-   マスターおよび検証ポリシーは BIC 検証が必要な場合は、BIC 検証 (BIC_Master_Policy.xml と BIC_Validation_Policy.xml) に関連付けられています。 これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base ポリシー。 発行し、これらのポリシーを展開する、前に、BIC データベース名、SQL Server の名前を持つ BIC_Master_Policy.xml をカスタマイズする必要があり、セキュリティの値を統合します。 詳細については、次を参照してください。[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)です。 発行して、ルール エンジン展開ウィザードを使用して、これらを展開します。  
  
### <a name="to-deploy-bre-rules"></a>BRE のルールを展開するには  
  
1.  BRE 配置ユーティリティを実行します。 詳細については、「展開 BRE 規則すべてに 1 回」以下を参照してください。 このユーティリティは、発行され、次が展開します。  
  
    -   A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリ  
  
    -   メッセージ スキーマ、SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、ネットワークなどの基本 SWIFT のポリシー ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml)  
  
    -   関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml と MTxxx_Validation_Policy.xml) を展開します。  
  
2.  SQL server, BIC データベースの名前と、統合セキュリティの値の名前を持つ BIC_Master_Policy.xml をカスタマイズします。 詳細については、次を参照してください。[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)です。  
  
3.  BIC_Master_Policy.xml と BIC_Validation_Policy.xml を発行して、展開には、ルール エンジン展開ウィザードを実行 (で\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFTMessages\A4SWIFT-SRG\<バージョン > \Base ポリシー)。 詳細については、「展開 BRE 規則 1 つで、下の日時」を参照してください。  
  
## <a name="tools-for-deploying-the-policies"></a>ポリシーを展開するためのツール  
 ボキャブラリを公開し、ポリシーを展開する最も簡単な方法は、ビジネス ルール エンジン (BRE) の展開ユーティリティ A4SWIFT ソフトウェア開発キット (SDK) を使用してです。 行うことができますもこれを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ずつ、同じタスクの 1 つボキャブラリまたはポリシーを実行するルール エンジン展開ウィザード。  
  
> [!NOTE]
>  BRE 配置ユーティリティ配置しません BIC マスター ポリシーおよび BIC 検証ポリシー。 ルール エンジン展開ウィザードを使用して、これらを展開する必要があります。  
  
### <a name="deploying-bre-rules-all-at-once"></a>BRE の規則を一度にすべて展開  
 ビジネス ルール エンジン (BRE) 配置ユーティリティは、1 つの手順で、一連の発行および展開のタスクを実行します。 再実行してください、配置ユーティリティいつでも、プロジェクトにスキーマを追加することです。  
  
##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a>BRE 配置ユーティリティを使用して BRE ルールを展開するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**をクリックし、 **BRE 配置ユーティリティ**.  
  
2.  BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**です。  
  
3.  .NET グローバル アセンブリ キャッシュ ダイアログ ボックスで、選択で配置したプロジェクト アセンブリ[A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)、クリックして**[ok]**です。  
  
4.  BRE 配置ユーティリティ] ダイアログ ボックスで、[**展開**です。  
  
    > [!NOTE]
    >  そのアセンブリと共に配置するスキーマに基づいて、配置ユーティリティは関連するルールを識別し、BRE で使用するためを公開します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。  
  
    > [!NOTE]
    >  "展開が完了しました。 ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"  
  
5.  BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  
  
6.  開いている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラー。 参照\<*ドライブ*>: \Documents and settings \all \all データとログ ファイル BREDeploymentLog.txt に表示されるそのドライブを確認します。  
  
7.  ルール エンジン更新サービスを再起動します。 クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]**です。 **サービス (ローカル)**ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。  
  
### <a name="deploying-bre-rules-one-at-a-time"></a>一度に 1 つずつ BRE 規則を展開します。  
 ルール エンジン展開ウィザードを使用して、ボキャブラリを公開し、一度に 1 つのポリシーを展開することができます。 ボキャブラリ、このプロセスには、インポートして、1 つのステップ内のファイルからデータベースにボキャブラリを公開が含まれます。 インポートおよび 1 つの手順で、ポリシーをパブリッシュする別のステップに展開するポリシー、プロセスが含まれます。  
  
##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a>ルール エンジン展開ウィザードを使用して BRE ルールを展開するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**ビジネス ルール エンジン展開ウィザード**.  
  
2.  ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**です。  
  
3.  展開タスク ページで、をクリックして**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、クリックして**次**です。  
  
4.  ポリシー ストア] ページで、 **SQL サーバー名] ボックス**のサーバーを選択し、[、**選択したサーバーの構成データベース**一覧で、[ **BizTalkRuleEngineDb**です。 **[次へ]**をクリックします。  
  
5.  インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、をクリックして**参照**です。  
  
6.  [ファイル] ページで、ポリシーのインポートで、**ファイルの場所**ドロップダウン リスト、ボキャブラリまたはポリシーに応じて、次のフォルダーのいずれかに移動。  
  
    -   \<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > A4SWIFT_CodeLists.xml および A4SWIFT_Functions.xml \Base Policies\Vocabulary  
  
    -   \<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml のポリシーネットワーク ルール ポリシー、BIC_Master_Policy.xml、および BIC_Validation_Policy.xml  
  
    -   \<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category 1\MTxxx 配置済みのメッセージに関連付けられているマスターと検証ポリシースキーマ  
  
7.  を展開し、をクリックするポリシーを選択して**開く**です。  
  
8.  インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、をクリックして**次**です。  
  
9. 準備完了 ページで、をクリックして**次**です。  
  
10. [ポリシー/ボキャブラリのインポート] ページで、コマンドが成功し、をクリックすることを確認**次**です。  
  
11. 完了のポリシーを展開するかどうか、ルール エンジン展開ウィザード ページ をクリックして**このウィザードを再度実行**、順にクリック**完了**です。  
  
12. ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**です。  
  
13. 展開タスク ページで、をクリックして**ポリシーの展開**、クリックして**次**です。  
  
14. ポリシー ストア] ページで、 **SQL サーバー名] ボックス**のサーバーを選択し、[、**選択したサーバーの構成データベース**一覧で、[ **BizTalkRuleEngineDb**です。 **[次へ]**をクリックします。  
  
15. ポリシーの展開 ページで、下矢印をクリックして の横に、**ルール エンジン ポリシー**テキスト ボックスは、発行すると、したポリシーを選択し、をクリックして**次**です。  
  
16. 準備完了 ページで、をクリックして**次**です。  
  
17. **ポリシー/ボキャブラリをインポートする** ページで、コマンドが成功し、をクリックすることを確認**次**です。  
  
18. **[完了]**をクリックします。  
  
19. 再起動、**ルール エンジン更新サービス**です。 クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]**です。 **サービス (ローカル)**ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。