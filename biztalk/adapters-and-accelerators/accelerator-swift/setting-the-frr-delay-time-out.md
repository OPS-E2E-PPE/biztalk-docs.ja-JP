---
title: FRR 遅延タイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, configuring delay time-out
ms.assetid: 62209bf6-56c8-483a-96d5-328bffc8b680
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42e141f1c2c3afff1049556c5bc041711695e9ca
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529982"
---
# <a name="setting-the-frr-delay-time-out"></a><span data-ttu-id="64258-102">FRR 遅延タイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="64258-102">Setting the FRR Delay Time-Out</span></span>
<span data-ttu-id="64258-103">無期限に FNN 応答を待機するはありませんが、いくつかの期間の後にタイムアウトに FRR オーケストレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64258-103">You must configure the FRR orchestration to time out after some duration, so it will not wait for the FNN response indefinitely.</span></span> <span data-ttu-id="64258-104">タイムアウト期間が経過すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム タイムアウト ハンドラーに、タイムアウト メッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="64258-104">If the time-out duration expires, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publishes the timed-out messages to a custom time-out handler.</span></span>  
  
### <a name="to-set-the-frr-delay-time-out"></a><span data-ttu-id="64258-105">FRR 遅延タイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="64258-105">To set the FRR delay time-out</span></span>  
  
1.  <span data-ttu-id="64258-106">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="64258-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="64258-107">レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk アクセラレータに移動します。</span><span class="sxs-lookup"><span data-stu-id="64258-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="64258-108">ロールは、[ロール] ノードで定義されているワークフロー内の位置に追加されます。</span><span class="sxs-lookup"><span data-stu-id="64258-108">The role will be added in the position in the workflow that is defined in the Roles node.</span></span> <span data-ttu-id="64258-109">その位置を変更するには、8 [ロール] ノード内のロールの順序を変更する手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64258-109">To change that position, you need to perform step 8 to change the order of the roles in the Roles node.</span></span>  
  
3.  <span data-ttu-id="64258-110">レジストリ エディターの右側のウィンドウでダブルクリック**DelayTimeout**します。</span><span class="sxs-lookup"><span data-stu-id="64258-110">In the right pane of the Registry Editor, double-click **DelayTimeout**.</span></span>  
  
4.  <span data-ttu-id="64258-111">**DWORD 値の編集** ダイアログ ボックスで、**値データ**ボックスに、16 進形式でタイムアウト期間を入力します。</span><span class="sxs-lookup"><span data-stu-id="64258-111">In the **Edit DWORD Value** dialog box, in the **Value data** box, type the time-out duration in hexadecimal format.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="64258-112">既定値、 **FRR DelayTimeout**プロパティが 600 秒 (258 16 進数)。</span><span class="sxs-lookup"><span data-stu-id="64258-112">The default value for the **FRR DelayTimeout** property is 600 seconds (258 Hexadecimal).</span></span>  
  
5.  <span data-ttu-id="64258-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="64258-113">Click **OK**.</span></span>