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
# <a name="deploying-bre-rules"></a><span data-ttu-id="c374a-102">BRE ルールの展開</span><span class="sxs-lookup"><span data-stu-id="c374a-102">Deploying BRE Rules</span></span>
<span data-ttu-id="c374a-103">使用される BRE ルールを展開する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT メッセージを処理するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="c374a-103">You must deploy the BRE rules used by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] orchestrations to process SWIFT messages.</span></span>  

 <span data-ttu-id="c374a-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="c374a-104">**Summary**</span></span>  

 <span data-ttu-id="c374a-105">次のボキャブラリを公開するには。</span><span class="sxs-lookup"><span data-stu-id="c374a-105">Publish the following vocabularies:</span></span>  

- <span data-ttu-id="c374a-106">A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="c374a-106">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies.</span></span> <span data-ttu-id="c374a-107">これらにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base Policies\Vocabulary します。</span><span class="sxs-lookup"><span data-stu-id="c374a-107">These are located in *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies\Vocabulary.</span></span> <span data-ttu-id="c374a-108">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-108">Publish and deploy these using the BRE Deployment Utility.</span></span>  

  <span data-ttu-id="c374a-109">発行し、次のポリシーの展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-109">Publish and deploy the following policies:</span></span>  

- <span data-ttu-id="c374a-110">SWIFT のメッセージ スキーマの基本ポリシーには、スキーマが展開されている SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、およびネットワーク ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml) など。</span><span class="sxs-lookup"><span data-stu-id="c374a-110">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml) for deployed schemas.</span></span> <span data-ttu-id="c374a-111">これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c374a-111">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="c374a-112">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-112">Publish and deploy these using the BRE Deployment Utility.</span></span>  

- <span data-ttu-id="c374a-113">関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml および MTxxx_Validation_Policy.xml) を展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-113">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml).</span></span> <span data-ttu-id="c374a-114">これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MTxxx します。</span><span class="sxs-lookup"><span data-stu-id="c374a-114">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MTxxx.</span></span> <span data-ttu-id="c374a-115">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-115">Publish and deploy these using the BRE Deployment Utility.</span></span>  

- <span data-ttu-id="c374a-116">BIC 検証が必要な場合は、BIC 検証 (BIC_Master_Policy.xml および BIC_Validation_Policy.xml) に関連付けられているマスターと検証のポリシー。</span><span class="sxs-lookup"><span data-stu-id="c374a-116">Master and validation policies associated with BIC validation (BIC_Master_Policy.xml and BIC_Validation_Policy.xml), if BIC validation is required.</span></span> <span data-ttu-id="c374a-117">これらにある\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c374a-117">These are located in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies.</span></span> <span data-ttu-id="c374a-118">発行と、これらのポリシーを展開する前に、BIC データベース名である SQL Server の名前を持つ BIC_Master_Policy.xml をカスタマイズする必要があり、セキュリティの値を統合します。</span><span class="sxs-lookup"><span data-stu-id="c374a-118">Before publishing and deploying these policies, you must customize BIC_Master_Policy.xml with the names of the SQL Server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="c374a-119">詳細については、次を参照してください。[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。</span><span class="sxs-lookup"><span data-stu-id="c374a-119">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span> <span data-ttu-id="c374a-120">発行し、ルール エンジン展開ウィザードを使用して、これらを展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-120">Publish and deploy these using the Rules Engine Deployment Wizard.</span></span>  

### <a name="to-deploy-bre-rules"></a><span data-ttu-id="c374a-121">BRE ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="c374a-121">To deploy BRE rules</span></span>  

1.  <span data-ttu-id="c374a-122">BRE 配置ユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="c374a-122">Run the BRE Deployment Utility.</span></span> <span data-ttu-id="c374a-123">詳細については、「展開 BRE ルールすべてに 1 回」以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c374a-123">For more information, see "Deploying BRE Rules All at Once" below.</span></span> <span data-ttu-id="c374a-124">このユーティリティは発行し、次のデプロイします。</span><span class="sxs-lookup"><span data-stu-id="c374a-124">This utility will publish and deploy the following:</span></span>  

    -   <span data-ttu-id="c374a-125">A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="c374a-125">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies</span></span>  

    -   <span data-ttu-id="c374a-126">SWIFT の基本ポリシーの SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、ネットワーク ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml) などのメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="c374a-126">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml)</span></span>  

    -   <span data-ttu-id="c374a-127">関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml および MTxxx_Validation_Policy.xml) を展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-127">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml)</span></span>  

