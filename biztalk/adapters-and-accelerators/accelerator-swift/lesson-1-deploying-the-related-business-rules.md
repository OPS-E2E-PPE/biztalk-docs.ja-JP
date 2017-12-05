---
title: "レッスン 1: 関連するビジネス ルールの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17c4b470b802a980306481361c1fafcec4f70269
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-1-deploying-the-related-business-rules"></a><span data-ttu-id="d4f10-102">レッスン 1: 関連するビジネス ルールの展開</span><span class="sxs-lookup"><span data-stu-id="d4f10-102">Lesson 1: Deploying the Related Business Rules</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="d4f10-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で、A4SWIFT ソフトウェア開発キット (SDK)、ビジネス ルール エンジン (BRE) の展開ユーティリティと呼ばれるプログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d4f10-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] includes a program in the A4SWIFT Software Development Kit (SDK) called the Business Rule Engine (BRE) Deployment Utility.</span></span> <span data-ttu-id="d4f10-104">このレッスンでは、このユーティリティを使用して展開されたスキーマのアセンブリを調べる、必須のルールを決定および必要なボキャブラリとすべてのスキーマのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d4f10-104">In this lesson, you use this utility to inspect an assembly for deployed schemas, determine the required rules, and deploy the necessary vocabularies and policies for each schema.</span></span>  
  
 <span data-ttu-id="d4f10-105">必要なルールを識別し、ビジネス ルール作成ツールを使用して、ボキャブラリとポリシーを展開する SWIFT 標準リリース ガイド (SRG) を使用して規則を展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="d4f10-105">You can also deploy rules by using the SWIFT Standards Release Guides (SRG) to identify the necessary rules and then use the Business Rule Composer tool to deploy the vocabularies and policies.</span></span>  
  
### <a name="to-deploy-the-related-business-rules"></a><span data-ttu-id="d4f10-106">関連するビジネス ルールを展開するには</span><span class="sxs-lookup"><span data-stu-id="d4f10-106">To deploy the related business rules</span></span>  
  
1.  <span data-ttu-id="d4f10-107">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 SWIFT**をクリックして**BRE 配置ユーティリティ**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-107">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for SWIFT**, and then click **BRE Deployment Utility**.</span></span>  
  
2.  <span data-ttu-id="d4f10-108">BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-108">In the BRE Deployment Utility dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="d4f10-109">.NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFTSchemas**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-109">In the .NET Global Assembly Cache dialog box, select **SWIFTSchemas**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4f10-110">SWIFTSchemas とは、アセンブリが以前に展開します。</span><span class="sxs-lookup"><span data-stu-id="d4f10-110">SWIFTSchemas refers to the assembly you previously deployed.</span></span>  
  
4.  <span data-ttu-id="d4f10-111">をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-111">Click **Deploy**.</span></span>  
  
     <span data-ttu-id="d4f10-112">そのアセンブリと共に配置するスキーマに基づいて、配置ユーティリティは関連するルールを識別し、BRE で使用するためを公開します。</span><span class="sxs-lookup"><span data-stu-id="d4f10-112">Based on the schemas you deployed with that assembly, the deployment utility identifies the related rules and publishes them for use with the BRE.</span></span> <span data-ttu-id="d4f10-113">完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d4f10-113">When complete, the BRE Deployment Utility displays the following message:</span></span>  
  
     <span data-ttu-id="d4f10-114">**展開が完了しました。詳細については、ログ ファイルまたはビジネス ルール作成ツールを表示します。**</span><span class="sxs-lookup"><span data-stu-id="d4f10-114">**Deployment has completed. View the log file or Business Rules Composer for details.**</span></span>  
  
5.  <span data-ttu-id="d4f10-115">SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d4f10-115">Close the SWIFT BRE Deployment Utility dialog box.</span></span>  
  
6.  <span data-ttu-id="d4f10-116">Windows エクスプ ローラーで参照\<*ドライブ*\>: \Documents and settings \all \all データいることを確認、ログ ファイル**BREDeploymentLog.txt**に表示されます、フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="d4f10-116">In Windows Explorer, browse to \<*drive*\>:\Documents and Settings\All Users\Application Data to confirm that the log file **BREDeploymentLog.txt** appears in the folder.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d4f10-117">各展開の手順を確認するテキスト エディターを使用してログ ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d4f10-117">You can open the log file using a text editor to confirm each of the deployment steps.</span></span>  
  
7.  <span data-ttu-id="d4f10-118">ルール エンジン更新サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="d4f10-118">Restart the Rule Engine Update Service.</span></span> <span data-ttu-id="d4f10-119">クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-119">Do so by clicking **Start**, clicking **Run**, entering **services.msc**, and clicking **OK**.</span></span> <span data-ttu-id="d4f10-120">**サービス (ローカル)**ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-120">In the **Services (Local)** window, right-click **Rule Engine Update Service**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="d4f10-121">進みます[レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認する](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4f10-121">Proceed to [Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md).</span></span>