---
title: BTARN 送信を設定し、受信パイプライン |Microsoft ドキュメント
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
ms.openlocfilehash: a6f5e996b7046e94c90df0269381391a3aed3084
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964512"
---
# <a name="setting-btarn-send-and-receive-pipelines"></a><span data-ttu-id="32c83-102">BTARN 送信を設定し、受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="32c83-102">Setting BTARN Send and Receive Pipelines</span></span>
<span data-ttu-id="32c83-103">既定では、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]標準を使用して[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]送信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Send) と標準[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]を作成するときに、受信パイプライン (Microsoft.Solutions.BTARN.Pipelines.Receive)パートナー送信ポート。</span><span class="sxs-lookup"><span data-stu-id="32c83-103">By default, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline (Microsoft.Solutions.BTARN.Pipelines.Send) and the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline (Microsoft.Solutions.BTARN.Pipelines.Receive) when you create partner send ports.</span></span> <span data-ttu-id="32c83-104">ただし、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 構成を変更して、既存の BizTalk パイプラインまたは作成したカスタム パイプラインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="32c83-104">However, you can change the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] configuration to use an existing BizTalk pipeline or a custom pipeline that you have created.</span></span> <span data-ttu-id="32c83-105">すべての取引先アグリーメント、およびすべてのパートナーとホーム組織は、同じ送信パイプラインと同じ受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="32c83-105">All trading partner agreements, and all partners and home organizations, use the same send pipeline and the same receive pipeline.</span></span>  
  
 <span data-ttu-id="32c83-106">最初に、パートナーを作成するときに[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]非同期のいずれかを使用するには、そのパートナーに対して 2 つの送信ポートを作成し、1 つの同期: \<*パートナー名*\>です。非同期の送信ポートと\<*パートナー名*\>です。同期送信ポートです。</span><span class="sxs-lookup"><span data-stu-id="32c83-106">When you first create a partner, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] creates two send ports for that partner to use, one asynchronous and one synchronous: \<*partner name*\>.Async send port and \<*partner name*\>.Sync send port.</span></span> <span data-ttu-id="32c83-107">これらの送信ポートは、既定で標準の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインに設定され、同期送信ポート受信パイプラインは、既定で標準の [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 受信パイプラインに設定されます。</span><span class="sxs-lookup"><span data-stu-id="32c83-107">These send ports default to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] send pipeline, and the sync send port receive pipeline defaults to the standard [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receive pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32c83-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理コンソールで [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パイプラインを変更すると、BizTalk エクスプローラーで直接変更したプロパティがリセットされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="32c83-108">Changing the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipeline in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console might reset properties that you changed directly in BizTalk Explorer.</span></span>  
  
### <a name="to-change-the-send-or-receive-pipeline-that-btarn-uses"></a><span data-ttu-id="32c83-109">BTARN が使用する送信パイプラインまたは受信パイプラインを変更するには</span><span class="sxs-lookup"><span data-stu-id="32c83-109">To change the send or receive pipeline that BTARN uses</span></span>  
  
1.  <span data-ttu-id="32c83-110">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="32c83-110">Click **Start**, point to **Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="32c83-111">BTARN 管理コンソールを右クリックし、[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]ノードをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="32c83-111">In the BTARN Management Console, right-click the [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] node, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="32c83-112">グローバル プロパティ ダイアログ ボックスで、ドロップダウン リストから、別のパイプラインを選択し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="32c83-112">In the Global Properties dialog box, select a different pipeline from the drop-down list, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="32c83-113">**ホスト インスタンス**ノードの下、 [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**ノードが停止してから、ホストを再起動します。</span><span class="sxs-lookup"><span data-stu-id="32c83-113">In the **Host Instances** node under the [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration** node, stop and then restart the host.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="32c83-114">パイプラインの変更は、BizTalk Server を再起動することにより初めて有効になります。</span><span class="sxs-lookup"><span data-stu-id="32c83-114">The changes to the pipelines will only take effect if you restart the BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c83-115">参照</span><span class="sxs-lookup"><span data-stu-id="32c83-115">See Also</span></span>  
 <span data-ttu-id="32c83-116">[構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md) </span><span class="sxs-lookup"><span data-stu-id="32c83-116">[Manage configuration, certificates, databases, and security](manage-configuration-certificates-databases-security.md) </span></span>  
 [<span data-ttu-id="32c83-117">BAM の追跡を有効にする</span><span class="sxs-lookup"><span data-stu-id="32c83-117">Enabling BAM Tracking</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)