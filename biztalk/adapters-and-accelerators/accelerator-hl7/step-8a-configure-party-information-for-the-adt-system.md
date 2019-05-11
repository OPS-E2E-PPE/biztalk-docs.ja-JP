---
title: 手順 8 a:ADT System 用にパーティ情報の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abeb65ac140bfcbc96c5c925960f38b539eeabf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287885"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a><span data-ttu-id="19491-102">手順 8 a:ADT System 用にパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="19491-102">Step 8A: Configure Party Information for the ADT System</span></span>
<span data-ttu-id="19491-103">この手順では、ADT System 用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="19491-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="19491-104">ADT System パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="19491-104">To configure the ADT System party information</span></span>  
  
1. <span data-ttu-id="19491-105">右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。</span><span class="sxs-lookup"><span data-stu-id="19491-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="19491-106">パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_ADTSystem**します。</span><span class="sxs-lookup"><span data-stu-id="19491-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_ADTSystem**.</span></span> <span data-ttu-id="19491-107">(このボックスに入力した値は、元の HL7 メッセージ インスタンス ADT^A03.txt MSH3 は) です。</span><span class="sxs-lookup"><span data-stu-id="19491-107">(The value you type in this box is from the original HL7 message instance, ADT^A03.txt MSH3.)</span></span>  
  
3. <span data-ttu-id="19491-108">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="19491-108">In the console tree, click **Send Ports**.</span></span>  
  
4. <span data-ttu-id="19491-109">送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_sendAck_ADT**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="19491-109">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendAck_ADT**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="19491-110">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="19491-110">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6. <span data-ttu-id="19491-111">BTAHL7 構成エクスプ ローラーで、**受信確認**タブ。**受信確認の種類**、 **EnhancedMode**します。</span><span class="sxs-lookup"><span data-stu-id="19491-111">In the BTAHL7 Configuration Explorer, select the **Acknowledgment** tab. For **Acknowledgment type**, select **EnhancedMode**.</span></span>  
  
7. <span data-ttu-id="19491-112">クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="19491-112">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
   <span data-ttu-id="19491-113">続行する[手順 8 b:RX System 用にパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="19491-113">Proceed to [Step 8B: Configure Party Information for the RX System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span></span>