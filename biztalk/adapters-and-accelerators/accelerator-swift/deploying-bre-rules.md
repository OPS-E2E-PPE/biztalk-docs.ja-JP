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
# <a name="deploying-bre-rules"></a><span data-ttu-id="bc918-102">BRE のルールの展開</span><span class="sxs-lookup"><span data-stu-id="bc918-102">Deploying BRE Rules</span></span>
<span data-ttu-id="bc918-103">使用される BRE 規則を展開する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]SWIFT メッセージを処理するオーケストレーションです。</span><span class="sxs-lookup"><span data-stu-id="bc918-103">You must deploy the BRE rules used by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] orchestrations to process SWIFT messages.</span></span>  
  
 <span data-ttu-id="bc918-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="bc918-104">**Summary**</span></span>  
  
 <span data-ttu-id="bc918-105">次のボキャブラリを公開するには。</span><span class="sxs-lookup"><span data-stu-id="bc918-105">Publish the following vocabularies:</span></span>  
  
-   <span data-ttu-id="bc918-106">A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="bc918-106">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies.</span></span> <span data-ttu-id="bc918-107">これらに*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base Policies\ボキャブラリです。</span><span class="sxs-lookup"><span data-stu-id="bc918-107">These are located in *\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies\Vocabulary.</span></span> <span data-ttu-id="bc918-108">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-108">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
 <span data-ttu-id="bc918-109">発行して、次のポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-109">Publish and deploy the following policies:</span></span>  
  
-   <span data-ttu-id="bc918-110">SWIFT のメッセージ スキーマの基本ポリシーには、スキーマが展開されているの SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、およびネットワーク ルール ポリシー (SWIFT_NetworkRulexxx_Policy.xml) を含むです。</span><span class="sxs-lookup"><span data-stu-id="bc918-110">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml) for deployed schemas.</span></span> <span data-ttu-id="bc918-111">これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base ポリシー。</span><span class="sxs-lookup"><span data-stu-id="bc918-111">These are located in \<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies.</span></span> <span data-ttu-id="bc918-112">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-112">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
-   <span data-ttu-id="bc918-113">関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml と MTxxx_Validation_Policy.xml) を展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-113">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml).</span></span> <span data-ttu-id="bc918-114">これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category 1\MTxxx です。</span><span class="sxs-lookup"><span data-stu-id="bc918-114">These are located in \<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Category 1\MTxxx.</span></span> <span data-ttu-id="bc918-115">発行し、BRE 配置ユーティリティを使用してこれらを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-115">Publish and deploy these using the BRE Deployment Utility.</span></span>  
  
