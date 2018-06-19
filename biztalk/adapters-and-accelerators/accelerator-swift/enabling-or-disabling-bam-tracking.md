---
title: 有効化または BAM の追跡を無効化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Repair and New Submission, BAM tracking
- BAM tracking
ms.assetid: 07896fab-88a0-4759-8547-16edcd1eebc0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1132c41e9a017e42139d988d1588f79d7d3afaa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207394"
---
# <a name="enabling-or-disabling-bam-tracking"></a><span data-ttu-id="a1d73-102">有効にするか、BAM 追跡を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a1d73-102">Enabling or Disabling BAM Tracking</span></span>
<span data-ttu-id="a1d73-103">有効にするにまたは BAM Message Repair and 新しい転送プロセスでは、トランザクションを持つプロセスの中であっても、任意の時点では、追跡を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1d73-103">You can enable or disable BAM tracking at any point, even while the Message Repair and New Transmission process has transactions in process.</span></span> <span data-ttu-id="a1d73-104">ただし、トランザクションは、プロセス中に BAM の追跡を無効にする場合、BAM データできない可能性がありますこれらのトランザクションの完了します。</span><span class="sxs-lookup"><span data-stu-id="a1d73-104">However, if you disable BAM tracking while transactions are in process, the BAM data may be incomplete for those transactions.</span></span> <span data-ttu-id="a1d73-105">このような場合、履歴テーブルにはまだすべてのインスタンスの正確なデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1d73-105">If this occurs, the history table will still contain accurate data for all instances.</span></span>  
  
 <span data-ttu-id="a1d73-106">有効化または BAM A4SWIFT コンポーネント構成プロセスの一部として追跡を無効にする方法については、次を参照してください。 [A4SWIFT のプロパティの設定](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="a1d73-106">For information about enabling or disabling BAM tracking as part of the A4SWIFT component configuration process, see [Setting A4SWIFT Properties](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="a1d73-107">有効にするにまたは BAM の追跡を無効にするには</span><span class="sxs-lookup"><span data-stu-id="a1d73-107">To enable or disable BAM Tracking</span></span>  
  
1.  <span data-ttu-id="a1d73-108">プロファイル Web クライアントを右クリックして**BizTalk Accelerator 用 SWIFT**をクリックしてコンソール ツリーで、**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="a1d73-108">In the Profile Web Client, right-click **BizTalk Accelerator for SWIFT** in the console tree, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a1d73-109">グローバル プロパティ ダイアログ ボックスで、BAM の選択を解除して追跡を無効にする**BAM の追跡を有効にする**、または BAM を選択して追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1d73-109">In the Global Properties dialog box, disable BAM tracking by deselecting **Enable BAM Tracking**, or enable BAM tracking by selecting it.</span></span>  
  
3.  <span data-ttu-id="a1d73-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1d73-110">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="a1d73-111">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、し**プラットフォームの設定**です。</span><span class="sxs-lookup"><span data-stu-id="a1d73-111">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, and then **Platform Settings**.</span></span> <span data-ttu-id="a1d73-112">をクリックして**のホスト インスタンスの**します。</span><span class="sxs-lookup"><span data-stu-id="a1d73-112">Click **Host Instances**.</span></span>  
  
5.  <span data-ttu-id="a1d73-113">詳細ウィンドウで、ホスト インスタンスを右クリックし、をクリックして**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="a1d73-113">In the details pane, right-click the host instance , and then click **Restart**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d73-114">参照</span><span class="sxs-lookup"><span data-stu-id="a1d73-114">See Also</span></span>  
 [<span data-ttu-id="a1d73-115">A4SWIFT のプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="a1d73-115">Setting A4SWIFT Properties</span></span>](../../adapters-and-accelerators/accelerator-swift/setting-a4swift-properties.md)