2.  <span data-ttu-id="c374a-128">SQL server, BIC データベースの名前、および統合のセキュリティの値の名前を持つ BIC_Master_Policy.xml をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="c374a-128">Customize BIC_Master_Policy.xml with the names of the SQL server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="c374a-129">詳細については、次を参照してください。[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)します。</span><span class="sxs-lookup"><span data-stu-id="c374a-129">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span>  

3.  <span data-ttu-id="c374a-130">BIC_Master_Policy.xml と BIC_Validation_Policy.xml を発行して、展開には、ルール エンジン展開ウィザードの実行 (で\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base ポリシー)。</span><span class="sxs-lookup"><span data-stu-id="c374a-130">Run the Rules Engine Deployment Wizard to publish and deploy BIC_Master_Policy.xml and   BIC_Validation_Policy.xml (in \<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies).</span></span> <span data-ttu-id="c374a-131">詳細については、「展開 BRE ルール 1 つ同時に」次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c374a-131">For more information, see "Deploying BRE Rules One at a Time" below.</span></span>  

## <a name="tools-for-deploying-the-policies"></a><span data-ttu-id="c374a-132">ポリシーを展開するためのツール</span><span class="sxs-lookup"><span data-stu-id="c374a-132">Tools for Deploying the Policies</span></span>  
 <span data-ttu-id="c374a-133">ボキャブラリを公開し、ポリシーを展開する最も簡単な方法は、A4SWIFT ソフトウェア開発キット (SDK) をビジネス ルール エンジン (BRE) 配置ユーティリティを使用してです。</span><span class="sxs-lookup"><span data-stu-id="c374a-133">The easiest way to publish the vocabularies and deploy the policies is by using the Business Rule Engine (BRE) Deployment Utility in the A4SWIFT Software Development Kit (SDK).</span></span> <span data-ttu-id="c374a-134">使用して行うようにも、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]時に、同じタスクの 1 つボキャブラリまたはポリシーを実行します。 ルール エンジン展開ウィザード。</span><span class="sxs-lookup"><span data-stu-id="c374a-134">You can also do so by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Rule Engine Deployment Wizard, which performs the same task one vocabulary or policy at a time.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c374a-135">BRE 配置ユーティリティをデプロイしません BIC マスター ポリシーおよび BIC 検証ポリシー。</span><span class="sxs-lookup"><span data-stu-id="c374a-135">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="c374a-136">ルール エンジン展開ウィザードを使用してこれらを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c374a-136">You must deploy these using the Rule Engine Deployment wizard.</span></span>  

### <a name="deploying-bre-rules-all-at-once"></a><span data-ttu-id="c374a-137">BRE ルールをすべて一度に展開します。</span><span class="sxs-lookup"><span data-stu-id="c374a-137">Deploying BRE Rules All at Once</span></span>  
 <span data-ttu-id="c374a-138">ビジネス ルール エンジン (BRE) 配置ユーティリティは、1 つの手順で、一連の発行および展開のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c374a-138">The Business Rule Engine (BRE) Deployment Utility performs a series of publishing and deployment tasks in one step.</span></span> <span data-ttu-id="c374a-139">必要がありますを再実行する配置ユーティリティいつをプロジェクトにスキーマを追加することです。</span><span class="sxs-lookup"><span data-stu-id="c374a-139">You must rerun the deployment utility any time that you add a schema to your project.</span></span>  

##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a><span data-ttu-id="c374a-140">BRE 配置ユーティリティを使用して BRE ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="c374a-140">To deploy BRE rules using the BRE Deployment Utility</span></span>  

1. <span data-ttu-id="c374a-141">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**.</span><span class="sxs-lookup"><span data-stu-id="c374a-141">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  

2. <span data-ttu-id="c374a-142">BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-142">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  

