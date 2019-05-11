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
ms.openlocfilehash: 70dd783e805116b24e224886e02d0f46fe2edfed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281824"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a><span data-ttu-id="3f94e-102">パブリック プロセス オーケストレーションと HTTP アダプタのタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="3f94e-102">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>
<span data-ttu-id="3f94e-103">同期のシナリオで HTTP アダプターを使用したパブリック プロセス オーケストレーションを使用するときにごとのタイムアウトの設定値を適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f94e-103">When you use a public-process orchestration with an HTTP adapter in a synchronous scenario, you must set the time-outs for each appropriately.</span></span> <span data-ttu-id="3f94e-104">オーケストレーション (実行までの時間) のタイムアウト設定は、(要求タイムアウト) HTTP アダプターのタイムアウトより小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f94e-104">The time-out setting for the orchestration (Time to Perform) must be smaller than the time-out for the HTTP adapter (Request Timeout).</span></span> <span data-ttu-id="3f94e-105">これは、ため、アダプターが、オーケストレーションの前にタイムアウトになる可能性があります、HTTP アダプターの設定が小さい場合は、です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-105">This is because if the setting for the HTTP adapter is smaller, the adapter could time out before the orchestration.</span></span> <span data-ttu-id="3f94e-106">これにより、プロセス、アダプターを制御します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-106">This gives the adapter control of the process.</span></span> <span data-ttu-id="3f94e-107">オーケストレーションがプロセスのコントロールである必要があります。そのため、そのタイムアウトの設定は、小さくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f94e-107">The orchestration must be in control of the process; therefore, its time-out setting must be smaller.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a><span data-ttu-id="3f94e-108">HTTP アダプターのタイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="3f94e-108">To set the time-out setting for the HTTP adapter</span></span>  
  
1.  <span data-ttu-id="3f94e-109">BizTalk エクスプ ローラーで、**送信ポート**、パブリック プロセス オーケストレーションを使用する HTTP 送信ポートをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f94e-109">In BizTalk Explorer, expand **Send ports**, and then double-click the HTTP send port used with the public-process orchestration.</span></span>  
  
2.  <span data-ttu-id="3f94e-110">送信ポートのプロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) の**アドレス (URI)** します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-110">In the Send Port Properties window, click the ellipsis button (**...**) for **Address (URI)**.</span></span>  
  
3.  <span data-ttu-id="3f94e-111">HTTP トランスポートのプロパティ ウィンドウの 全般 ウィンドウで、**要求のタイムアウト (秒)** ボックスに、適切なタイムアウト値を入力します。この値はより大きくする必要があります、**実行までの時間**の関連するプロセス PIP (Partner Interface) を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-111">In the HTTP Transport Properties window, in the General pane, in the **Request timeout (sec.)** box, type an appropriate value for the time-out. This value must be larger than the **Time to Perform** setting for the relevant Partner Interface Process (PIP).</span></span>  
  
4.  <span data-ttu-id="3f94e-112">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="3f94e-112">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a><span data-ttu-id="3f94e-113">パブリック プロセス オーケストレーションのタイムアウト設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="3f94e-113">To set the time-out setting for the public-process orchestration</span></span>  
  
1. <span data-ttu-id="3f94e-114">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**BizTalk Accelerator for RosettaNet 管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-114">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click  **BizTalk Accelerator for RosettaNet Management Console**.</span></span>  
  
2. <span data-ttu-id="3f94e-115">展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**プロセス構成設定**します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-115">Expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Process Configuration Settings**.</span></span>  
  
3. <span data-ttu-id="3f94e-116">タイムアウトを設定を設定する PIP を右クリックし、をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3f94e-116">Right-click the PIP that you want to set the time-out setting for, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="3f94e-117">プロパティ ダイアログ ボックスで、上、**アクティビティ** タブで、**実行までの時間**ボックスで、適切な値を設定すると、HTTP アダプターのタイムアウトよりも小さいを入力し、をクリックし、 **ok**.</span><span class="sxs-lookup"><span data-stu-id="3f94e-117">In theProperties dialog box, on the **Activity** tab, in the **Time to Perform** box, type an appropriate value that is smaller than the HTTP adapter time-out setting, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f94e-118">参照</span><span class="sxs-lookup"><span data-stu-id="3f94e-118">See Also</span></span>  
 [<span data-ttu-id="3f94e-119">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3f94e-119">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)