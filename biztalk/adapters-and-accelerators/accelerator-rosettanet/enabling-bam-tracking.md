---
title: BAM 追跡の有効化 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM tracking, enabling
- BAM tracking, disabling
ms.assetid: 3fee3315-fba7-4eea-89f3-6a061b450bb8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90fae70edf7f748de3790aeaa9e13e3381c44c48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210058"
---
# <a name="enabling-bam-tracking"></a><span data-ttu-id="47488-102">BAM 追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47488-102">Enabling BAM Tracking</span></span>
[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]<span data-ttu-id="47488-103"> では、BizTalk アクティビティ監視 (BAM) を使用した拡張追跡機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="47488-103"> supports enhanced tracking using BizTalk Activity Monitoring (BAM).</span></span> <span data-ttu-id="47488-104">BTARN 構成のグローバル プロパティの一部として追跡を有効にします。</span><span class="sxs-lookup"><span data-stu-id="47488-104">You enable tracking as part of the global properties of the BTARN configuration.</span></span> <span data-ttu-id="47488-105">追跡を有効にすると、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] はすべてのアグリーメントに対するメッセージを追跡します。</span><span class="sxs-lookup"><span data-stu-id="47488-105">After you enable tracking, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] tracks all messages for all agreements.</span></span> <span data-ttu-id="47488-106">既定では追跡が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="47488-106">By default, tracking is enabled.</span></span>  
  
 <span data-ttu-id="47488-107">追跡の詳細については、次を参照してください。[追跡強化](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)です。</span><span class="sxs-lookup"><span data-stu-id="47488-107">For more information about tracking, see [Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md).</span></span>  
  
### <a name="to-enable-or-disable-bam-tracking"></a><span data-ttu-id="47488-108">BAM の追跡を有効または無効にするには</span><span class="sxs-lookup"><span data-stu-id="47488-108">To enable or disable BAM tracking</span></span>  
  
1.  <span data-ttu-id="47488-109">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="47488-109">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="47488-110">右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノードをクリックしてスコープ ペイン**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="47488-110">Right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node in the scope pane, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="47488-111">**グローバル プロパティ**ダイアログ ボックスで、 **BAM の追跡を有効にする**の追跡を有効または無効にするには、このオプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="47488-111">In the **Global Properties** dialog box, select **Enable BAM Tracking** to enable tracking, or clear this option to disable it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47488-112">有効フラグを変更して追跡を有効または無効にした場合は、常に、パブリック処理と HTTP アダプターが実行されているすべてのサービスを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47488-112">Whenever you change the enable flag to enable or disable tracking, you have to restart all services on which the public processes and the HTTP adapter are running.</span></span> <span data-ttu-id="47488-113">この再開には、ホスト サービスと分離ホスト サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47488-113">This includes the host service and the isolated host service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47488-114">参照</span><span class="sxs-lookup"><span data-stu-id="47488-114">See Also</span></span>  
 <span data-ttu-id="47488-115">[構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="47488-115">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 <span data-ttu-id="47488-116">[拡張追跡](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="47488-116">[Enhanced Tracking](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md) </span></span>  
 [<span data-ttu-id="47488-117">BTARN 構成の管理</span><span class="sxs-lookup"><span data-stu-id="47488-117">Administering the BTARN Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)