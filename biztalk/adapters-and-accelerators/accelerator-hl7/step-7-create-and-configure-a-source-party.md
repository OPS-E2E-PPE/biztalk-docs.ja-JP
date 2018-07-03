---
title: '手順 7: を作成し、送信元パーティの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4708a682047ced4fa33ae34781fd88d379c5e70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968931"
---
# <a name="step-7-create-and-configure-a-source-party"></a><span data-ttu-id="f3523-102">手順 7: を作成し、送信元パーティの構成</span><span class="sxs-lookup"><span data-stu-id="f3523-102">Step 7: Create and Configure a Source Party</span></span>
<span data-ttu-id="f3523-103">この手順では、ソース パーティを構成し、送信ポート、送信メッセージのメッセージ ヘッダーの変換を有効にするを割り当てますを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3523-103">In this step, you create and configure a source party, and assign send ports to enable message header transformations for the outgoing message.</span></span>  
  
### <a name="to-create-and-configure-a-source-party"></a><span data-ttu-id="f3523-104">作成および送信元パーティを構成するには</span><span class="sxs-lookup"><span data-stu-id="f3523-104">To create and configure a source party</span></span>  
  
1. <span data-ttu-id="f3523-105">BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="f3523-106">**パーティ プロパティ**ダイアログ ボックスで、名前フィールドに、型**Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-106">In the **Party Properties** dialog box, in the Name field, type **Tutorial_BatchSource**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="f3523-107">このボックスに入力した値が、元の FHS3.1 から[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]FragmentedInboundBatch.txt バッチのメッセージ。</span><span class="sxs-lookup"><span data-stu-id="f3523-107">The value that you type in this box is from FHS3.1 of the original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batched message, FragmentedInboundBatch.txt.</span></span>  
  
3. <span data-ttu-id="f3523-108">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-108">In the console tree, click **Send Ports**.</span></span>  
  
4. <span data-ttu-id="f3523-109">送信ポート ペインで、名前フィールドに、次のように選択します。 **Tutorial_2wayAck**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-109">In the Send Ports pane, for the Name field, select **Tutorial_2wayAck**.</span></span>  
  
5. <span data-ttu-id="f3523-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f3523-110">Click **OK**.</span></span>  
  
6. <span data-ttu-id="f3523-111">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-111">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
7. <span data-ttu-id="f3523-112">BTAHL7 構成エクスプ ローラーでの**パーティ**] タブで [ **Tutorial_BatchSource**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-112">In BTAHL7 Configuration Explorer, on the **Parties** tab, click **Tutorial_BatchSource**.</span></span>  
  
8. <span data-ttu-id="f3523-113">選択、**バッチ定義**BTAHL7 構成エクスプ ローラーのタブ。</span><span class="sxs-lookup"><span data-stu-id="f3523-113">Select the **Batch Definition** tab of BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="f3523-114">選択**はい**の**断片化のために必要な**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-114">Select **Yes** for **Fragmentation Required**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="f3523-115">選択、**受信確認**タブ。**受信確認の種類**を選択します**OriginalMode**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="f3523-115">Select the **Acknowledgment** tab. For **Acknowledgment Type**, select **OriginalMode**, and then click **Save**.</span></span>  
  
   <span data-ttu-id="f3523-116">続行する[手順 8: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="f3523-116">Proceed to [Step 8: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span></span>