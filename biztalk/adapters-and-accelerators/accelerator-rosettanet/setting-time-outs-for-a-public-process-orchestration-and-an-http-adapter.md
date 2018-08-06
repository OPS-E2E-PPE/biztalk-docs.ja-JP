---
title: パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0977589e310746e2c75c1f89fdd2c41ecb86aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976715"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a><span data-ttu-id="5be0a-102">パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="5be0a-102">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>
<span data-ttu-id="5be0a-103">同期接続シナリオでパブリック プロセス オーケストレーションを HTTP アダプターと一緒に使用する場合、それぞれのタイムアウトを適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5be0a-103">When you use a public-process orchestration with an HTTP adapter in a synchronous scenario, you must set the time-outs for each appropriately.</span></span> <span data-ttu-id="5be0a-104">オーケストレーションのタイムアウト設定 (実行までの時間) は HTTP アダプターのタイムアウト (要求のタイムアウト) より小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5be0a-104">The time-out setting for the orchestration (Time to Perform) must be smaller than the time-out for the HTTP adapter (Request Timeout).</span></span> <span data-ttu-id="5be0a-105">これは、HTTP アダプターの設定が小さいと、オーケストレーションの前にアダプターがタイムアウトになる可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="5be0a-105">This is because if the setting for the HTTP adapter is smaller, the adapter could time out before the orchestration.</span></span> <span data-ttu-id="5be0a-106">この場合、プロセスの制御権がアダプターに渡ります。</span><span class="sxs-lookup"><span data-stu-id="5be0a-106">This gives the adapter control of the process.</span></span> <span data-ttu-id="5be0a-107">プロセスはオーケストレーションが制御する必要があるため、そのタイムアウト値が小さくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="5be0a-107">The orchestration must be in control of the process; therefore, its time-out setting must be smaller.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a><span data-ttu-id="5be0a-108">HTTP アダプターのタイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="5be0a-108">To set the time-out setting for the HTTP adapter</span></span>  
  
1.  <span data-ttu-id="5be0a-109">BizTalk エクスプ ローラーで、**送信ポート**、パブリック プロセス オーケストレーションを使用する HTTP 送信ポートをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5be0a-109">In BizTalk Explorer, expand **Send ports**, and then double-click the HTTP send port used with the public-process orchestration.</span></span>  
  
2.  <span data-ttu-id="5be0a-110">送信ポートのプロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) の**アドレス (URI)** します。</span><span class="sxs-lookup"><span data-stu-id="5be0a-110">In the Send Port Properties window, click the ellipsis button (**...**) for **Address (URI)**.</span></span>  
  
3.  <span data-ttu-id="5be0a-111">HTTP トランスポートのプロパティ ウィンドウの 全般 ウィンドウで、**要求のタイムアウト (秒)** ボックスに、適切なタイムアウト値を入力します。この値はより大きくする必要があります、**実行までの時間**の関連するプロセス PIP (Partner Interface) を設定します。</span><span class="sxs-lookup"><span data-stu-id="5be0a-111">In the HTTP Transport Properties window, in the General pane, in the **Request timeout (sec.)** box, type an appropriate value for the time-out. This value must be larger than the **Time to Perform** setting for the relevant Partner Interface Process (PIP).</span></span>  
  
4.  <span data-ttu-id="5be0a-112">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="5be0a-112">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a><span data-ttu-id="5be0a-113">パブリック プロセス オーケストレーションのタイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="5be0a-113">To set the time-out setting for the public-process orchestration</span></span>  
  
1. <span data-ttu-id="5be0a-114">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**BizTalk Accelerator for RosettaNet 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="5be0a-114">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click  **BizTalk Accelerator for RosettaNet Management Console**.</span></span>  
  
2. <span data-ttu-id="5be0a-115">展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**プロセス構成設定**します。</span><span class="sxs-lookup"><span data-stu-id="5be0a-115">Expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Process Configuration Settings**.</span></span>  
  
3. <span data-ttu-id="5be0a-116">タイムアウトを設定を設定する PIP を右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="5be0a-116">Right-click the PIP that you want to set the time-out setting for, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="5be0a-117">プロパティ ダイアログ ボックスで、上、**アクティビティ** タブで、**実行までの時間**ボックスで、適切な値を設定すると、HTTP アダプターのタイムアウトよりも小さいを入力し、をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="5be0a-117">In theProperties dialog box, on the **Activity** tab, in the **Time to Perform** box, type an appropriate value that is smaller than the HTTP adapter time-out setting, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5be0a-118">参照</span><span class="sxs-lookup"><span data-stu-id="5be0a-118">See Also</span></span>  
 [<span data-ttu-id="5be0a-119">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="5be0a-119">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)