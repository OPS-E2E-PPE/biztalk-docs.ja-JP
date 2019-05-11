---
title: 手順 4:プロジェクトのビルド |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d88b1407-ecdd-4dbf-90da-02dc4781568c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6216d96e0d9ce0f8e564fa45bc28c075ce124c8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367696"
---
# <a name="step-4-build-the-project"></a><span data-ttu-id="2ed7f-102">手順 4:プロジェクトをビルドします</span><span class="sxs-lookup"><span data-stu-id="2ed7f-102">Step 4: Build the Project</span></span>
<span data-ttu-id="2ed7f-103">![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="2ed7f-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="2ed7f-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="2ed7f-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="2ed7f-105">**目標:** この手順では、BizTalk オーケストレーション プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-105">**Objective:** In this step, you compile the BizTalk orchestration project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2ed7f-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="2ed7f-106">Prerequisites</span></span>  
 <span data-ttu-id="2ed7f-107">完了する必要があります[手順 3。レコードを挿入し、応答を受信する要求メッセージの送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-107">You must have completed [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  
  
### <a name="to-build-the-biztalk-orchestration-project"></a><span data-ttu-id="2ed7f-108">BizTalk オーケストレーション プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="2ed7f-108">To build the BizTalk orchestration project</span></span>  
  
1. <span data-ttu-id="2ed7f-109">ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-109">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="2ed7f-110">ツリー ウィンドウで、プロパティ ページ] ダイアログ ボックスで [**共通プロパティ**、 をクリックして**アセンブリ**、プロパティ ボックスの一覧をクリックし、**アセンブリ キー ファイル**省略記号 **[...]**.</span><span class="sxs-lookup"><span data-stu-id="2ed7f-110">In the property pages dialog box, in the tree pane, expand **Common Properties**, click **Assembly**, and then in the properties list, click the **Assembly Key File** ellipsis **[…]**.</span></span>  
  
3. <span data-ttu-id="2ed7f-111">」の説明に従って作成したアセンブリ キー ファイルへのパスを指定[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-111">Specify a path to the assembly key file you created as described in [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md), and then click **Open**.</span></span>  
  
4. <span data-ttu-id="2ed7f-112">ツリー ウィンドウで、プロパティ ページ ダイアログ ボックスで **構成プロパティ**、 をクリックして**展開**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-112">In the property pages dialog box, in the tree pane, expand **Configuration Properties**, click **Deployment**, and then do the following:</span></span>  
  
   1. <span data-ttu-id="2ed7f-113">**アプリケーション名**プロパティに「`SampleApplication`します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-113">For the **Application Name** property, type `SampleApplication`.</span></span>  
  
   2. <span data-ttu-id="2ed7f-114">**再デプロイ**プロパティで、 **True**します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-114">For the **Redeploy** property, select **True**.</span></span>  
  
      <span data-ttu-id="2ed7f-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-115">Click **OK**.</span></span>  
  
5. <span data-ttu-id="2ed7f-116">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-116">On the **File** menu, click **Save All**.</span></span>  
  
6. <span data-ttu-id="2ed7f-117">ソリューション エクスプ ローラーでソリューション名を右クリックし をクリックし、**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-117">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
    <span data-ttu-id="2ed7f-118">画面の下部にある出力ウィンドウは次のようになります。**ビルド:3 つ成功または最新、0 失敗、0 スキップされます。**</span><span class="sxs-lookup"><span data-stu-id="2ed7f-118">The Output pane at the bottom of the screen should read: **Build: 3 succeeded or up-to-date, 0 failed, 0 skipped.**</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="2ed7f-119">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-119">What did I just do?</span></span>  
 <span data-ttu-id="2ed7f-120">この手順では、BizTalk プロジェクトと 2 つのクラス ライブラリ プロジェクトを含むソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-120">In this step, you compiled the solution containing the BizTalk project and two class library projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2ed7f-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="2ed7f-121">Next Steps</span></span>  
 <span data-ttu-id="2ed7f-122">」の説明に従って、ソリューションの配置[レッスン 5。ソリューションの配置](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="2ed7f-122">You deploy the solution, as described in [Lesson 5: Deploy the Solution](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed7f-123">参照</span><span class="sxs-lookup"><span data-stu-id="2ed7f-123">See Also</span></span>  
 <span data-ttu-id="2ed7f-124">[ステップ 3:レコードを挿入し、応答を受信する要求メッセージを送信します。](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span><span class="sxs-lookup"><span data-stu-id="2ed7f-124">[Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span></span>  
 [<span data-ttu-id="2ed7f-125">レッスン 4:注文テーブルに対して挿入操作を実行する</span><span class="sxs-lookup"><span data-stu-id="2ed7f-125">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)