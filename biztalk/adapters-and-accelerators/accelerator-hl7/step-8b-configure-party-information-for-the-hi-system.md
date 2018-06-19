---
title: '手順 8B: HI システム用のパーティ情報を構成する |Microsoft ドキュメント'
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
ms.openlocfilehash: 460840cf3bbbd6556b1684b25851a16778be92b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206314"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a><span data-ttu-id="988a4-102">手順 8B: HI システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="988a4-102">Step 8B: Configure Party Information for the HI System</span></span>
<span data-ttu-id="988a4-103">この手順では、HI システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="988a4-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="988a4-104">HI システム パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="988a4-104">To configure the HI System party information</span></span>  
  
1.  <span data-ttu-id="988a4-105">BizTalk 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="988a4-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="988a4-106">パーティのプロパティ ダイアログ ボックスで、**名前**フィールドに「 **HIS**です。</span><span class="sxs-lookup"><span data-stu-id="988a4-106">In the Party Properties dialog box, in the **Name** field, type **HIS**.</span></span> <span data-ttu-id="988a4-107">(このボックスに入力した値は、元の HL7 メッセージ インスタンス QRY^Q01.txt MSH5 を一致する必要があります)</span><span class="sxs-lookup"><span data-stu-id="988a4-107">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH5.)</span></span>  
  
3.  <span data-ttu-id="988a4-108">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="988a4-108">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="988a4-109">**送信ポート** ウィンドウの**名前**最初の行では、次のように選択します。 **HIS_Send**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="988a4-109">In the **Send Port** pane, for **Name** in the first row, select **HIS_Send**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="988a4-110">進みます[手順 9: BizTalk Server を再起動して](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)です。</span><span class="sxs-lookup"><span data-stu-id="988a4-110">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).</span></span>