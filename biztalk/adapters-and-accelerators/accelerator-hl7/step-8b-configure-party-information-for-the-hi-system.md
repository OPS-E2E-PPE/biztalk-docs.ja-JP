---
title: '手順 8 b: HI System 用のパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d2cfc31d4bc42b599d7403006f8b44a8bfab447
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973747"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a><span data-ttu-id="184fa-102">手順 8 b: HI System 用のパーティ情報の構成</span><span class="sxs-lookup"><span data-stu-id="184fa-102">Step 8B: Configure Party Information for the HI System</span></span>
<span data-ttu-id="184fa-103">この手順では、HI System 用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="184fa-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="184fa-104">HI System パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="184fa-104">To configure the HI System party information</span></span>  
  
1. <span data-ttu-id="184fa-105">BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="184fa-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="184fa-106">パーティのプロパティ ダイアログ ボックスでの**名前**フィールドに「 **HIS**します。</span><span class="sxs-lookup"><span data-stu-id="184fa-106">In the Party Properties dialog box, in the **Name** field, type **HIS**.</span></span> <span data-ttu-id="184fa-107">(このボックスに入力した値は、元の HL7 メッセージ インスタンス qry ^ q01.txt MSH5 を一致する必要があります)</span><span class="sxs-lookup"><span data-stu-id="184fa-107">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH5.)</span></span>  
  
3. <span data-ttu-id="184fa-108">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="184fa-108">In the Console Tree, click **Send Ports**.</span></span>  
  
4. <span data-ttu-id="184fa-109">**送信ポート**ウィンドウの**名前**最初の行では、次のように選択します。 **HIS_Send**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="184fa-109">In the **Send Port** pane, for **Name** in the first row, select **HIS_Send**, and then click **OK**.</span></span>  
  
   <span data-ttu-id="184fa-110">続行する[手順 9: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)します。</span><span class="sxs-lookup"><span data-stu-id="184fa-110">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).</span></span>