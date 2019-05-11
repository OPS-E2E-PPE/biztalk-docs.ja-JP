---
title: BRE 配置ユーティリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d59a06b55e4d30e9e87a68adbf830dad38578f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378973"
---
# <a name="bre-deployment-utility"></a><span data-ttu-id="85a5a-102">BRE 配置ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="85a5a-102">BRE Deployment Utility</span></span>
<span data-ttu-id="85a5a-103">BRE 配置ユーティリティを発行して、ビジネス ルール エンジン (BRE) のボキャブラリと SWIFT スキーマに必要なポリシーの展開に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="85a5a-103">You can use the BRE Deployment Utility to publish and deploy the Business Rule Engine (BRE) vocabularies and policies required for a SWIFT schema.</span></span> <span data-ttu-id="85a5a-104">メッセージの種類の BRE 検証を有効にするには、公開およびこれらのボキャブラリおよびポリシーの展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="85a5a-104">Publishing and deploying these vocabularies and policies is required to enable BRE validation for the message type.</span></span>  
  
 <span data-ttu-id="85a5a-105">SWIFT 標準リリース ガイド (SRGs) を使用して、必要なルールを識別する、Microsoft を使用して、ビジネス ルールをデプロイすることもできます。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ボキャブラリおよびポリシーを展開するビジネス ルール作成ツールです。</span><span class="sxs-lookup"><span data-stu-id="85a5a-105">You can also deploy business rules by using the SWIFT Standards Release Guides (SRGs) to identify the required rules, and then using the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Business Rule Composer tool to deploy the vocabularies and policies.</span></span> <span data-ttu-id="85a5a-106">ただし、BRE 配置ユーティリティを使用して、はるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="85a5a-106">However, using the BRE Deployment Utility is much easier.</span></span>  
  
 <span data-ttu-id="85a5a-107">BRE 配置ユーティリティの実行、次の場合。</span><span class="sxs-lookup"><span data-stu-id="85a5a-107">The BRE Deployment Utility accomplishes the following:</span></span>  
  
- <span data-ttu-id="85a5a-108">指定した展開済みのアセンブリを調べ、アセンブリの展開されたメッセージのスキーマを決定します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-108">Examines the deployed assembly that you specify and determines the message schemas that you deployed for the assembly.</span></span>  
  
- <span data-ttu-id="85a5a-109">発行、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml ボキャブラリが必要な Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ビジネス ルールを処理します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-109">Publishes the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml vocabularies required for Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] business rules processing.</span></span>  
  
- <span data-ttu-id="85a5a-110">発行し、SWIFT 基本ポリシー (ポリシーの参照、パーティの識別子のポリシーおよびネットワーク ルールのポリシー メッセージ スキーマに関連付けられている) を展開します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-110">Publishes and deploys the SWIFT base policies (reference policy, party identifier policy, and network rule policies) associated with the message schemas.</span></span>  
  
- <span data-ttu-id="85a5a-111">発行し、マスター ポリシーと各メッセージ スキーマに関連付けられている検証ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-111">Publishes and deploys the master policy and validation policy associated with each message schema.</span></span>  
  
