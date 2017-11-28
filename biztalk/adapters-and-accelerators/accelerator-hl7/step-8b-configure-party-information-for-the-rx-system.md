---
title: "手順 8B: RX システム用のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29ab7194e0e1b81a773c61123de9171f1c65eb0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a><span data-ttu-id="7a714-102">手順 8B: RX システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="7a714-102">Step 8B: Configure Party Information for the RX System</span></span>
<span data-ttu-id="7a714-103">この手順では、RX システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="7a714-103">In this step, you configure the party information for the RX System.</span></span>  
  
### <a name="to-configure-the-rx-system-party-information"></a><span data-ttu-id="7a714-104">RX システム パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="7a714-104">To configure the RX System party information</span></span>  
  
1.  <span data-ttu-id="7a714-105">BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="7a714-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="7a714-106">パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_RXSystem**です。</span><span class="sxs-lookup"><span data-stu-id="7a714-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_RXSystem**.</span></span>  
  
3.  <span data-ttu-id="7a714-107">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7a714-107">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="7a714-108">送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_sendMsg_RX**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="7a714-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendMsg_RX**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="7a714-109">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="7a714-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="7a714-110">BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="7a714-110">In the BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="7a714-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7a714-111">Use this</span></span>|<span data-ttu-id="7a714-112">目的</span><span class="sxs-lookup"><span data-stu-id="7a714-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="7a714-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="7a714-113">**MSH3**</span></span>|<span data-ttu-id="7a714-114">型**BTAHL7**左のテキスト ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="7a714-114">Type **BTAHL7** in the left text box.</span></span>|  
    |<span data-ttu-id="7a714-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="7a714-115">**MSH5**</span></span>|<span data-ttu-id="7a714-116">型**Tutorial_RXSystem**左のテキスト ボックスにします。</span><span class="sxs-lookup"><span data-stu-id="7a714-116">Type **Tutorial_RXSystem** in the left text box.</span></span>|  
  
7.  <span data-ttu-id="7a714-117">をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7a714-117">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="7a714-118">進みます[手順 8 C: HI システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="7a714-118">Proceed to [Step 8C: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).</span></span>