-   <span data-ttu-id="bc918-116">マスターおよび検証ポリシーは BIC 検証が必要な場合は、BIC 検証 (BIC_Master_Policy.xml と BIC_Validation_Policy.xml) に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="bc918-116">Master and validation policies associated with BIC validation (BIC_Master_Policy.xml and BIC_Validation_Policy.xml), if BIC validation is required.</span></span> <span data-ttu-id="bc918-117">これらに\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base ポリシー。</span><span class="sxs-lookup"><span data-stu-id="bc918-117">These are located in \<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies.</span></span> <span data-ttu-id="bc918-118">発行し、これらのポリシーを展開する、前に、BIC データベース名、SQL Server の名前を持つ BIC_Master_Policy.xml をカスタマイズする必要があり、セキュリティの値を統合します。</span><span class="sxs-lookup"><span data-stu-id="bc918-118">Before publishing and deploying these policies, you must customize BIC_Master_Policy.xml with the names of the SQL Server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="bc918-119">詳細については、次を参照してください。[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc918-119">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span> <span data-ttu-id="bc918-120">発行して、ルール エンジン展開ウィザードを使用して、これらを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-120">Publish and deploy these using the Rules Engine Deployment Wizard.</span></span>  
  
### <a name="to-deploy-bre-rules"></a><span data-ttu-id="bc918-121">BRE のルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="bc918-121">To deploy BRE rules</span></span>  
  
1.  <span data-ttu-id="bc918-122">BRE 配置ユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc918-122">Run the BRE Deployment Utility.</span></span> <span data-ttu-id="bc918-123">詳細については、「展開 BRE 規則すべてに 1 回」以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc918-123">For more information, see "Deploying BRE Rules All at Once" below.</span></span> <span data-ttu-id="bc918-124">このユーティリティは、発行され、次が展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-124">This utility will publish and deploy the following:</span></span>  
  
    -   <span data-ttu-id="bc918-125">A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="bc918-125">A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies</span></span>  
  
    -   <span data-ttu-id="bc918-126">メッセージ スキーマ、SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml、ネットワークなどの基本 SWIFT のポリシー ルールのポリシー (SWIFT_NetworkRulexxx_Policy.xml)</span><span class="sxs-lookup"><span data-stu-id="bc918-126">SWIFT base policies for message schema, including SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, and network rule policies (SWIFT_NetworkRulexxx_Policy.xml)</span></span>  
  
    -   <span data-ttu-id="bc918-127">関連付けられているマスターと検証のポリシーは、メッセージ スキーマ (MTxxx_Master_Policy.xml と MTxxx_Validation_Policy.xml) を展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-127">Master and validation policies associated with deployed message schemas (MTxxx_Master_Policy.xml and MTxxx_Validation_Policy.xml)</span></span>  
  
2.  <span data-ttu-id="bc918-128">SQL server, BIC データベースの名前と、統合セキュリティの値の名前を持つ BIC_Master_Policy.xml をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="bc918-128">Customize BIC_Master_Policy.xml with the names of the SQL server, the BIC database name, and integrated security value.</span></span> <span data-ttu-id="bc918-129">詳細については、次を参照してください。[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)です。</span><span class="sxs-lookup"><span data-stu-id="bc918-129">For more information, see [Enabling Validation of Bank Identifier Codes](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md).</span></span>  
  
3.  <span data-ttu-id="bc918-130">BIC_Master_Policy.xml と BIC_Validation_Policy.xml を発行して、展開には、ルール エンジン展開ウィザードを実行 (で\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFTMessages\A4SWIFT-SRG\<バージョン > \Base ポリシー)。</span><span class="sxs-lookup"><span data-stu-id="bc918-130">Run the Rules Engine Deployment Wizard to publish and deploy BIC_Master_Policy.xml and   BIC_Validation_Policy.xml (in \<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies).</span></span> <span data-ttu-id="bc918-131">詳細については、「展開 BRE 規則 1 つで、下の日時」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc918-131">For more information, see "Deploying BRE Rules One at a Time" below.</span></span>  
  
## <a name="tools-for-deploying-the-policies"></a><span data-ttu-id="bc918-132">ポリシーを展開するためのツール</span><span class="sxs-lookup"><span data-stu-id="bc918-132">Tools for Deploying the Policies</span></span>  
 <span data-ttu-id="bc918-133">ボキャブラリを公開し、ポリシーを展開する最も簡単な方法は、ビジネス ルール エンジン (BRE) の展開ユーティリティ A4SWIFT ソフトウェア開発キット (SDK) を使用してです。</span><span class="sxs-lookup"><span data-stu-id="bc918-133">The easiest way to publish the vocabularies and deploy the policies is by using the Business Rule Engine (BRE) Deployment Utility in the A4SWIFT Software Development Kit (SDK).</span></span> <span data-ttu-id="bc918-134">行うことができますもこれを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ずつ、同じタスクの 1 つボキャブラリまたはポリシーを実行するルール エンジン展開ウィザード。</span><span class="sxs-lookup"><span data-stu-id="bc918-134">You can also do so by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Rule Engine Deployment Wizard, which performs the same task one vocabulary or policy at a time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc918-135">BRE 配置ユーティリティ配置しません BIC マスター ポリシーおよび BIC 検証ポリシー。</span><span class="sxs-lookup"><span data-stu-id="bc918-135">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="bc918-136">ルール エンジン展開ウィザードを使用して、これらを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc918-136">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  
### <a name="deploying-bre-rules-all-at-once"></a><span data-ttu-id="bc918-137">BRE の規則を一度にすべて展開</span><span class="sxs-lookup"><span data-stu-id="bc918-137">Deploying BRE Rules All at Once</span></span>  
 <span data-ttu-id="bc918-138">ビジネス ルール エンジン (BRE) 配置ユーティリティは、1 つの手順で、一連の発行および展開のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc918-138">The Business Rule Engine (BRE) Deployment Utility performs a series of publishing and deployment tasks in one step.</span></span> <span data-ttu-id="bc918-139">再実行してください、配置ユーティリティいつでも、プロジェクトにスキーマを追加することです。</span><span class="sxs-lookup"><span data-stu-id="bc918-139">You must rerun the deployment utility any time that you add a schema to your project.</span></span>  
  
##### <a name="to-deploy-bre-rules-using-the-bre-deployment-utility"></a><span data-ttu-id="bc918-140">BRE 配置ユーティリティを使用して BRE ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="bc918-140">To deploy BRE rules using the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="bc918-141">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**をクリックし、 **BRE 配置ユーティリティ**.</span><span class="sxs-lookup"><span data-stu-id="bc918-141">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="bc918-142">BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-142">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="bc918-143">.NET グローバル アセンブリ キャッシュ ダイアログ ボックスで、選択で配置したプロジェクト アセンブリ[A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-143">In the .NET Global Assembly Cache dialog box, select the project assembly that you deployed in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md), and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="bc918-144">BRE 配置ユーティリティ] ダイアログ ボックスで、[**展開**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-144">In the BRE Deployment Utility dialog box, click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc918-145">そのアセンブリと共に配置するスキーマに基づいて、配置ユーティリティは関連するルールを識別し、BRE で使用するためを公開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-145">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="bc918-146">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="bc918-146">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc918-147">"展開が完了しました。</span><span class="sxs-lookup"><span data-stu-id="bc918-147">"Deployment has completed.</span></span> <span data-ttu-id="bc918-148">ログ ファイルまたはビジネス ルール作成ツールの表示の詳細。"</span><span class="sxs-lookup"><span data-stu-id="bc918-148">View the log file or Business Rule Composer for details."</span></span>  
  
5.  <span data-ttu-id="bc918-149">BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc918-149">Close the BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="bc918-150">開いている[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラー。</span><span class="sxs-lookup"><span data-stu-id="bc918-150">Open [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer.</span></span> <span data-ttu-id="bc918-151">参照\<*ドライブ*>: \Documents and settings \all \all データとログ ファイル BREDeploymentLog.txt に表示されるそのドライブを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc918-151">Browse to \<*drive*>:\Documents and Settings\All Users\Application Data, and confirm that the log file BREDeploymentLog.txt appears in that drive.</span></span>  
  
7.  <span data-ttu-id="bc918-152">ルール エンジン更新サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bc918-152">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="bc918-153">クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-153">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="bc918-154">**サービス (ローカル)**ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-154">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
### <a name="deploying-bre-rules-one-at-a-time"></a><span data-ttu-id="bc918-155">一度に 1 つずつ BRE 規則を展開します。</span><span class="sxs-lookup"><span data-stu-id="bc918-155">Deploying BRE Rules One at a Time</span></span>  
 <span data-ttu-id="bc918-156">ルール エンジン展開ウィザードを使用して、ボキャブラリを公開し、一度に 1 つのポリシーを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="bc918-156">You can use the Rules Engine Deployment Wizard to publish vocabularies and deploy policies one at a time.</span></span> <span data-ttu-id="bc918-157">ボキャブラリ、このプロセスには、インポートして、1 つのステップ内のファイルからデータベースにボキャブラリを公開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc918-157">For a vocabulary, this process involves importing and publishing the vocabulary to the database from a file in one step.</span></span> <span data-ttu-id="bc918-158">インポートおよび 1 つの手順で、ポリシーをパブリッシュする別のステップに展開するポリシー、プロセスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc918-158">For a policy, the process involves importing and publishing the policy in one step, and then deploying it in another step.</span></span>  
  
##### <a name="to-deploy-bre-rules-using-the-rules-engine-deployment-wizard"></a><span data-ttu-id="bc918-159">ルール エンジン展開ウィザードを使用して BRE ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="bc918-159">To deploy BRE rules Using the Rules Engine Deployment Wizard</span></span>  
  
1.  <span data-ttu-id="bc918-160">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、クリックして**ビジネス ルール エンジン展開ウィザード**.</span><span class="sxs-lookup"><span data-stu-id="bc918-160">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rules Engine Deployment Wizard**.</span></span>  
  
2.  <span data-ttu-id="bc918-161">ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-161">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="bc918-162">展開タスク ページで、をクリックして**インポート ポリシー/ボキャブラリをファイルからデータベースに発行し、**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-162">On the Deployment Task page, click **Import and publish Policy/Vocabulary to database from file**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="bc918-163">ポリシー ストア] ページで、 **SQL サーバー名] ボックス**のサーバーを選択し、[、**選択したサーバーの構成データベース**一覧で、[ **BizTalkRuleEngineDb**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-163">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="bc918-164">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc918-164">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="bc918-165">インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、をクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-165">On the Import Rules Engine Policy/Vocabulary file page, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="bc918-166">[ファイル] ページで、ポリシーのインポートで、**ファイルの場所**ドロップダウン リスト、ボキャブラリまたはポリシーに応じて、次のフォルダーのいずれかに移動。</span><span class="sxs-lookup"><span data-stu-id="bc918-166">On the Import Policy from file page, in the **Look in** drop-down list, move to one of the following folders, depending upon the vocabulary or policy:</span></span>  
  
    -   <span data-ttu-id="bc918-167">\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > A4SWIFT_CodeLists.xml および A4SWIFT_Functions.xml \Base Policies\Vocabulary</span><span class="sxs-lookup"><span data-stu-id="bc918-167">\<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies\Vocabulary for A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml</span></span>  
  
    -   <span data-ttu-id="bc918-168">\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Base SWIFT_Reference_Policy.xml、SWIFT_PartyIdentifier_Policy.xml のポリシーネットワーク ルール ポリシー、BIC_Master_Policy.xml、および BIC_Validation_Policy.xml</span><span class="sxs-lookup"><span data-stu-id="bc918-168">\<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Base Policies for SWIFT_Reference_Policy.xml, SWIFT_PartyIdentifier_Policy.xml, network rule policies, BIC_Master_Policy.xml, and BIC_Validation_Policy.xml</span></span>  
  
    -   <span data-ttu-id="bc918-169">\<ドライブ >: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン > メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン > \Category 1\MTxxx 配置済みのメッセージに関連付けられているマスターと検証ポリシースキーマ</span><span class="sxs-lookup"><span data-stu-id="bc918-169">\<drive>:\Program Files\ Microsoft BizTalk Accelerator for SWIFT \<version> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version>\Category 1\MTxxx for the master and validation policies associated with deployed message schemas</span></span>  
  
7.  <span data-ttu-id="bc918-170">を展開し、をクリックするポリシーを選択して**開く**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-170">Select the policy that you want to deploy, and then click **Open**.</span></span>  
  
8.  <span data-ttu-id="bc918-171">インポート ルール エンジン ポリシー/ボキャブラリ ファイル ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-171">On the Import Rules Engine Policy/Vocabulary file page, click **Next**.</span></span>  
  
9. <span data-ttu-id="bc918-172">準備完了 ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-172">On the Ready page, click **Next**.</span></span>  
  
10. <span data-ttu-id="bc918-173">[ポリシー/ボキャブラリのインポート] ページで、コマンドが成功し、をクリックすることを確認**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-173">On the Importing Policy/Vocabulary page, verify that the command succeeded, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="bc918-174">完了のポリシーを展開するかどうか、ルール エンジン展開ウィザード ページ をクリックして**このウィザードを再度実行**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-174">If you want to deploy a policy, on the Completing the Rules Engine Deployment Wizard page, click **Run this Wizard again**, and then click **Finish**.</span></span>  
  
12. <span data-ttu-id="bc918-175">ルール エンジン展開ウィザードのページへようこそ、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-175">On the Welcome to the Rules Engine Deployment Wizard page, click **Next**.</span></span>  
  
13. <span data-ttu-id="bc918-176">展開タスク ページで、をクリックして**ポリシーの展開**、クリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-176">On the Deployment Task page, click **Deploy Policy**, and then click **Next**.</span></span>  
  
14. <span data-ttu-id="bc918-177">ポリシー ストア] ページで、 **SQL サーバー名] ボックス**のサーバーを選択し、[、**選択したサーバーの構成データベース**一覧で、[ **BizTalkRuleEngineDb**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-177">On the Policy Store page, in the **SQL Server Name list**, select your server, and in the **Configuration Database on selected server** list, select **BizTalkRuleEngineDb**.</span></span> <span data-ttu-id="bc918-178">**[次へ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc918-178">Click **Next**.</span></span>  
  
15. <span data-ttu-id="bc918-179">ポリシーの展開 ページで、下矢印をクリックして の横に、**ルール エンジン ポリシー**テキスト ボックスは、発行すると、したポリシーを選択し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-179">On the Deploy Policy page, click the down arrow next to the **Rules Engine Policy** text box, select the policy you just published, and then click **Next**.</span></span>  
  
16. <span data-ttu-id="bc918-180">準備完了 ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-180">On the Ready page, click **Next**.</span></span>  
  
17. <span data-ttu-id="bc918-181">**ポリシー/ボキャブラリをインポートする** ページで、コマンドが成功し、をクリックすることを確認**次**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-181">On the **Importing Policy/Vocabulary** page, verify that the command succeeded, and then click **Next**.</span></span>  
  
18. <span data-ttu-id="bc918-182">**[完了]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc918-182">Click **Finish**.</span></span>  
  
19. <span data-ttu-id="bc918-183">再起動、**ルール エンジン更新サービス**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-183">Restart the **Rule Engine Update Service**.</span></span> <span data-ttu-id="bc918-184">クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-184">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="bc918-185">**サービス (ローカル)**ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="bc918-185">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>