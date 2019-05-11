---
title: 手順 1:バッチのバッチでアウト用にパーティ情報の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 188b7cae45ac9cae0076ed129e92147f276a79d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289073"
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="aaf8b-102">手順 1:バッチ用にパーティ情報の構成/バッチ アウト</span><span class="sxs-lookup"><span data-stu-id="aaf8b-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="aaf8b-103">バッチを有効にすると、パーティのバッチ処理の断片化をオフにするこの手順で/バッチ アウト シナリオ。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="aaf8b-104">再起動する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を有効にする構成変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="aaf8b-105">パーティのバッチ処理の断片化をオフにするには</span><span class="sxs-lookup"><span data-stu-id="aaf8b-105">To turn off fragmentation of batching for the party</span></span>  
  
1. <span data-ttu-id="aaf8b-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**をクリックして**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2. <span data-ttu-id="aaf8b-107">BTAHL7 構成エクスプ ローラーでの**パーティ**左側のウィンドウ] タブで [ **Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3. <span data-ttu-id="aaf8b-108">をクリックして、**バッチ定義**タブ。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-108">Click the **Batch Definition** tab.</span></span>  
  
4. <span data-ttu-id="aaf8b-109">選択**いいえ**の**断片化のために必要な**、順にクリックします**保存**します。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5. <span data-ttu-id="aaf8b-110">確認します**回復可能なインターチェンジ サポート必要**ドロップダウン リスト**False**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
   <span data-ttu-id="aaf8b-111">続行する[手順 2。変更または作成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)します。</span><span class="sxs-lookup"><span data-stu-id="aaf8b-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>