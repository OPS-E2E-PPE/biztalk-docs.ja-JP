---
title: "FRR NAK ハンドラーのサンプルを実装する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4233bf7f81cf7e645440e18a54479c8aa81094e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-frr-nak-handler-sample"></a><span data-ttu-id="539df-102">FRR NAK ハンドラーのサンプルを実装します。</span><span class="sxs-lookup"><span data-stu-id="539df-102">Implementing the FRR NAK Handler Sample</span></span>
<span data-ttu-id="539df-103">サンプル FRR NAK カスタム ハンドラーを実装して、サンプル プロジェクトをソリューションに追加、ビルドし、プロジェクトを配置、バインドし、オーケストレーションを開始および停止し、再開する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="539df-103">To implement the sample FRR NAK custom handler, add the sample project to your solution, build and deploy the project, bind and start the orchestration, and then stop and restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
### <a name="to-implement-the-frr-nak-custom-handler"></a><span data-ttu-id="539df-104">FRR NAK カスタム ハンドラーを実装するには</span><span class="sxs-lookup"><span data-stu-id="539df-104">To implement the FRR NAK Custom Handler</span></span>  
  
1.  <span data-ttu-id="539df-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="539df-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], open your solution.</span></span> <span data-ttu-id="539df-106">ソリューション エクスプ ローラーでソリューションを右クリックし、**追加**、クリックして**既存のプロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="539df-106">In Solution Explorer, right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  
  
2.  <span data-ttu-id="539df-107">**既存プロジェクトの追加** ダイアログ ボックスに移動*\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler です。</span><span class="sxs-lookup"><span data-stu-id="539df-107">In the **Add Existing Project** dialog box, move to *\<drive>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler.</span></span> <span data-ttu-id="539df-108">選択**RepairSWIFTRejectedMessage.btproj**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="539df-108">Select **RepairSWIFTRejectedMessage.btproj**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="539df-109">キーを生成し、キーをプロジェクトに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="539df-109">Generate a key and assign the key to the project.</span></span>  
  
4.  <span data-ttu-id="539df-110">ビルドして RepairSWIFTRejectedMessage.btproj プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="539df-110">Build and deploy the RepairSWIFTRejectedMessage.btproj project.</span></span>  
  
5.  <span data-ttu-id="539df-111">BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、   **\<*サーバー名*>、BizTalkMgmtDb.dbo**、および**オーケストレーション**を右クリックして**RepairSWIFTRejectedMessage.Orchestration_1**、クリックして**バインド**です。</span><span class="sxs-lookup"><span data-stu-id="539df-111">In BizTalk Explorer, expand **BizTalk Configuration Databases**, **\<*server name*>,BizTalkMgmtDb.dbo**, and **Orchestrations**, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Bind**.</span></span>  
  
6.  <span data-ttu-id="539df-112">**ポート バインド プロパティ**ダイアログ ボックスでは、BizTalkServerApplication など、ホストを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="539df-112">In the **Port Binding Properties** dialog box, select your host, such as BizTalkServerApplication, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="539df-113">BizTalk エクスプ ローラーで右クリック**RepairSWIFTRejectedMessage.Orchestration_1**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="539df-113">In BizTalk Explorer, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Start**.</span></span>  
  
8.  <span data-ttu-id="539df-114">**スタート**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="539df-114">In the **Express Start** dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="539df-115">**[スタート]**ボタンをクリックし、 **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="539df-115">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="539df-116">入力**services.msc**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="539df-116">Enter **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="539df-117">右クリック**BizTalk サービス**、クリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="539df-117">Right-click **BizTalk Service**, and then click **Restart**.</span></span>