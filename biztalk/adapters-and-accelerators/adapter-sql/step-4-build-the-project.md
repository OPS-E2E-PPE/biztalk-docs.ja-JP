---
title: '手順 4: プロジェクトをビルドします |Microsoft ドキュメント'
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
ms.openlocfilehash: 0f1d6fa03b4a686537ef04f0121c1ae168e525ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225666"
---
# <a name="step-4-build-the-project"></a><span data-ttu-id="015f6-102">手順 4: プロジェクトをビルドします</span><span class="sxs-lookup"><span data-stu-id="015f6-102">Step 4: Build the Project</span></span>
<span data-ttu-id="015f6-103">![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="015f6-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="015f6-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="015f6-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="015f6-105">**目標:** この手順では、BizTalk オーケストレーション プロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="015f6-105">**Objective:** In this step, you compile the BizTalk orchestration project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="015f6-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="015f6-106">Prerequisites</span></span>  
 <span data-ttu-id="015f6-107">完了する必要があります[手順 3: 応答レコードの挿入と受信する要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md)です。</span><span class="sxs-lookup"><span data-stu-id="015f6-107">You must have completed [Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md).</span></span>  
  
### <a name="to-build-the-biztalk-orchestration-project"></a><span data-ttu-id="015f6-108">BizTalk オーケストレーション プロジェクトをビルドするには</span><span class="sxs-lookup"><span data-stu-id="015f6-108">To build the BizTalk orchestration project</span></span>  
  
1.  <span data-ttu-id="015f6-109">ソリューション エクスプ ローラーで BizTalk プロジェクト名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="015f6-109">In the Solution Explorer, right-click the BizTalk project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="015f6-110">プロパティ ページ] ダイアログ ボックスのツリー ウィンドウで、[展開**共通プロパティ**をクリックして**アセンブリ**、プロパティ リストをクリックし、**アセンブリ キー ファイル**省略記号 **[...]**.</span><span class="sxs-lookup"><span data-stu-id="015f6-110">In the property pages dialog box, in the tree pane, expand **Common Properties**, click **Assembly**, and then in the properties list, click the **Assembly Key File** ellipsis **[…]**.</span></span>  
  
3.  <span data-ttu-id="015f6-111">」の説明に従って作成したアセンブリ キー ファイルへのパスを指定して[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)、順にクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="015f6-111">Specify a path to the assembly key file you created as described in [Prerequisites to create SQL applications using the SQL adapter](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md), and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="015f6-112">プロパティ ページ] ダイアログ ボックスのツリー ウィンドウで、[展開**構成プロパティ**をクリックして**展開**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="015f6-112">In the property pages dialog box, in the tree pane, expand **Configuration Properties**, click **Deployment**, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="015f6-113">**アプリケーション名**プロパティで、「`SampleApplication`です。</span><span class="sxs-lookup"><span data-stu-id="015f6-113">For the **Application Name** property, type `SampleApplication`.</span></span>  
  
    2.  <span data-ttu-id="015f6-114">**再展開**プロパティで、 **True**です。</span><span class="sxs-lookup"><span data-stu-id="015f6-114">For the **Redeploy** property, select **True**.</span></span>  
  
     <span data-ttu-id="015f6-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="015f6-115">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="015f6-116">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="015f6-116">On the **File** menu, click **Save All**.</span></span>  
  
6.  <span data-ttu-id="015f6-117">ソリューション エクスプ ローラーでソリューション名を右クリックし、をクリックして**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="015f6-117">In Solution Explorer, right-click the solution name, and then click **Build Solution**.</span></span>  
  
     <span data-ttu-id="015f6-118">画面の下部にある出力ウィンドウを読み取る必要があります:**ビルド: 3 の成功または最新、0 失敗、0 スキップします。**</span><span class="sxs-lookup"><span data-stu-id="015f6-118">The Output pane at the bottom of the screen should read: **Build: 3 succeeded or up-to-date, 0 failed, 0 skipped.**</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="015f6-119">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="015f6-119">What did I just do?</span></span>  
 <span data-ttu-id="015f6-120">このステップでは、BizTalk プロジェクトと 2 つのクラス ライブラリ プロジェクトを含むソリューションをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="015f6-120">In this step, you compiled the solution containing the BizTalk project and two class library projects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="015f6-121">次の手順</span><span class="sxs-lookup"><span data-stu-id="015f6-121">Next Steps</span></span>  
 <span data-ttu-id="015f6-122">」の説明に従って、ソリューションの配置[レッスン 5: ソリューションの配置](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="015f6-122">You deploy the solution, as described in [Lesson 5: Deploy the Solution](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="015f6-123">参照</span><span class="sxs-lookup"><span data-stu-id="015f6-123">See Also</span></span>  
 <span data-ttu-id="015f6-124">[手順 3: レコードを挿入し、応答を受信する要求メッセージを送信します。](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span><span class="sxs-lookup"><span data-stu-id="015f6-124">[Step 3: Send the Request Message to Insert Records and Receive a Response](../../adapters-and-accelerators/adapter-sql/step-3-send-the-request-message-to-insert-records-and-receive-a-response.md) </span></span>  
 [<span data-ttu-id="015f6-125">レッスン 4: Purchase Order テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="015f6-125">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)