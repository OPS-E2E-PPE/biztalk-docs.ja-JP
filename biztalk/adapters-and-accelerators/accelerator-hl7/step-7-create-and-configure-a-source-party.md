---
title: "手順 7: を作成し、送信元パーティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32539b1c352ac1fd2b60d2acd4c5ee975e2c3d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-and-configure-a-source-party"></a><span data-ttu-id="ec24c-102">手順 7: を作成し、送信元パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ec24c-102">Step 7: Create and Configure a Source Party</span></span>
<span data-ttu-id="ec24c-103">このステップでは、送信元パーティを構成して、送信メッセージのメッセージ ヘッダーの変換を有効にする送信ポートを割り当てるを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec24c-103">In this step, you create and configure a source party, and assign send ports to enable message header transformations for the outgoing message.</span></span>  
  
### <a name="to-create-and-configure-a-source-party"></a><span data-ttu-id="ec24c-104">作成および送信元パーティの構成</span><span class="sxs-lookup"><span data-stu-id="ec24c-104">To create and configure a source party</span></span>  
  
1.  <span data-ttu-id="ec24c-105">BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="ec24c-106">**パーティ プロパティ**ダイアログ ボックスの [名前] フィールドの種類で**Tutorial_BatchSource**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-106">In the **Party Properties** dialog box, in the Name field, type **Tutorial_BatchSource**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec24c-107">このボックスに入力した値は、元の FHS3.1 から[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]FragmentedInboundBatch.txt、バッチ処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ec24c-107">The value that you type in this box is from FHS3.1 of the original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batched message, FragmentedInboundBatch.txt.</span></span>  
  
3.  <span data-ttu-id="ec24c-108">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="ec24c-109">送信ポート ペインの 名前 フィールドの選択**Tutorial_2wayAck**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-109">In the Send Ports pane, for the Name field, select **Tutorial_2wayAck**.</span></span>  
  
5.  <span data-ttu-id="ec24c-110">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec24c-110">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="ec24c-111">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-111">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
7.  <span data-ttu-id="ec24c-112">BTAHL7 構成エクスプ ローラーで、上、**パーティ** タブで、をクリックして**Tutorial_BatchSource**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-112">In BTAHL7 Configuration Explorer, on the **Parties** tab, click **Tutorial_BatchSource**.</span></span>  
  
8.  <span data-ttu-id="ec24c-113">選択、**バッチ定義**BTAHL7 構成エクスプ ローラーのタブ。</span><span class="sxs-lookup"><span data-stu-id="ec24c-113">Select the **Batch Definition** tab of BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="ec24c-114">選択**[はい]**の**断片化のために必要な**、順にクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-114">Select **Yes** for **Fragmentation Required**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="ec24c-115">選択、**受信確認**タブです。**受信確認の種類** **OriginalMode**、順にクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-115">Select the **Acknowledgment** tab. For **Acknowledgment Type**, select **OriginalMode**, and then click **Save**.</span></span>  
  
 <span data-ttu-id="ec24c-116">進みます[手順 8: BizTalk Server を再起動して](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="ec24c-116">Proceed to [Step 8: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span></span>