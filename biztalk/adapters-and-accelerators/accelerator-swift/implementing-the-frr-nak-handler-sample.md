---
title: FRR NAK ハンドラー サンプルの実装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80fa5fb7-6864-4923-b641-e76d2b95d923
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42885d6c487c6f088bfab113891ec5425d3fc82e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990283"
---
# <a name="implementing-the-frr-nak-handler-sample"></a><span data-ttu-id="a35b8-102">FRR NAK ハンドラー サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="a35b8-102">Implementing the FRR NAK Handler Sample</span></span>
<span data-ttu-id="a35b8-103">サンプル FRR NAK のカスタム ハンドラーを実装する、サンプル プロジェクトをソリューションに追加、ビルドしプロジェクトを展開、バインドし、オーケストレーションを開始および停止し、再開する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-103">To implement the sample FRR NAK custom handler, add the sample project to your solution, build and deploy the project, bind and start the orchestration, and then stop and restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

### <a name="to-implement-the-frr-nak-custom-handler"></a><span data-ttu-id="a35b8-104">FRR NAK のカスタム ハンドラーを実装するには</span><span class="sxs-lookup"><span data-stu-id="a35b8-104">To implement the FRR NAK Custom Handler</span></span>  

1. <span data-ttu-id="a35b8-105">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="a35b8-105">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], open your solution.</span></span> <span data-ttu-id="a35b8-106">ソリューション エクスプ ローラーでソリューションを右クリックして**追加**、 をクリックし、**既存のプロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-106">In Solution Explorer, right-click the solution, point to **Add**, and then click **Existing Project**.</span></span>  

2. <span data-ttu-id="a35b8-107">**既存プロジェクトの追加** ダイアログ ボックスに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-107">In the **Add Existing Project** dialog box, move to *\<drive\>*:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Samples\FrrHandler.</span></span> <span data-ttu-id="a35b8-108">選択**RepairSWIFTRejectedMessage.btproj**、 をクリックし、**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-108">Select **RepairSWIFTRejectedMessage.btproj**, and then click **Open**.</span></span>  

3. <span data-ttu-id="a35b8-109">キーを生成し、プロジェクトにキーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a35b8-109">Generate a key and assign the key to the project.</span></span>  

4. <span data-ttu-id="a35b8-110">ビルドおよび RepairSWIFTRejectedMessage.btproj プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-110">Build and deploy the RepairSWIFTRejectedMessage.btproj project.</span></span>  

5. <span data-ttu-id="a35b8-111">BizTalk エクスプ ローラーで、 **BizTalk 構成データベース**、  **\<*サーバー名*\>、>.biztalkmgmtdb.dbo**、および**オーケストレーション**、右クリック**RepairSWIFTRejectedMessage.Orchestration_1**、 をクリックし、**バインド**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-111">In BizTalk Explorer, expand **BizTalk Configuration Databases**, **\<*server name*\>,BizTalkMgmtDb.dbo**, and **Orchestrations**, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Bind**.</span></span>  

6. <span data-ttu-id="a35b8-112">**ポートのバインドのプロパティ**ダイアログ ボックスは、BizTalkServerApplication など、ホストを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-112">In the **Port Binding Properties** dialog box, select your host, such as BizTalkServerApplication, and then click **OK**.</span></span>  

7. <span data-ttu-id="a35b8-113">BizTalk エクスプ ローラーで右クリックして**RepairSWIFTRejectedMessage.Orchestration_1**、 をクリックし、**開始**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-113">In BizTalk Explorer, right-click **RepairSWIFTRejectedMessage.Orchestration_1**, and then click **Start**.</span></span>  

8. <span data-ttu-id="a35b8-114">**スタート**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="a35b8-114">In the **Express Start** dialog box, click **OK**.</span></span>  

9. <span data-ttu-id="a35b8-115">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a35b8-115">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="a35b8-116">入力**services.msc**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="a35b8-116">Enter **services.msc**, and then click **OK**.</span></span> <span data-ttu-id="a35b8-117">右クリック**BizTalk サービス**、 をクリックし、**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="a35b8-117">Right-click **BizTalk Service**, and then click **Restart**.</span></span>
