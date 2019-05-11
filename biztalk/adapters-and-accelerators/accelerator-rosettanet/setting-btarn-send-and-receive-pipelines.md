---
title: BTARN 送信の設定および受信パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send pipelines, modifying
- modifying, send pipelines
- receive pipelines, modifying
- modifying, receive pipelines
ms.assetid: 00960de0-3763-40aa-9e4b-1fedc7f1eea6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c195747a5c5501a3ac9ef57602f5bbdd5e0c0bfc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281830"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a><span data-ttu-id="3b58f-102">BTARN 送信の設定および受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="3b58f-102">Setting BTARN Send and Receive Pipelines</span></span>
<span data-ttu-id="3b58f-103">既定では、Microsoft によって[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]標準を使用して[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Send) と標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パートナーを作成するときに、パイプライン (Microsoft.Solutions.BTARN.Pipelines.Receive) を受信送信ポート。</span><span class="sxs-lookup"><span data-stu-id="3b58f-103">By default, Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline (Microsoft.Solutions.BTARN.Pipelines.Send) and the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline (Microsoft.Solutions.BTARN.Pipelines.Receive) when you create partner send ports.</span></span> <span data-ttu-id="3b58f-104">ただし、変更、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]既存の BizTalk パイプラインまたは作成したカスタム パイプラインを使用するよう構成します。</span><span class="sxs-lookup"><span data-stu-id="3b58f-104">However, you can change the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration to use an existing BizTalk pipeline or a custom pipeline that you have created.</span></span> <span data-ttu-id="3b58f-105">すべての取引先アグリーメント、およびすべてのパートナーとホーム組織は、使用して、同じ送信パイプラインと、同じ受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="3b58f-105">All trading partner agreements, and all partners and home organizations, use the same send pipeline and the same receive pipeline.</span></span>  
  
 <span data-ttu-id="3b58f-106">最初に、パートナーを作成するときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非同期のいずれかを使用するには、そのパートナーに対して 2 つの送信ポートを作成します。 もう 1 つの同期: \<*パートナー名*\>します。非同期の送信ポートと\<*パートナー名*\>します。同期送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="3b58f-106">When you first create a partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] creates two send ports for that partner to use, one asynchronous and one synchronous: \<*partner name*\>.Async send port and \<*partner name*\>.Sync send port.</span></span> <span data-ttu-id="3b58f-107">標準にこれらの送信ポートは、既定[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン、および同期送信ポートの受信パイプライン既定値は、標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="3b58f-107">These send ports default to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline, and the sync send port receive pipeline defaults to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b58f-108">変更、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]でパイプライン、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソールは、BizTalk エクスプ ローラーで直接変更したプロパティをリセット可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b58f-108">Changing the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console might reset properties that you changed directly in BizTalk Explorer.</span></span>  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a><span data-ttu-id="3b58f-109">BTARN を使用するパイプラインの受信を送信を変更するには</span><span class="sxs-lookup"><span data-stu-id="3b58f-109">To change the send or receive pipeline that BTARN uses</span></span>  
  
1. <span data-ttu-id="3b58f-110">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="3b58f-110">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="3b58f-111">BTARN 管理コンソールで、右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノード、およびクリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3b58f-111">In the BTARN Management Console, right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="3b58f-112">グローバル プロパティ ダイアログ ボックスで、ドロップダウン リストから別のパイプラインを選択し、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="3b58f-112">In the Global Properties dialog box, select a different pipeline from the drop-down list, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="3b58f-113">**ホスト インスタンス**ノードの下、 [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**ノードが停止して、ホストを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3b58f-113">In the **Host Instances** node under the [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration** node, stop and then restart the host.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3b58f-114">BizTalk Server を再起動する場合と、パイプラインの変更が反映のみ。</span><span class="sxs-lookup"><span data-stu-id="3b58f-114">The changes to the pipelines will only take effect if you restart the BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b58f-115">参照</span><span class="sxs-lookup"><span data-stu-id="3b58f-115">See Also</span></span>  
 <span data-ttu-id="3b58f-116">[構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="3b58f-116">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 [<span data-ttu-id="3b58f-117">BAM の追跡を有効にする</span><span class="sxs-lookup"><span data-stu-id="3b58f-117">Enabling BAM Tracking</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)