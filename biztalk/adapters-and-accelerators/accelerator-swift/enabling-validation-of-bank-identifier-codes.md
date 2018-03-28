---
title: 銀行識別コードの検証を有効化 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3868906d4f61242b1344a02147e4e71307d67d3
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="enabling-validation-of-bank-identifier-codes"></a>銀行識別コードの検証を有効にします。
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] スキーマでは、SWIFT インターチェンジのドキュメントで指定された銀行識別コード (BICs) が SWIFT 定義 BIC データ形式に準拠していることを確認してください。 A4SWIFT は、データベース内の顧客が指定した BIC リストに対して BICs の検証もサポートします。  
  
 BRE 検証を有効にして、BIC 検証を有効にする場合は、この検証を実行することができます。  
  
 既定では、A4SWIFT セットアップには、BRE の検証が無効にします。 有効にするには、A4SWIFT 逆アセンブラーを使用する受信パイプラインが true と BRE 検証の構成パラメーターを設定する必要があります。 検証に使用するメッセージをマスター ポリシーと特定の検証ポリシーを展開する BRE 配置ユーティリティも実行して必要があります (MT*xxx*_Master_policy.xml と MT*xxx*_Validation_Policy.xml)。 詳細については、次を参照してください。 [BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)と[BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)です。  
  
 BRE の検証を有効にした後に行う必要がありますを発行して (BIC_Master_Policy.xml および BIC_Validation_Policy.xml) 両方の BIC 検証ポリシーの展開ルール エンジン展開ウィザードを使用します。 これを行うには、前に、次の操作を行う必要があります。  
  
-   データベースに SWIFT から BIC 値を設定します。 Bicplus テーブルを使用するには、A4SWIFT セットアップによってインストールされる、A4SWIFT データベースにまたは、独自のカスタム データベースを使用することができます。 詳細については、次を参照してください。 [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)です。  
  
-   BIC データベースを設定し、BIC マスター ポリシーをカスタマイズすることにより BIC 検証を有効にします。 次の手順を参照してください。  
  
 BIC 検証が必要ない場合はパフォーマンス向上のため BIC 検証ポリシーを展開する必要がありません。  
  
> [!NOTE]
>  発行および A4SWIFT_Codelist と A4SWIFT_Functions ボキャブラリを公開した場合にのみ、BIC 検証ポリシーを展開できます。 SWIFTSchemas アセンブリで BRE 配置ユーティリティを実行してこれらのボキャブラリを公開します。 詳細については、次を参照してください。[レッスン 1: 関連するビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)です。  
  
### <a name="to-customize-the-bic-master-policy"></a>BIC マスター ポリシーをカスタマイズするには  
  
1.  (メモ帳など)、XML エディターを開きを参照 **<*ドライブ*プログラム files \ Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Base ポリシー**です。  
  
2.  開いている**BIC_Master_Policy.xml**です。 次の既存の文字列を新しい値に置き換えます。  
  
    > [!NOTE]
    >  A4SWIFT データベースで Bicplus テーブルまたはカスタム データベースの値を入力する必要があります。 A4SWIFT データベースは、BIC_Master_Policy.xml で既定ではありません。  
  
    > [!NOTE]
    >  次の文字列を二重引用符で囲まれた含まれていない必要があります。  
  
    |既存の文字列|[置換後の文字列]|  
    |---------------------|------------------|  
    |**SQL サーバー名を指定します。**|名前、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BIC を保持しているデータベースを格納します。|  
    |**BIC データベース名を指定します。**|BIC テーブルを含むデータベースの名前。|  
    |**統合セキュリティの値を指定します。**|**SSPI**|  
  
3.  変更のマスター ポリシーを保存します。  
  
4.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**ビジネス ルール エンジン展開ウィザード**.  
  
5.  [ようこそ] ページで、をクリックして**次**です。  
  
6.  展開タスク ページで、をクリックして**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、クリックして**次**です。  
  
7.  ポリシー ストア] ページで、[ **SQL Server 名**を選択、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納します。 **選択したサーバーの構成データベース** **BizTalkRuleEngineDb**、順にクリック**次へ**です。  
  
8.  インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページを参照 **<*ドライブ*\Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン\>\Base ポリシー**をクリックして**BIC_Master_Policy.xml**、 をクリックして**開く**をクリックして**次**です。  
  
9. 準備完了 ページで、データを確認し、をクリックして**次**です。  
  
10. [ポリシー/ボキャブラリのインポート] ページで、コマンドが成功し、をクリックすることを確認**次**です。  
  
11. 完了ルール エンジン展開ウィザード ページで、をクリックして**このウィザードを再度実行**、順にクリック**完了**。  
  
12. [ようこそ] ページで、をクリックして**次**です。  
  
13. 展開タスク ページで、をクリックして**ポリシーの展開**、クリックして**次**です。  
  
14. **ポリシー ストア**] ページの [ **SQL Server 名**、select、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納します。 **選択したサーバーの構成データベース** **BizTalkRuleEngineDb**、順にクリック**次へ**です。  
  
15. **ポリシーの展開**] ページで、[ **BIC_Master_Policy.1.0**、順にクリック**次**です。  
  
16. **準備ができて** ] ページで [ **次**します。  
  
17. [ポリシーの配置] ページで、展開が成功した場合、をクリックして**次**です。 をクリックして**このウィザードを再度実行**、順にクリック**完了**です。  
  
18. 手順 5. ~ 17 の**BIC_Validation_Policy.xml**入力、 **BIC_Validation_Policy**の代わりに**BIC_Master_Policy**です。  
  
19. ルール エンジン展開ウィザードを終了します。  
  
20. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。 いることを確認、**ポリシー**一覧が含まれます**BIC_Master_Policy**と**BIC_Validation_Policy** **ポリシー**です。  
  
21. 展開**バージョン 1.0 - 展開済み** **BIC_Master_Policy**、クリックして**BIC_Master_Rule**です。  
  
22. [THEN] ペインに表示されている SQL 接続のプロパティが正しいことを確認します。  
  
    > [!NOTE]
    >  A4SWIFT SWIFT の逆アセンブラーを使用する現在構成されている受信パイプラインをホストする BizTalk サービスを再起動するまでに、マスター BIC 検証ポリシーに加えられた変更は取得されません。 A4SWIFT は、BIC マスター ポリシーで指定された BIC 列に含まれている BIC 値については、このパイプラインを通過するすべてのドキュメントを検証します。 この BizTalk サービス (BTSNTSvc.exe) を開始するために使用するユーザー アカウント、BIC データベースとテーブルへのアクセスが必要です。 セキュリティの向上、BIC データベースおよびテーブルへの読み取り専用のアクセスを付与することをお勧めします。  
  
    > [!NOTE]
    >  Message Repair and New Submission を使用している場合、InfoPath から作業する BIC 検証用 (を実行して iisreset.exe)、World Wide Web 発行サービスを再起動してください。  
  
## <a name="see-also"></a>参照  
 [BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)   
 [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)