- <span data-ttu-id="85a5a-112">必要なすべての手順を示すログ ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-112">Generates a log file that indicates all the steps that it takes.</span></span> <span data-ttu-id="85a5a-113">このファイルで BREDeploymentLog.txt、 \<*ドライブ*\>: \Documents and バックアップ データを別のフォルダー。</span><span class="sxs-lookup"><span data-stu-id="85a5a-113">This file is BREDeploymentLog.txt in the \<*drive*\>:\Documents and Settings\All Users\Application Data folder.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="85a5a-114">BRE 配置ユーティリティをデプロイしません BIC マスター ポリシーおよび BIC 検証ポリシー。</span><span class="sxs-lookup"><span data-stu-id="85a5a-114">The BRE Deployment Utility does not deploy the BIC Master Policy and BIC Validation Policy.</span></span> <span data-ttu-id="85a5a-115">ルール エンジン展開ウィザードを使用してこれらを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85a5a-115">You must deploy these using the Rule Engine Deployment wizard.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="85a5a-116">インストールした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]で既定以外のディレクトリ (C:\Program files \microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])、または 64 ビット コンピューターで作業して、BRE 配置ユーティリティは正しく動作しません内のパスを変更するまで、BREDeployment.exe.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="85a5a-116">If you have installed [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] in a non-default directory (other than C:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]), or you are working on a 64-bit computer, the BRE Deployment Utility will not work correctly until you change the paths in the BREDeployment.exe.config file.</span></span> <span data-ttu-id="85a5a-117">この構成ファイルにある、 \<*ドライブ*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools フォルダー。</span><span class="sxs-lookup"><span data-stu-id="85a5a-117">This configuration file is located in the \<*drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools folder.</span></span> <span data-ttu-id="85a5a-118">ユーティリティの構成を更新するには、メモ帳で BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-118">To update the utility's configuration, open BREDeployment.exe.config in Notepad, and change the folders for the base policies, schemas, and vocabulary directories.</span></span>  
  
  <span data-ttu-id="85a5a-119">展開解除ポリシーとボキャブラリの発行を取り消すと、このプロセスを反転させる配置ユーティリティを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="85a5a-119">You can also use the deployment utility to reverse this process, undeploying and unpublishing the policies and vocabularies.</span></span> <span data-ttu-id="85a5a-120">ユーティリティは、デプロイ両方がし、機能の展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-120">The utility has both deploy and undeploy functionality.</span></span>  
  
### <a name="to-use-the-bre-deployment-utility"></a><span data-ttu-id="85a5a-121">BRE 配置ユーティリティを使用するには</span><span class="sxs-lookup"><span data-stu-id="85a5a-121">To use the BRE Deployment Utility</span></span>  
  
1.  <span data-ttu-id="85a5a-122">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-122">Click **Start**, point to **Programs**, point to **Microsoft BizTalk Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="85a5a-123">BRE 配置ユーティリティでクリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-123">In the BRE Deployment Utility, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="85a5a-124">展開済みのアセンブリまたはアセンブリの発行、ボキャブラリとポリシーを展開し、クリックする選択**OK**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-124">Select the deployed assembly or assemblies for which you want to publish and deploy vocabularies and policies, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="85a5a-125">クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-125">Click **Deploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85a5a-126">そのアセンブリを展開するスキーマに基づき、BRE 配置ユーティリティは、関連するルールを識別して、BRE を使用するための発行のプロセス。</span><span class="sxs-lookup"><span data-stu-id="85a5a-126">Based on the schemas that you deployed with that assembly, the BRE Deployment Utility goes through the process of identifying the related rules and publishing them for use with the BRE.</span></span> <span data-ttu-id="85a5a-127">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。**配置が完了したら**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-127">When complete, the BRE Deployment Utility displays the following message: **Deployment has completed**.</span></span> <span data-ttu-id="85a5a-128">ビジネス ルール作成ツールを使用すると、展開の成功を確認します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-128">Use the Business Rule Composer to verify successful deployment.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85a5a-129">ポリシーとボキャブラリを展開解除する をクリックして**Undeploy**します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-129">To undeploy the policies and vocabularies, click **Undeploy**.</span></span> <span data-ttu-id="85a5a-130">展開解除プロセスは、展開されているその他のポリシーで使用することが A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリを展開解除されません。</span><span class="sxs-lookup"><span data-stu-id="85a5a-130">The undeploy process does not undeploy the A4SWIFT_CodeLists.xml and A4SWIFT_Functions.xml vocabularies, which might be used by other deployed policies.</span></span>  
  
5.  <span data-ttu-id="85a5a-131">検索\<*ドライブ*\>: \Documents and ユーティリティには、ログが作成されたことを確認する場合のバックアップ データ ファイルの BREDeploymentLog.txt します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-131">Locate \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the utility created the log file BREDeploymentLog.txt.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85a5a-132">ログ ファイルを開くには、テキスト エディターを使用して、各デプロイの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="85a5a-132">You can open the log file by using a text editor to confirm each deployment step.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a5a-133">参照</span><span class="sxs-lookup"><span data-stu-id="85a5a-133">See Also</span></span>  
 [<span data-ttu-id="85a5a-134">ツール</span><span class="sxs-lookup"><span data-stu-id="85a5a-134">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)