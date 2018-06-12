---
title: '手順 5: ミラー アグリーメントの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, mirror agreements
- loopback tutorial, creating mirror agreements
- agreements, mirror agreements
ms.assetid: 6aa70b1e-7d38-49f7-9d5f-f008cbe3df66
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65fbb1c93b0401e8c6460c9df1f2313931c34950
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855597"
---
# <a name="step-5-create-a-mirror-agreement"></a><span data-ttu-id="f071e-102">手順 5: ミラー アグリーメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f071e-102">Step 5: Create a Mirror Agreement</span></span>
<span data-ttu-id="f071e-103">ここでは、ループバック ユーティリティを使用してミラー アグリーメントを作成します。このミラー アグリーメントは、ホーム組織を構成したコンピューターと同じコンピューターで取引先をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="f071e-103">In this step, you use the Loopback utility to create a mirror agreement simulating the trading partner on the same computer on which you configured the home organization.</span></span> <span data-ttu-id="f071e-104">ループバック ユーティリティは、コマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="f071e-104">The Loopback utility is a command-line tool.</span></span>  
  
### <a name="to-create-a-mirror-agreement-using-the-loopback-utility"></a><span data-ttu-id="f071e-105">ループバック ユーティリティを使用してミラー アグリーメントを作成するには</span><span class="sxs-lookup"><span data-stu-id="f071e-105">To create a mirror agreement using the Loopback utility</span></span>  
  
1.  <span data-ttu-id="f071e-106">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="f071e-106">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="f071e-107">コマンド プロンプトでに移動\<*ドライブ*\>: \Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk です。</span><span class="sxs-lookup"><span data-stu-id="f071e-107">At the command prompt, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK.</span></span> <span data-ttu-id="f071e-108">次のコマンドを入力し、キーを押します**Enter**:</span><span class="sxs-lookup"><span data-stu-id="f071e-108">Type the following command and then press **Enter**:</span></span>  
  
    ```  
    Loopback /enable HOME  
    ```  
  
3.  <span data-ttu-id="f071e-109">手順 2 で実行されるコマンドが完了したら、コマンド プロンプトで次のコマンドを入力し、キーを押します**Enter**:</span><span class="sxs-lookup"><span data-stu-id="f071e-109">After the command executed in step 2 has completed, type the following command in the command prompt, and then press **Enter**:</span></span>  
  
    ```  
    Loopback /mirror "Trade Agreement"   
    ```  
  
 <span data-ttu-id="f071e-110">ループバック ユーティリティによって、ホーム組織 (開始側) 用の送信ポートと、取引先組織用のミラー取引アグリーメントが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="f071e-110">The Loopback utility automatically creates send ports for the home organization (initiator) and a mirror trade agreement for the partner organization.</span></span> <span data-ttu-id="f071e-111">パートナーは、この 2 つの新しい送信ポートを使用して、ホーム組織と通信します。</span><span class="sxs-lookup"><span data-stu-id="f071e-111">The partner uses the two new send ports to communicate with the home organization.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f071e-112">元の取引アグリーメントを更新した場合は、その都度取引アグリーメントの再ミラーリングを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="f071e-112">You must re-mirror the trade agreement whenever you update the original trade agreement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f071e-113">参照</span><span class="sxs-lookup"><span data-stu-id="f071e-113">See Also</span></span>  
 [<span data-ttu-id="f071e-114">手順 6: オーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="f071e-114">Step 6: Start Orchestrations</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-start-orchestrations.md)
