---
title: "パブリック プロセス オーケストレーションと HTTP アダプターのタイムアウトの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f7f15d01759704af6b6b3134c9d36f0e64f8e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a><span data-ttu-id="c5e70-102">パブリック プロセス オーケストレーションと HTTP アダプターのタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="c5e70-102">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>
<span data-ttu-id="c5e70-103">同期接続シナリオでパブリック プロセス オーケストレーションを HTTP アダプターと一緒に使用する場合、それぞれのタイムアウトを適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5e70-103">When you use a public-process orchestration with an HTTP adapter in a synchronous scenario, you must set the time-outs for each appropriately.</span></span> <span data-ttu-id="c5e70-104">オーケストレーションのタイムアウト設定 (実行までの時間) は HTTP アダプターのタイムアウト (要求のタイムアウト) より小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5e70-104">The time-out setting for the orchestration (Time to Perform) must be smaller than the time-out for the HTTP adapter (Request Timeout).</span></span> <span data-ttu-id="c5e70-105">これは、HTTP アダプターの設定が小さいと、オーケストレーションの前にアダプターがタイムアウトになる可能性があるからです。</span><span class="sxs-lookup"><span data-stu-id="c5e70-105">This is because if the setting for the HTTP adapter is smaller, the adapter could time out before the orchestration.</span></span> <span data-ttu-id="c5e70-106">この場合、プロセスの制御権がアダプターに渡ります。</span><span class="sxs-lookup"><span data-stu-id="c5e70-106">This gives the adapter control of the process.</span></span> <span data-ttu-id="c5e70-107">プロセスはオーケストレーションが制御する必要があるため、そのタイムアウト値が小さくなければなりません。</span><span class="sxs-lookup"><span data-stu-id="c5e70-107">The orchestration must be in control of the process; therefore, its time-out setting must be smaller.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a><span data-ttu-id="c5e70-108">HTTP アダプターのタイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="c5e70-108">To set the time-out setting for the HTTP adapter</span></span>  
  
1.  <span data-ttu-id="c5e70-109">BizTalk エクスプ ローラーで、**送信ポート**、し、パブリック プロセス オーケストレーションで使用する HTTP 送信ポートをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="c5e70-109">In BizTalk Explorer, expand **Send ports**, and then double-click the HTTP send port used with the public-process orchestration.</span></span>  
  
2.  <span data-ttu-id="c5e70-110">[送信ポートのプロパティ] ウィンドウの省略記号ボタン (**.**) の**アドレス (URI)**です。</span><span class="sxs-lookup"><span data-stu-id="c5e70-110">In the Send Port Properties window, click the ellipsis button (**...**) for **Address (URI)**.</span></span>  
  
3.  <span data-ttu-id="c5e70-111">HTTP トランスポートのプロパティ] ウィンドウの [全般] ウィンドウで、[、**要求のタイムアウト (秒)**ボックスに、タイムアウトの適切な値を入力します。この値はより大きくする必要があります、**実行までの時間**の関連するプロセス PIP (Partner Interface) を設定します。</span><span class="sxs-lookup"><span data-stu-id="c5e70-111">In the HTTP Transport Properties window, in the General pane, in the **Request timeout (sec.)** box, type an appropriate value for the time-out. This value must be larger than the **Time to Perform** setting for the relevant Partner Interface Process (PIP).</span></span>  
  
4.  <span data-ttu-id="c5e70-112">をクリックして**[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="c5e70-112">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a><span data-ttu-id="c5e70-113">パブリック プロセス オーケストレーションのタイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="c5e70-113">To set the time-out setting for the public-process orchestration</span></span>  
  
1.  <span data-ttu-id="c5e70-114">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**、クリックして**BizTalk Accelerator for RosettaNet 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="c5e70-114">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click  **BizTalk Accelerator for RosettaNet Management Console**.</span></span>  
  
2.  <span data-ttu-id="c5e70-115">展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、クリックして**プロセス構成設定**です。</span><span class="sxs-lookup"><span data-stu-id="c5e70-115">Expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Process Configuration Settings**.</span></span>  
  
3.  <span data-ttu-id="c5e70-116">タイムアウトを設定を設定する PIP を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c5e70-116">Right-click the PIP that you want to set the time-out setting for, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c5e70-117">プロパティ ダイアログ ボックスで、上、**アクティビティ**] タブの [、**実行までの時間**ボックスを設定すると、HTTP アダプタのタイムアウトよりも小さいを適切な値を入力してをクリックして**[ok]**.</span><span class="sxs-lookup"><span data-stu-id="c5e70-117">In theProperties dialog box, on the **Activity** tab, in the **Time to Perform** box, type an appropriate value that is smaller than the HTTP adapter time-out setting, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e70-118">参照</span><span class="sxs-lookup"><span data-stu-id="c5e70-118">See Also</span></span>  
 [<span data-ttu-id="c5e70-119">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c5e70-119">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)