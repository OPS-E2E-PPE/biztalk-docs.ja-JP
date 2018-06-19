---
title: FRR 遅延タイムアウトの設定 |Microsoft ドキュメント
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
ms.openlocfilehash: fbf4c08984876627c0f11f935b0be3e32769b5f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214002"
---
# <a name="setting-the-frr-delay-time-out"></a><span data-ttu-id="62c09-102">FRR 遅延タイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="62c09-102">Setting the FRR Delay Time-Out</span></span>
<span data-ttu-id="62c09-103">これは待機しません FNN 応答を無期限にようにいくつかの期間の後にタイムアウトに FRR オーケストレーションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62c09-103">You must configure the FRR orchestration to time out after some duration, so it will not wait for the FNN response indefinitely.</span></span> <span data-ttu-id="62c09-104">タイムアウト期間が経過すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]タイムアウトのカスタム ハンドラーにタイムアウトになったメッセージを公開します。</span><span class="sxs-lookup"><span data-stu-id="62c09-104">If the time-out duration expires, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] publishes the timed-out messages to a custom time-out handler.</span></span>  
  
### <a name="to-set-the-frr-delay-time-out"></a><span data-ttu-id="62c09-105">FRR 遅延タイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="62c09-105">To set the FRR delay time-out</span></span>  
  
1.  <span data-ttu-id="62c09-106">をクリックして**開始**、 をクリックして**実行**、型**regedit**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="62c09-106">Click **Start**, click **Run**, type **regedit**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="62c09-107">レジストリ エディターの左側のウィンドウでは、SWIFT/FRR のマイ コンピューター/HKEY_LOCAL_MACHINE/ソフトウェア/Microsoft/BizTalk Accelerator に移動します。</span><span class="sxs-lookup"><span data-stu-id="62c09-107">In the left pane of the Registry Editor, move to My Computer/HKEY_LOCAL_MACHINE/SOFTWARE/Microsoft/BizTalk Accelerator for SWIFT/FRR.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="62c09-108">ロールは、[ロール] ノードで定義されている、ワークフロー内の位置に追加されます。</span><span class="sxs-lookup"><span data-stu-id="62c09-108">The role will be added in the position in the workflow that is defined in the Roles node.</span></span> <span data-ttu-id="62c09-109">その位置を変更するには、手順 8 を実行し、[ロール] ノード内のロールの順序を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62c09-109">To change that position, you need to perform step 8 to change the order of the roles in the Roles node.</span></span>  
  
3.  <span data-ttu-id="62c09-110">レジストリ エディターの右側のウィンドウでダブルクリック**DelayTimeout**です。</span><span class="sxs-lookup"><span data-stu-id="62c09-110">In the right pane of the Registry Editor, double-click **DelayTimeout**.</span></span>  
  
4.  <span data-ttu-id="62c09-111">**DWORD 値の編集** ダイアログ ボックスで、**値のデータ**ボックスに、16 進形式でタイムアウト期間を入力します。</span><span class="sxs-lookup"><span data-stu-id="62c09-111">In the **Edit DWORD Value** dialog box, in the **Value data** box, type the time-out duration in hexadecimal format.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62c09-112">既定値、 **FRR DelayTimeout**プロパティは 600 秒 (258 16 進数)。</span><span class="sxs-lookup"><span data-stu-id="62c09-112">The default value for the **FRR DelayTimeout** property is 600 seconds (258 Hexadecimal).</span></span>  
  
5.  <span data-ttu-id="62c09-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62c09-113">Click **OK**.</span></span>