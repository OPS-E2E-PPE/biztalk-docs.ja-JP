---
title: 銀行識別コードの検証を有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe33576bb23ff40fd80f85281c38a6f5a0ec930
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974171"
---
# <a name="enabling-validation-of-bank-identifier-codes"></a>銀行識別コードの検証を有効にします。
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]スキーマでは、SWIFT インターチェンジのドキュメントで指定された銀行識別コード (BICs) が、SWIFT 定義 BIC データ形式に準拠していることを確認します。 A4SWIFT は、データベース内の顧客が指定した BIC リストに対して BICs の検証もサポートします。  

 BRE の検証を有効にして BIC 検証を有効にし、この検証を実行することができます。  

 既定では、A4SWIFT セットアップには、BRE の検証が無効にします。 有効にするには、A4SWIFT 逆アセンブラーを使用する受信パイプラインが true と BRE 検証の構成パラメーターを設定する必要があります。 検証するためのメッセージに、マスター ポリシーと特定の検証ポリシーを展開する BRE 配置ユーティリティも実行する必要があります (MT*xxx*_Master_policy.xml と MT*xxx*_Validation_Policy.xml)。 詳細については、次を参照してください。[の BRE ポリシーを操作](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)と[BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)します。  

 使用する必要がありますを BRE の検証を有効にした後に発行し、両方 BIC 検証ポリシー (BIC_Master_Policy.xml および BIC_Validation_Policy.xml) を配置、ルール エンジン展開ウィザードを使用します。 これを行うには、前に、次の操作を行う必要があります。  

- SWIFT から BIC 値を持つデータベースを設定します。 A4SWIFT セットアップによってインストールされる A4SWIFT データベースの Bicplus テーブルを使用することができますか、独自のカスタム データベースを使用することができます。 詳細については、次を参照してください。 [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)します。  

- BIC データベースを設定し、BIC マスター ポリシーをカスタマイズして BIC 検証を有効にします。 次の手順を参照してください。  

  BIC 検証が必要ない場合はパフォーマンスの向上のため BIC の検証ポリシーを展開する必要がありますされません。  

> [!NOTE]
>  発行し、A4SWIFT_Codelist と A4SWIFT_Functions ボキャブラリを公開した場合にのみ、BIC 検証ポリシーを展開できます。 SWIFTSchemas アセンブリで BRE 配置ユーティリティを実行してこれらのボキャブラリを公開します。 詳細については、次を参照してください。[レッスン 1: 関連するビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)します。  

### <a name="to-customize-the-bic-master-policy"></a>BIC マスター ポリシーをカスタマイズするには  

1. (メモ帳など)、XML エディターを開きを参照 **<*ドライブ*Program files \ Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Base ポリシー**します。  

2. 開いている**BIC_Master_Policy.xml**します。 次の既存の文字列を新しい値に置き換えます。  

   > [!NOTE]
   >  A4SWIFT データベース内のいずれかの Bicplus テーブルまたは独自のカスタム データベースの値を入力する必要があります。 A4SWIFT データベースは、BIC_Master_Policy.xml で既定ではありません。  

   > [!NOTE]
   >  次の文字列を二重引用符で囲まれた含まれていない必要があります。  

   |            既存の文字列            |                                                              [置換後の文字列]                                                              |
   |---------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
   |      **SQL SERVER 名を指定します。**      | 名前、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BIC を保持するデータベースを格納しています。 |
   |     **BIC データベース名を指定します。**     |                                         BIC テーブルを含むデータベースの名前。                                          |
   | **統合セキュリティを指定します。** |                                                                **SSPI**                                                                |


3. 変更されたマスター ポリシーを保存します。  

4. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**.  

5. [ようこそ] ページで、次のようにクリックします。**次**します。  

6. 展開タスク ページで、次のようにクリックします。**インポート ポリシー/ボキャブラリをファイルからデータベースに発行および**、順にクリックします**次**。  

7. ポリシー ストア ページで**SQL Server 名**を選択、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納しています。 **選択したサーバーの構成データベース**を選択します**BizTalkRuleEngineDb**、 をクリックし、**次**。  

8. インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページを参照 **<*ドライブ*\Program Files\ Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン\>\Base ポリシー**、 をクリックして**BIC_Master_Policy.xml**、 をクリックして**オープン**をクリックして**次**します。  

9. 準備完了 ページで、データを検証し、**次**します。  

10. ポリシー/ボキャブラリのインポート ページで、コマンドが成功し、クリックを確認します。**次**します。  

11. 完了ルール エンジン展開ウィザード ページで、をクリックして**このウィザードを再度実行**、順にクリックします**完了**します。  

12. [ようこそ] ページで、次のようにクリックします。**次**します。  

13. 展開タスク ページで、次のようにクリックします。**ポリシーの展開**、 をクリックし、**次**。  

14. **ポリシー ストア**] ページの [ **SQL Server 名**を選択、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納しています。 **選択したサーバーの構成データベース**を選択します**BizTalkRuleEngineDb**、 をクリックし、**次**。  

15. **ポリシーの展開**] ページで、[ **BIC_Master_Policy.1.0**、順にクリックします**次**します。  

16. **準備ができて**] ページで [**次**。  

17. ポリシーの展開 ページで、展開が成功した場合 をクリックして**次**します。 クリックして**このウィザードを再度実行**、順にクリックします**完了**します。  

18. 手順 5 ~ 17 の**BIC_Validation_Policy.xml**入力、 **BIC_Validation_Policy**の代わりに**BIC_Master_Policy**します。  

19. ルール エンジン展開ウィザードを終了します。  

20. クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。 いることを確認、**ポリシー**一覧が含まれます**BIC_Master_Policy**と**BIC_Validation_Policy** **ポリシー**します。  

21. 展開**バージョン 1.0 - 展開済み**[ **BIC_Master_Policy**、] をクリックし、 **BIC_Master_Rule**します。  

22. THEN ペインに表示されている SQL 接続のプロパティが正しいことを確認します。  

    > [!NOTE]
    >  A4SWIFT SWIFT 逆アセンブラーを使用する現在構成されている受信パイプラインをホストする BizTalk サービスを再起動するまでに、マスター BIC 検証ポリシーに加えられた変更は取得されません。 A4SWIFT は、BIC 値 BIC マスター ポリシーで指定された BIC 列に含まれているは、このパイプラインを通過するすべてのドキュメントを検証します。 この BizTalk サービス (BTSNTSvc.exe) を開始するために使用するユーザー アカウント、BIC データベースとテーブルへのアクセスが必要です。 セキュリティの向上、BIC データベースとテーブルに読み取り専用アクセスを付与することをお勧めします。  

    > [!NOTE]
    >  Message Repair and New Submission を使用している場合、InfoPath を使用する BIC 検証 (iisreset.exe を実行) して、World Wide Web 発行サービスを再起動してください。  

## <a name="see-also"></a>参照  
 [BRE ポリシーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)   
 [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)