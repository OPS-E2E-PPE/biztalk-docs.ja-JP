---
title: BRE ルールの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, BRE policies
- BRE policies, deploying
ms.assetid: 3a66aa57-e7f9-400f-963c-eda12fb1e659
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 311a15690dfa63fe18f67ce320310a0ed3339e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977963"
---
# <a name="deploying-bre-rules"></a>BRE ルールの展開
使用される BRE ルールを展開する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT メッセージを処理するオーケストレーションです。  

 **概要**  

 次のボキャブラリを公開するには。  

- A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリです。 これらにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base Policies\Vocabulary します。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  

  発行し、次のポリシーの展開します。  

- SWIFT のメッセージ スキーマの基本ポリシーには、スキーマが展開されている SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、およびネットワーク ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml) など。 これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  

- 関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml および MTxxx_Validation_Policy.xml) を展開します。 これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MTxxx します。 発行し、BRE 配置ユーティリティを使用してこれらを展開します。  

- BIC 検証が必要な場合は、BIC 検証 (BIC_Master_Policy.xml および BIC_Validation_Policy.xml) に関連付けられているマスターと検証のポリシー。 これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー。 発行と、これらのポリシーを展開する前に、BIC データベース名である SQL Server の名前を持つ BIC_Master_Policy.xml をカスタマイズする必要があり、セキュリティの値を統合します。 詳細については、次を参照してください。[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。 発行し、ルール エンジン展開ウィザードを使用して、これらを展開します。  

### <a name="to-deploy-bre-rules"></a>BRE ルールを展開するには  

1.  BRE 配置ユーティリティを実行します。 詳細については、「展開 BRE ルールすべてに 1 回」以下を参照してください。 このユーティリティは発行し、次のデプロイします。  

    -   A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリ  

    -   SWIFT の基本ポリシーの SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、ネットワーク ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml) などのメッセージ スキーマ  

    -   関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml および MTxxx_Validation_Policy.xml) を展開します。  

2.  SQL server, BIC データベースの名前、および統合のセキュリティの値の名前を持つ BIC_Master_Policy.xml をカスタマイズします。 詳細については、次を参照してください。[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。  

3.  BIC_Master_Policy.xml と BIC_Validation_Policy.xml を発行して、展開には、ルール エンジン展開ウィザードの実行 (で\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー)。 詳細については、「展開 BRE ルール 1 つ同時に」次を参照してください。  

## <a name="tools-for-deploying-the-policies"></a>ポリシーを展開するためのツール  
 ボキャブラリを公開し、ポリシーを展開する最も簡単な方法は、A4SWIFT ソフトウェア開発キット (SDK) をビジネス ルール エンジン (BRE) 配置ユーティリティを使用してです。 使用して行うようにも、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]時に、同じタスクの 1 つボキャブラリまたはポリシーを実行します。 ルール エンジン展開ウィザード。  

> [!NOTE]
>  BRE 配置ユーティリティをデプロイしません BIC マスター ポリシーおよび BIC 検証ポリシー。 ルール エンジン展開ウィザードを使用してこれらを展開する必要があります。  

### <a name="deploying-bre-rules-all-at-once"></a>BRE ルールをすべて一度に展開します。  
 ビジネス ルール エンジン (BRE) 配置ユーティリティは、1 つの手順で、一連の発行および展開のタスクを実行します。 必要がありますを再実行する配置ユーティリティいつをプロジェクトにスキーマを追加することです。  

##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a>BRE 配置ユーティリティを使用して BRE ルールを展開するには  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**.  

2. BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**します。  

3. .NET グローバル アセンブリ キャッシュ ダイアログ ボックスに展開されたプロジェクトのアセンブリを選択します。 [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)、順にクリックします**OK**します。  

4. BRE 配置ユーティリティ] ダイアログ ボックスで、[**デプロイ**します。  

   > [!NOTE]
   >  そのアセンブリを展開するスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。  

   > [!NOTE]
   >  "デプロイが完了しました。 ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"  

5. BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  

6. 開いている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラー。 参照\<*ドライブ*\>: \Documents and バックアップ データの場合、そのドライブに表示される BREDeploymentLog.txt をログ ファイルことを確認します。  

7. ルール エンジン更新サービスを再起動します。 クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。 **サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。  

### <a name="deploying-bre-rules-one-at-a-time"></a>一度に BRE ルール 1 の展開  
 ルール エンジン展開ウィザードを使用して、ボキャブラリを公開し、一度に 1 つのポリシーをデプロイすることができます。 ボキャブラリにはこのプロセスには、インポートして、1 つのステップ内のファイルからデータベースにボキャブラリを公開が含まれます。 ポリシーをインポートおよび 1 つの手順で、ポリシーをパブリッシュし、別のステップに展開するプロセスします。  

##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a>ルール エンジン展開ウィザードを使用して BRE ルールを展開するには  

1. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**.  

2. ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**します。  

3. 展開タスク ページで、次のようにクリックします。**インポート ポリシー/ボキャブラリをファイルからデータベースに発行および**、順にクリックします**次**。  

4. ポリシー ストア ページで、 **SQL サーバー名 ボックス**のサーバーを選択し、**選択したサーバーの構成データベース**一覧で、 **BizTalkRuleEngineDb**。 **[次へ]** をクリックします。  

5. インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、次のようにクリックします。**参照**します。  

6. [ファイル] ページで、ポリシーのインポートで、**検索**ドロップダウン リスト、ボキャブラリまたはポリシーに応じて、次のフォルダーのいずれかに移動。  

   -   \<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>A4SWIFT_CodeLists.xml の \Base Policies\VocabularyA4SWIFT_Functions.xml  

   -   \<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base SWIFT_Reference_Policy.xml、SWIFT_ のポリシーPartyIdentifier_Policy.xml、ネットワーク ルール ポリシー、BIC_Master_Policy.xml、および BIC_Validation_Policy.xml  

   -   \<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MTxxx マスターと検証ポリシー展開済みのメッセージ スキーマに関連付けられています。  

7. 展開、およびクリックするポリシーを選択して**オープン**します。  

8. インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、次のようにクリックします。**次**します。  

9. 準備完了 ページで、**次**します。  

10. ポリシー/ボキャブラリのインポート ページで、コマンドが成功し、クリックを確認します。**次**します。  

11. 完了のポリシーを展開するかどうか、ルール エンジン展開ウィザード ページ をクリックして**このウィザードを再度実行**、順にクリックします**完了**します。  

12. ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**します。  

13. 展開タスク ページで、次のようにクリックします。**ポリシーの展開**、 をクリックし、**次**。  

14. ポリシー ストア ページで、 **SQL サーバー名 ボックス**のサーバーを選択し、**選択したサーバーの構成データベース**一覧で、 **BizTalkRuleEngineDb**。 **[次へ]** をクリックします。  

15. ポリシーの展開 ページで、場合は、横にある下矢印をクリックして、**ルール エンジン ポリシー**テキスト ボックスが発行したポリシーを選択し、順にクリックします**次**します。  

16. 準備完了 ページで、**次**します。  

17. **ポリシー/ボキャブラリのインポート** ページで、コマンドが成功したことを確認 をクリックして**次**します。  

18. **[完了]** をクリックします。  

19. 再起動、**ルール エンジン更新サービス**します。 クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。 **サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。
