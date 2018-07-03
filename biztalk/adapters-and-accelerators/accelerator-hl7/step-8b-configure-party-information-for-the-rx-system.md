---
title: '手順 8 b: RX System 用にパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2ed8dfaeb333c1b35ea64a5d52a53ebce509729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008403"
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a><span data-ttu-id="29e3a-102">手順 8 b: RX System 用にパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-102">Step 8B: Configure Party Information for the RX System</span></span>
<span data-ttu-id="29e3a-103">この手順では、RX System 用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-103">In this step, you configure the party information for the RX System.</span></span>  

### <a name="to-configure-the-rx-system-party-information"></a><span data-ttu-id="29e3a-104">RX System パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="29e3a-104">To configure the RX System party information</span></span>  

1. <span data-ttu-id="29e3a-105">右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。</span><span class="sxs-lookup"><span data-stu-id="29e3a-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="29e3a-106">パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_RXSystem**します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_RXSystem**.</span></span>  

3. <span data-ttu-id="29e3a-107">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-107">In the console tree, click **Send Ports**.</span></span>  

4. <span data-ttu-id="29e3a-108">送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_sendMsg_RX**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendMsg_RX**, and then click **OK**.</span></span>  

5. <span data-ttu-id="29e3a-109">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

6. <span data-ttu-id="29e3a-110">BTAHL7 構成エクスプ ローラーで、 **MSH マップ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="29e3a-110">In the BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  


   | <span data-ttu-id="29e3a-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="29e3a-111">Use this</span></span> |                    <span data-ttu-id="29e3a-112">目的</span><span class="sxs-lookup"><span data-stu-id="29e3a-112">To do this</span></span>                    |
   |----------|--------------------------------------------------|
   | <span data-ttu-id="29e3a-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="29e3a-113">**MSH3**</span></span> |      <span data-ttu-id="29e3a-114">型**BTAHL7**左側のテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="29e3a-114">Type **BTAHL7** in the left text box.</span></span>       |
   | <span data-ttu-id="29e3a-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="29e3a-115">**MSH5**</span></span> | <span data-ttu-id="29e3a-116">型**Tutorial_RXSystem**左側のテキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="29e3a-116">Type **Tutorial_RXSystem** in the left text box.</span></span> |


7. <span data-ttu-id="29e3a-117">クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="29e3a-117">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  

   <span data-ttu-id="29e3a-118">続行する[手順 8 C: HI System 用にパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="29e3a-118">Proceed to [Step 8C: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).</span></span>