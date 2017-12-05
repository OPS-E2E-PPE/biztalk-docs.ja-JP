---
title: "手順 8 a.: ADT システム用のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42b92e3b55cd4de181103e28526abf3ecde29412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a><span data-ttu-id="68813-102">手順 8 a.: ADT システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="68813-102">Step 8A: Configure Party Information for the ADT System</span></span>
<span data-ttu-id="68813-103">この手順では、ADT システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="68813-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="68813-104">ADT システム パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="68813-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="68813-105">BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="68813-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="68813-106">パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_ADTSystem**です。</span><span class="sxs-lookup"><span data-stu-id="68813-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_ADTSystem**.</span></span> <span data-ttu-id="68813-107">(このボックスに入力した値は、元の HL7 メッセージ インスタンス ADT^A03.txt MSH3 は) です。</span><span class="sxs-lookup"><span data-stu-id="68813-107">(The value you type in this box is from the original HL7 message instance, ADT^A03.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="68813-108">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="68813-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="68813-109">送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_sendAck_ADT**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="68813-109">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendAck_ADT**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="68813-110">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="68813-110">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="68813-111">BTAHL7 構成エクスプ ローラーで、選択、**受信確認**タブです。**受信確認の種類** **EnhancedMode**です。</span><span class="sxs-lookup"><span data-stu-id="68813-111">In the BTAHL7 Configuration Explorer, select the **Acknowledgment** tab. For **Acknowledgment type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="68813-112">をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="68813-112">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="68813-113">進みます[手順 8B: RX システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="68813-113">Proceed to [Step 8B: Configure Party Information for the RX System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span></span>