---
title: "銀行識別コードの検証を有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Bank Identifier Code (BIC), enabling
ms.assetid: d268a892-f304-44cb-b590-28ef359c8d99
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a9869bdeaeed638c2cc8c3bf3ace869a0124f73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-validation-of-bank-identifier-codes"></a><span data-ttu-id="dcfa3-102">銀行識別コードの検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-102">Enabling Validation of Bank Identifier Codes</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="dcfa3-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]スキーマでは、SWIFT インターチェンジのドキュメントで指定された銀行識別コード (BICs) が SWIFT 定義 BIC データ形式に準拠していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] schemas ensure that the Bank Identifier Codes (BICs) specified in the SWIFT interchange document conform to the SWIFT-defined BIC data format.</span></span> <span data-ttu-id="dcfa3-104">A4SWIFT は、データベース内の顧客が指定した BIC リストに対して BICs の検証もサポートします。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-104">A4SWIFT also supports validating the BICs against a customer-specified BIC list in a database.</span></span>  
  
 <span data-ttu-id="dcfa3-105">BRE 検証を有効にして、BIC 検証を有効にする場合は、この検証を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-105">You can perform this validation if you have enabled BRE validation and then enabled BIC validation.</span></span>  
  
 <span data-ttu-id="dcfa3-106">既定では、A4SWIFT セットアップには、BRE の検証が無効にします。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-106">By default, A4SWIFT Setup disables BRE validation.</span></span> <span data-ttu-id="dcfa3-107">有効にするには、A4SWIFT 逆アセンブラーを使用する受信パイプラインが true と BRE 検証の構成パラメーターを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-107">To enable it, you must set the BRE validation configuration parameter to true for a receive pipeline that uses the A4SWIFT disassembler.</span></span> <span data-ttu-id="dcfa3-108">検証に使用するメッセージをマスター ポリシーと特定の検証ポリシーを展開する BRE 配置ユーティリティも実行して必要があります (MT*xxx*_Master_policy.xml と MT*xxx*_Validation_Policy.xml)。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-108">You must also run the BRE Deployment Utility to deploy the master policy and validation policy specific to the message to be validated (MT*xxx*_Master_policy.xml and MT*xxx*_Validation_Policy.xml).</span></span> <span data-ttu-id="dcfa3-109">詳細については、次を参照してください。 [BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)と[BRE ルールの展開](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-109">For more information, see [Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) and [Deploying BRE Rules](../../adapters-and-accelerators/accelerator-swift/deploying-bre-rules.md).</span></span>  
  
 <span data-ttu-id="dcfa3-110">BRE の検証を有効にした後に行う必要がありますを発行して (BIC_Master_Policy.xml および BIC_Validation_Policy.xml) 両方の BIC 検証ポリシーの展開ルール エンジン展開ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-110">After you have enabled BRE validation, you must use publish and deploy both BIC validation policies (BIC_Master_Policy.xml and BIC_Validation_Policy.xml) using the Rules Engine Deployment Wizard.</span></span> <span data-ttu-id="dcfa3-111">これを行うには、前に、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-111">Before doing so, you must do the following:</span></span>  
  
