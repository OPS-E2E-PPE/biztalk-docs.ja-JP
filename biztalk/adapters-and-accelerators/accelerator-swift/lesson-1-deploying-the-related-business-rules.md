---
title: 'レッスン 1: 関連するビジネス ルールの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6228f890e0f508650827f2bb2c3e52b5d29f96f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971107"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a><span data-ttu-id="fbee1-102">レッスン 1: 関連するビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="fbee1-102">Lesson 1: Deploying the Related Business Rules</span></span>
<span data-ttu-id="fbee1-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で、A4SWIFT ソフトウェア開発キット (SDK)、ビジネス ルール エンジン (BRE) の展開ユーティリティと呼ばれるプログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbee1-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes a program in the A4SWIFT Software Development Kit (SDK) called the Business Rule Engine (BRE) Deployment Utility.</span></span> <span data-ttu-id="fbee1-104">このレッスンでは、このユーティリティを使用して展開されたスキーマのアセンブリを検査、必要なルールを決定および必要なボキャブラリとすべてのスキーマのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-104">In this lesson, you use this utility to inspect an assembly for deployed schemas, determine the required rules, and deploy the necessary vocabularies and policies for each schema.</span></span>  
  
 <span data-ttu-id="fbee1-105">必要なルールを識別し、ビジネス ルール作成ツールを使用して、ボキャブラリとポリシーを展開する SWIFT 標準リリース ガイド (SRG) を使用して規則をデプロイすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fbee1-105">You can also deploy rules by using the SWIFT Standards Release Guides (SRG) to identify the necessary rules and then use the Business Rule Composer tool to deploy the vocabularies and policies.</span></span>  
  
### <a name="to-deploy-the-related-business-rules"></a><span data-ttu-id="fbee1-106">関連するビジネス ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="fbee1-106">To deploy the related business rules</span></span>  
  
1. <span data-ttu-id="fbee1-107">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for SWIFT**をクリックして**BRE 配置ユーティリティ**します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-107">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2. <span data-ttu-id="fbee1-108">BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-108">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3. <span data-ttu-id="fbee1-109">.NET グローバル アセンブリ キャッシュ ダイアログ ボックスで、 **SWIFTSchemas**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="fbee1-109">In the .NET Global Assembly Cache dialog box, select **SWIFTSchemas**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fbee1-110">アセンブリを参照 SWIFTSchemas 以前に展開します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-110">SWIFTSchemas refers to the assembly you previously deployed.</span></span>  
  
4. <span data-ttu-id="fbee1-111">クリックして**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-111">Click **Deploy**.</span></span>  
  
    <span data-ttu-id="fbee1-112">そのアセンブリを展開するスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-112">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="fbee1-113">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="fbee1-113">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
    <span data-ttu-id="fbee1-114">**デプロイが完了しました。詳細については、ログ ファイルまたはビジネス ルール作成ツールを表示します。**</span><span class="sxs-lookup"><span data-stu-id="fbee1-114">**Deployment has completed. View the log file or Business Rules Composer for details.**</span></span>  
  
5. <span data-ttu-id="fbee1-115">SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fbee1-115">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6. <span data-ttu-id="fbee1-116">Windows エクスプ ローラーを参照\<*ドライブ*\>: \Documents and ことを確認する場合のバックアップ データ、ログ ファイル**BREDeploymentLog.txt**に表示されます、フォルダー。</span><span class="sxs-lookup"><span data-stu-id="fbee1-116">In Windows Explorer, browse to \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the log file **BREDeploymentLog.txt** appears in the folder.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fbee1-117">各展開の手順を確認するテキスト エディターを使用してログ ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="fbee1-117">You can open the log file using a text editor to confirm each of the deployment steps.</span></span>  
  
7. <span data-ttu-id="fbee1-118">ルール エンジン更新サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-118">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="fbee1-119">クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。</span><span class="sxs-lookup"><span data-stu-id="fbee1-119">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="fbee1-120">**サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-120">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
   <span data-ttu-id="fbee1-121">進みます[レッスン 2: ビジネス ルールの作成ツールを使用して、展開を確認する](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)します。</span><span class="sxs-lookup"><span data-stu-id="fbee1-121">Proceed to [Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span></span>