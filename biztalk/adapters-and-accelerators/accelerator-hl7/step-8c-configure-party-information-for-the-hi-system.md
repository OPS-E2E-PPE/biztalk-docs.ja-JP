---
title: "手順 8 C: HI システム用のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f0b9e1538ea667eab2299a1a02021c1237bc985
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a><span data-ttu-id="157e6-102">手順 8 C: HI システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="157e6-102">Step 8C: Configure Party Information for the HI System</span></span>
<span data-ttu-id="157e6-103">この手順では、HI システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="157e6-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="157e6-104">HI システム パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="157e6-104">To configure the HI System party information</span></span>  
  
1.  <span data-ttu-id="157e6-105">BizTalk Server 管理コンソールで、右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="157e6-106">パーティのプロパティ ダイアログ ボックスで、**名前**ボックスに、入力**Tutorial_HISystem**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_HISystem**.</span></span>  
  
3.  <span data-ttu-id="157e6-107">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-107">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="157e6-108">送信ポート] ペインで [空白のフィールドをクリックして、**名前**列で、選択**Tutorial_MllpSend**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_MllpSend**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="157e6-109">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="157e6-110">BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="157e6-110">In BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="157e6-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="157e6-111">Use this</span></span>|<span data-ttu-id="157e6-112">目的</span><span class="sxs-lookup"><span data-stu-id="157e6-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="157e6-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="157e6-113">**MSH3**</span></span>|<span data-ttu-id="157e6-114">型**BTAHL7**、 **IE**、および**UUID**最初に、2 番目し、3 番目にメッセージ ボックスのそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="157e6-114">Type **BTAHL7**, **IE**, and **UUID** in the first, second, and third message boxes, respectively.</span></span>|  
    |<span data-ttu-id="157e6-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="157e6-115">**MSH5**</span></span>|<span data-ttu-id="157e6-116">型**HI**、**システム**、および**GUID**最初に、2 番目し、3 番目にメッセージ ボックスのそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="157e6-116">Type **HI**, **System**, and **GUID** in the first, second, and third message boxes, respectively.</span></span>|  
    |<span data-ttu-id="157e6-117">**MSH9**</span><span class="sxs-lookup"><span data-stu-id="157e6-117">**MSH9**</span></span>|<span data-ttu-id="157e6-118">型**ADT**と**A04**番目と 2 番目のメッセージ ボックスに、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="157e6-118">Type **ADT** and **A04** in the first and second message boxes, respectively.</span></span>|  
    |<span data-ttu-id="157e6-119">**MSH12**</span><span class="sxs-lookup"><span data-stu-id="157e6-119">**MSH12**</span></span>|<span data-ttu-id="157e6-120">型**2.4**です。</span><span class="sxs-lookup"><span data-stu-id="157e6-120">Type **2.4**.</span></span>|  
    |<span data-ttu-id="157e6-121">**MSH15**</span><span class="sxs-lookup"><span data-stu-id="157e6-121">**MSH15**</span></span>|<span data-ttu-id="157e6-122">選択**SU**メッセージの転送が成功した後に受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="157e6-122">Select **SU** to send acknowledgments after successful transmission of a message.</span></span>|  
    |<span data-ttu-id="157e6-123">**MSH16**</span><span class="sxs-lookup"><span data-stu-id="157e6-123">**MSH16**</span></span>|<span data-ttu-id="157e6-124">選択**NE**受信確認を送信しないようにします。</span><span class="sxs-lookup"><span data-stu-id="157e6-124">Select **NE** to never send acknowledgments.</span></span>|  
  
7.  <span data-ttu-id="157e6-125">をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="157e6-125">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="157e6-126">構成情報がこのシナリオで必要ないため、BTAHL7 インターフェイス エンジンのシステムでは、パーティ情報を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="157e6-126">You do not need to create party information for the BTAHL7 Interface Engine System, because configuration information is not required for this scenario.</span></span>  
  
 <span data-ttu-id="157e6-127">進みます[手順 9: BizTalk Server を再起動して](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="157e6-127">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span></span>