-   <span data-ttu-id="dcfa3-112">データベースに SWIFT から BIC 値を設定します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-112">Populate the database with BIC values from SWIFT.</span></span> <span data-ttu-id="dcfa3-113">Bicplus テーブルを使用するには、A4SWIFT セットアップによってインストールされる、A4SWIFT データベースにまたは、独自のカスタム データベースを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-113">You can use the Bicplus table in the A4SWIFT database, which is installed by A4SWIFT Setup, or you can use your own custom database.</span></span> <span data-ttu-id="dcfa3-114">詳細については、次を参照してください。 [A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-114">For more information, see [Managing the Bicplus Table in the A4SWIFT Database](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md).</span></span>  
  
-   <span data-ttu-id="dcfa3-115">BIC データベースを設定し、BIC マスター ポリシーをカスタマイズすることにより BIC 検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-115">Set the BIC database and enable BIC validation by customizing the BIC Master Policy.</span></span> <span data-ttu-id="dcfa3-116">次の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-116">See the procedure below.</span></span>  
  
 <span data-ttu-id="dcfa3-117">BIC 検証が必要ない場合はパフォーマンス向上のため BIC 検証ポリシーを展開する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-117">For better performance, you should not deploy the BIC validation policies if BIC validation is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcfa3-118">発行および A4SWIFT_Codelist と A4SWIFT_Functions ボキャブラリを公開した場合にのみ、BIC 検証ポリシーを展開できます。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-118">You can publish and deploy the BIC validation policy only if you have published the A4SWIFT_Codelist and A4SWIFT_Functions vocabularies.</span></span> <span data-ttu-id="dcfa3-119">SWIFTSchemas アセンブリで BRE 配置ユーティリティを実行してこれらのボキャブラリを公開します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-119">Publish these vocabularies by running the BRE Deployment Utility on the SWIFTSchemas assembly.</span></span> <span data-ttu-id="dcfa3-120">詳細については、次を参照してください。[レッスン 1: 関連するビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-120">For more information, see [Lesson 1: Deploying the Related Business Rules](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md).</span></span>  
  
### <a name="to-customize-the-bic-master-policy"></a><span data-ttu-id="dcfa3-121">BIC マスター ポリシーをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="dcfa3-121">To customize the BIC Master Policy</span></span>  
  
1.  <span data-ttu-id="dcfa3-122">(メモ帳など)、XML エディターを開きを参照  **<*ドライブ*プログラム files \ Microsoft BizTalk Accelerator for SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base ポリシー * *。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-122">Open an XML editor (such as Notepad), and browse to **<*drive*Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies**.</span></span>  
  
2.  <span data-ttu-id="dcfa3-123">開いている**BIC_Master_Policy.xml**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-123">Open **BIC_Master_Policy.xml**.</span></span> <span data-ttu-id="dcfa3-124">次の既存の文字列を新しい値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-124">Replace the following existing strings with new values.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dcfa3-125">A4SWIFT データベースで Bicplus テーブルまたはカスタム データベースの値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-125">You must enter values for either the Bicplus table in the A4SWIFT database or your own custom database.</span></span> <span data-ttu-id="dcfa3-126">A4SWIFT データベースは、BIC_Master_Policy.xml で既定ではありません。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-126">The A4SWIFT database is not the default in BIC_Master_Policy.xml.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dcfa3-127">次の文字列を二重引用符で囲まれた含まれていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-127">The following strings must not be contained within double quotes.</span></span>  
  
    |<span data-ttu-id="dcfa3-128">既存の文字列</span><span class="sxs-lookup"><span data-stu-id="dcfa3-128">Existing string</span></span>|<span data-ttu-id="dcfa3-129">[置換後の文字列]</span><span class="sxs-lookup"><span data-stu-id="dcfa3-129">Replace with</span></span>|  
    |---------------------|------------------|  
    |<span data-ttu-id="dcfa3-130">**SQL サーバー名を指定します。**</span><span class="sxs-lookup"><span data-stu-id="dcfa3-130">**SPECIFY SQL SERVER NAME**</span></span>|<span data-ttu-id="dcfa3-131">名前、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BIC を保持しているデータベースを格納します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-131">The name of the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] containing the database holding the BIC.</span></span>|  
    |<span data-ttu-id="dcfa3-132">**BIC データベース名を指定します。**</span><span class="sxs-lookup"><span data-stu-id="dcfa3-132">**SPECIFY BIC DATABASE NAME**</span></span>|<span data-ttu-id="dcfa3-133">BIC テーブルを含むデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-133">The name of the database that contains the BIC table.</span></span>|  
    |<span data-ttu-id="dcfa3-134">**統合セキュリティの値を指定します。**</span><span class="sxs-lookup"><span data-stu-id="dcfa3-134">**SPECIFY INTEGRATED SECURITY VALUE**</span></span>|<span data-ttu-id="dcfa3-135">**SSPI**</span><span class="sxs-lookup"><span data-stu-id="dcfa3-135">**SSPI**</span></span>|  
  
3.  <span data-ttu-id="dcfa3-136">変更のマスター ポリシーを保存します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-136">Save the modified Master Policy.</span></span>  
  
4.  <span data-ttu-id="dcfa3-137">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**ビジネス ルール エンジン展開ウィザード**.</span><span class="sxs-lookup"><span data-stu-id="dcfa3-137">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
5.  <span data-ttu-id="dcfa3-138">[ようこそ] ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-138">On the Welcome page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="dcfa3-139">展開タスク ページで、をクリックして**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-139">On the Deployment Task page, click **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="dcfa3-140">ポリシー ストア] ページで、[ **SQL Server 名**を選択、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-140">On the Policy Store page, in **SQL Server Name**, select the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that contains your BizTalk databases.</span></span> <span data-ttu-id="dcfa3-141">**選択したサーバーの構成データベース** **BizTalkRuleEngineDb**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-141">In **Configuration Database on selected server**, select **BizTalkRuleEngineDb**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="dcfa3-142">インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページを参照  **<*ドライブ*\Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFTMessages\A4SWIFT SRG\<バージョン > \Base * *、ポリシーのをクリックして**BIC_Master_Policy.xml**、 をクリックして**開く**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-142">In the Import Rules Engine Policy/Vocabulary file page, browse to **<*drive*\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies**, click **BIC_Master_Policy.xml**, click **Open**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="dcfa3-143">準備完了 ページで、データを確認し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-143">On the Ready page, verify the data, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="dcfa3-144">[ポリシー/ボキャブラリのインポート] ページで、コマンドが成功し、をクリックすることを確認**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-144">On the Importing Policy/Vocabulary page, verify that the command succeeded, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="dcfa3-145">完了ルール エンジン展開ウィザード ページで、をクリックして**このウィザードを再度実行**、順にクリック**完了**。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-145">On the Completing the Rules Engine Deployment Wizard page, click **Run this wizard again**, and then click **Finish**.</span></span>  
  
12. <span data-ttu-id="dcfa3-146">[ようこそ] ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-146">On the Welcome page, click **Next**.</span></span>  
  
13. <span data-ttu-id="dcfa3-147">展開タスク ページで、をクリックして**ポリシーの展開**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-147">On the Deployment Task page, click **Deploy Policy**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="dcfa3-148">**ポリシー ストア**] ページの [ **SQL Server 名**、select、 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] BizTalk データベースを格納します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-148">On the **Policy Store** page, in **SQL Server Name**, select the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] that contains your BizTalk databases.</span></span> <span data-ttu-id="dcfa3-149">**選択したサーバーの構成データベース** **BizTalkRuleEngineDb**、順にクリック**次へ**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-149">In **Configuration Database on selected server**, select **BizTalkRuleEngineDb**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="dcfa3-150">**ポリシーの展開**] ページで、[ **BIC_Master_Policy.1.0**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-150">On the **Deploy Policy** page, select **BIC_Master_Policy.1.0**, and then click **Next**.</span></span>  
  
16. <span data-ttu-id="dcfa3-151">**準備** ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-151">On the **Ready** page, click **Next**.</span></span>  
  
17. <span data-ttu-id="dcfa3-152">[ポリシーの配置] ページで、展開が成功した場合、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-152">On the Deploying Policy page, if the deployment has succeeded, click **Next**.</span></span> <span data-ttu-id="dcfa3-153">をクリックして**このウィザードを再度実行**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-153">Click **Run this wizard again**, and then click **Finish**.</span></span>  
  
18. <span data-ttu-id="dcfa3-154">手順 5. ~ 17 の**BIC_Validation_Policy.xml**入力、 **BIC_Validation_Policy**の代わりに**BIC_Master_Policy**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-154">Repeat steps 5 through 17 for **BIC_Validation_Policy.xml**, entering **BIC_Validation_Policy** instead of **BIC_Master_Policy**.</span></span>  
  
19. <span data-ttu-id="dcfa3-155">ルール エンジン展開ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-155">Exit the Rules Engine Deployment Wizard.</span></span>  
  
20. <span data-ttu-id="dcfa3-156">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-156">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="dcfa3-157">いることを確認、**ポリシー**一覧が含まれます**BIC_Master_Policy**と**BIC_Validation_Policy** **ポリシー**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-157">Verify that the **Policies** list includes **BIC_Master_Policy** and **BIC_Validation_Policy** under **Policies**.</span></span>  
  
21. <span data-ttu-id="dcfa3-158">展開**バージョン 1.0 - 展開済み** **BIC_Master_Policy**、クリックして**BIC_Master_Rule**です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-158">Expand **Version 1.0 - Deployed** under **BIC_Master_Policy**, and then click **BIC_Master_Rule**.</span></span>  
  
22. <span data-ttu-id="dcfa3-159">[THEN] ペインに表示されている SQL 接続のプロパティが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-159">In the THEN pane, verify that the SQL Connection properties listed are correct.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dcfa3-160">A4SWIFT SWIFT の逆アセンブラーを使用する現在構成されている受信パイプラインをホストする BizTalk サービスを再起動するまでに、マスター BIC 検証ポリシーに加えられた変更は取得されません。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-160">A4SWIFT does not pick up changes made to the master BIC validation policy until you restart the BizTalk service that hosts the receive pipeline that is currently configured to use the SWIFT disassembler.</span></span> <span data-ttu-id="dcfa3-161">A4SWIFT は、BIC マスター ポリシーで指定された BIC 列に含まれている BIC 値については、このパイプラインを通過するすべてのドキュメントを検証します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-161">A4SWIFT validates all documents that pass through this pipeline for the BIC values that are contained in the BIC column specified in the BIC master policy.</span></span> <span data-ttu-id="dcfa3-162">この BizTalk サービス (BTSNTSvc.exe) を開始するために使用するユーザー アカウント、BIC データベースとテーブルへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-162">The user account used to start this BizTalk service (BTSNTSvc.exe) must have access to the BIC database and table.</span></span> <span data-ttu-id="dcfa3-163">セキュリティの向上、BIC データベースおよびテーブルへの読み取り専用のアクセスを付与することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-163">For better security, it is recommended that you grant read-only access to the BIC database and table.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dcfa3-164">Message Repair and New Submission を使用している場合、InfoPath から作業する BIC 検証用 (を実行して iisreset.exe)、World Wide Web 発行サービスを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-164">If you are using Message Repair and New Submission, the World Wide Web Publishing service must be restarted (by running iisreset.exe) for BIC validation to work from InfoPath.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfa3-165">参照</span><span class="sxs-lookup"><span data-stu-id="dcfa3-165">See Also</span></span>  
 <span data-ttu-id="dcfa3-166">[BRE ポリシーの扱い](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) </span><span class="sxs-lookup"><span data-stu-id="dcfa3-166">[Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md) </span></span>  
 [<span data-ttu-id="dcfa3-167">A4SWIFT データベース内の Bicplus テーブルを管理します。</span><span class="sxs-lookup"><span data-stu-id="dcfa3-167">Managing the Bicplus Table in the A4SWIFT Database</span></span>](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)