3. <span data-ttu-id="c374a-143">.NET グローバル アセンブリ キャッシュ ダイアログ ボックスに展開されたプロジェクトのアセンブリを選択します。 [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-143">In the .NET Global Assembly Cache dialog box, select the project assembly that you deployed in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md), and then click **OK**.</span></span>  

4. <span data-ttu-id="c374a-144">BRE 配置ユーティリティ] ダイアログ ボックスで、[**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-144">In the BRE Deployment Utility dialog box, click **Deploy**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c374a-145">そのアセンブリを展開するスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。</span><span class="sxs-lookup"><span data-stu-id="c374a-145">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="c374a-146">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c374a-146">When complete, the BRE Deployment Utility displays the following message:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c374a-147">"デプロイが完了しました。</span><span class="sxs-lookup"><span data-stu-id="c374a-147">"Deployment has completed.</span></span> <span data-ttu-id="c374a-148">ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"</span><span class="sxs-lookup"><span data-stu-id="c374a-148">View the log file or Business Rule Composer for details."</span></span>  

5. <span data-ttu-id="c374a-149">BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c374a-149">Close the BRE Deployment Utility dialog box.</span></span>  

6. <span data-ttu-id="c374a-150">開いている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="c374a-150">Open [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer.</span></span> <span data-ttu-id="c374a-151">参照\<*ドライブ*\>: \Documents and バックアップ データの場合、そのドライブに表示される BREDeploymentLog.txt をログ ファイルことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c374a-151">Browse to \<*drive*\>:\Documents and Settings\All Users\Application Data, and confirm that the log file BREDeploymentLog.txt appears in that drive.</span></span>  

7. <span data-ttu-id="c374a-152">ルール エンジン更新サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c374a-152">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="c374a-153">クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。</span><span class="sxs-lookup"><span data-stu-id="c374a-153">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="c374a-154">**サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-154">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  

### <a name="deploying-bre-rules-one-at-a-time"></a><span data-ttu-id="c374a-155">一度に BRE ルール 1 の展開</span><span class="sxs-lookup"><span data-stu-id="c374a-155">Deploying BRE Rules One at a Time</span></span>  
 <span data-ttu-id="c374a-156">ルール エンジン展開ウィザードを使用して、ボキャブラリを公開し、一度に 1 つのポリシーをデプロイすることができます。</span><span class="sxs-lookup"><span data-stu-id="c374a-156">You can use the Rules Engine Deployment Wizard to publish vocabularies and deploy policies one at a time.</span></span> <span data-ttu-id="c374a-157">ボキャブラリにはこのプロセスには、インポートして、1 つのステップ内のファイルからデータベースにボキャブラリを公開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c374a-157">For a vocabulary, this process involves importing and publishing the vocabulary to the database from a file in one step.</span></span> <span data-ttu-id="c374a-158">ポリシーをインポートおよび 1 つの手順で、ポリシーをパブリッシュし、別のステップに展開するプロセスします。</span><span class="sxs-lookup"><span data-stu-id="c374a-158">For a policy, the process involves importing and publishing the policy in one step, and then deploying it in another step.</span></span>  

##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a><span data-ttu-id="c374a-159">ルール エンジン展開ウィザードを使用して BRE ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="c374a-159">To deploy BRE rules Using the Rules Engine Deployment Wizard</span></span>  

1. <span data-ttu-id="c374a-160">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール エンジン展開ウィザード**.</span><span class="sxs-lookup"><span data-stu-id="c374a-160">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  

2. <span data-ttu-id="c374a-161">ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-161">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  

3. <span data-ttu-id="c374a-162">展開タスク ページで、次のようにクリックします。**インポート ポリシー/ボキャブラリをファイルからデータベースに発行および**、順にクリックします**次**。</span><span class="sxs-lookup"><span data-stu-id="c374a-162">On the Deployment Task page, click **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  

4. <span data-ttu-id="c374a-163">ポリシー ストア ページで、 **SQL サーバー名 ボックス**のサーバーを選択し、**選択したサーバーの構成データベース**一覧で、 **BizTalkRuleEngineDb**。</span><span class="sxs-lookup"><span data-stu-id="c374a-163">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="c374a-164">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c374a-164">Click **Next**.</span></span>  

5. <span data-ttu-id="c374a-165">インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、次のようにクリックします。**参照**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-165">On the Import Rules Engine Policy/Vocabulary file page, click **Browse**.</span></span>  

6. <span data-ttu-id="c374a-166">[ファイル] ページで、ポリシーのインポートで、**検索**ドロップダウン リスト、ボキャブラリまたはポリシーに応じて、次のフォルダーのいずれかに移動。</span><span class="sxs-lookup"><span data-stu-id="c374a-166">On the Import Policy from file page, in the **Look in** drop-down list, move to one of the following folders, depending upon the vocabulary or policy:</span></span>  

   -   <span data-ttu-id="c374a-167">\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>A4SWIFT_CodeLists.xml の \Base Policies\VocabularyA4SWIFT_Functions.xml</span><span class="sxs-lookup"><span data-stu-id="c374a-167">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies\Vocabulary for A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml</span></span>  

   -   <span data-ttu-id="c374a-168">\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base SWIFT_Reference_Policy.xml、SWIFT_ のポリシーPartyIdentifier_Policy.xml、ネットワーク ルール ポリシー、BIC_Master_Policy.xml、および BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="c374a-168">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Policies for SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, network rule policies, BIC_Master_Policy.xml, and BIC_Validation_Policy.xml</span></span>  

   -   <span data-ttu-id="c374a-169">\<ドライブ\>: Microsoft BizTalk Accelerator for SWIFT \Program Files\\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MTxxx マスターと検証ポリシー展開済みのメッセージ スキーマに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="c374a-169">\<drive\>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category 1\MTxxx for the master and validation policies associated with deployed message schemas</span></span>  

7. <span data-ttu-id="c374a-170">展開、およびクリックするポリシーを選択して**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-170">Select the policy that you want to deploy, and then click **Open**.</span></span>  

8. <span data-ttu-id="c374a-171">インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、次のようにクリックします。**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-171">On the Import Rules Engine Policy/Vocabulary file page, click **Next**.</span></span>  

9. <span data-ttu-id="c374a-172">準備完了 ページで、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-172">On the Ready page, click **Next**.</span></span>  

10. <span data-ttu-id="c374a-173">ポリシー/ボキャブラリのインポート ページで、コマンドが成功し、クリックを確認します。**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-173">On the Importing Policy/Vocabulary page, verify that the command succeeded, and then click **Next**.</span></span>  

11. <span data-ttu-id="c374a-174">完了のポリシーを展開するかどうか、ルール エンジン展開ウィザード ページ をクリックして**このウィザードを再度実行**、順にクリックします**完了**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-174">If you want to deploy a policy, on the Completing the Rules Engine Deployment Wizard page, click **Run this Wizard again**, and then click **Finish**.</span></span>  

12. <span data-ttu-id="c374a-175">ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-175">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  

13. <span data-ttu-id="c374a-176">展開タスク ページで、次のようにクリックします。**ポリシーの展開**、 をクリックし、**次**。</span><span class="sxs-lookup"><span data-stu-id="c374a-176">On the Deployment Task page, click **Deploy Policy**, and then click **Next**.</span></span>  

14. <span data-ttu-id="c374a-177">ポリシー ストア ページで、 **SQL サーバー名 ボックス**のサーバーを選択し、**選択したサーバーの構成データベース**一覧で、 **BizTalkRuleEngineDb**。</span><span class="sxs-lookup"><span data-stu-id="c374a-177">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="c374a-178">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c374a-178">Click **Next**.</span></span>  

15. <span data-ttu-id="c374a-179">ポリシーの展開 ページで、場合は、横にある下矢印をクリックして、**ルール エンジン ポリシー**テキスト ボックスが発行したポリシーを選択し、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-179">On the Deploy Policy page, click the down arrow next to the **Rules Engine Policy** text box, select the policy you just published, and then click **Next**.</span></span>  

16. <span data-ttu-id="c374a-180">準備完了 ページで、**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-180">On the Ready page, click **Next**.</span></span>  

17. <span data-ttu-id="c374a-181">**ポリシー/ボキャブラリのインポート** ページで、コマンドが成功したことを確認 をクリックして**次**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-181">On the **Importing Policy/Vocabulary** page, verify that the command succeeded, and then click **Next**.</span></span>  

18. <span data-ttu-id="c374a-182">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c374a-182">Click **Finish**.</span></span>  

19. <span data-ttu-id="c374a-183">再起動、**ルール エンジン更新サービス**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-183">Restart the **Rule Engine Update Service**.</span></span> <span data-ttu-id="c374a-184">クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。</span><span class="sxs-lookup"><span data-stu-id="c374a-184">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="c374a-185">**サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="c374a-185">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>
