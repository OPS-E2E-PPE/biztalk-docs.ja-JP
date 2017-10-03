---
title: "手順 1: バッチのバッチにするためのパーティ情報の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a93d774b-1282-40d9-836f-44abeb65f78e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 982b17fe3826a0e5c5ee2a42030ba020b755ab70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-configure-party-information-for-batch-inbatch-out"></a><span data-ttu-id="1904a-102">手順 1: 構成内のバッチの情報をパーティ/アウト バッチ</span><span class="sxs-lookup"><span data-stu-id="1904a-102">Step 1: Configure Party Information for Batch In/Batch Out</span></span>
<span data-ttu-id="1904a-103">バッチを有効にすると、パーティのバッチ処理の断片化をオフにするこの手順でのシナリオをバッチ処理/です。</span><span class="sxs-lookup"><span data-stu-id="1904a-103">In this step, you turn off fragmentation of batching for the party, enabling the Batch In/Batch Out scenario.</span></span> <span data-ttu-id="1904a-104">再起動する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を有効にする構成の変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1904a-104">You then restart [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] to enable the configuration change to take effect.</span></span>  
  
### <a name="to-turn-off-fragmentation-of-batching-for-the-party"></a><span data-ttu-id="1904a-105">パーティのバッチ処理の断片化をオフにするには</span><span class="sxs-lookup"><span data-stu-id="1904a-105">To turn off fragmentation of batching for the party</span></span>  
  
1.  <span data-ttu-id="1904a-106">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="1904a-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
2.  <span data-ttu-id="1904a-107">BTAHL7 構成エクスプ ローラーで、上、**パーティ**、左側のウィンドウ タブで、をクリックして**Tutorial_BatchSource**です。</span><span class="sxs-lookup"><span data-stu-id="1904a-107">In BTAHL7 Configuration Explorer, on the **Parties** tab in the left-hand pane, click **Tutorial_BatchSource**.</span></span>  
  
3.  <span data-ttu-id="1904a-108">クリックして、**バッチ定義**タブです。</span><span class="sxs-lookup"><span data-stu-id="1904a-108">Click the **Batch Definition** tab.</span></span>  
  
4.  <span data-ttu-id="1904a-109">選択**いいえ**の**断片化のために必要な**、順にクリック**保存**です。</span><span class="sxs-lookup"><span data-stu-id="1904a-109">Select **No** for **Fragmentation required**, and then click **Save**.</span></span>  
  
5.  <span data-ttu-id="1904a-110">ことを確認して**回復可能なインターチェンジのサポートに必要な**ドロップ ダウン リスト**False**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="1904a-110">Make sure that in **Recoverable Interchange Support Required** dropdown list **False** is selected.</span></span>  
  
 <span data-ttu-id="1904a-111">進みます[手順 2: 変更または作成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="1904a-111">Proceed to [Step 2: Modify or Create the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md).</span></span>