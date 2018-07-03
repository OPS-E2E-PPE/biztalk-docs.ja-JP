---
title: '手順 8 C: HI System 用のパーティ情報の構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba42674a78bbed850c0994ec23c477c36b29c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970827"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a><span data-ttu-id="341fd-102">手順 8 C: HI System 用のパーティ情報の構成</span><span class="sxs-lookup"><span data-stu-id="341fd-102">Step 8C: Configure Party Information for the HI System</span></span>
<span data-ttu-id="341fd-103">この手順では、HI System 用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="341fd-103">In this step, you configure the party information for the HI System.</span></span>  

### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="341fd-104">HI System パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="341fd-104">To configure the HI System party information</span></span>  

1. <span data-ttu-id="341fd-105">右クリックし、BizTalk Server 管理コンソールで**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**。</span><span class="sxs-lookup"><span data-stu-id="341fd-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="341fd-106">パーティのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_HISystem**します。</span><span class="sxs-lookup"><span data-stu-id="341fd-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_HISystem**.</span></span>  

3. <span data-ttu-id="341fd-107">コンソール ツリーで、クリックして**送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="341fd-107">In the console tree, click **Send Ports**.</span></span>  

4. <span data-ttu-id="341fd-108">送信ポート] ペインで、[空白のフィールドをクリックします。、**名前**列で、 **Tutorial_MllpSend**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="341fd-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_MllpSend**, and then click **OK**.</span></span>  

5. <span data-ttu-id="341fd-109">クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。</span><span class="sxs-lookup"><span data-stu-id="341fd-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

6. <span data-ttu-id="341fd-110">BTAHL7 構成エクスプ ローラーで、選択、 **MSH マップ**タブをクリックし、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="341fd-110">In BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  


   | <span data-ttu-id="341fd-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="341fd-111">Use this</span></span>  |                                             <span data-ttu-id="341fd-112">目的</span><span class="sxs-lookup"><span data-stu-id="341fd-112">To do this</span></span>                                             |
   |-----------|----------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="341fd-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="341fd-113">**MSH3**</span></span>  | <span data-ttu-id="341fd-114">型**BTAHL7**、 **IE**、および**UUID**最初に 2 番目、および第 3 にメッセージ ボックスをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="341fd-114">Type **BTAHL7**, **IE**, and **UUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="341fd-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="341fd-115">**MSH5**</span></span>  | <span data-ttu-id="341fd-116">型**HI**、**システム**、および**GUID**最初に 2 番目、および第 3 にメッセージ ボックスをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="341fd-116">Type **HI**, **System**, and **GUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="341fd-117">**MSH9**</span><span class="sxs-lookup"><span data-stu-id="341fd-117">**MSH9**</span></span>  |           <span data-ttu-id="341fd-118">型**ADT**と**A04**最初と 2 番目のメッセージ ボックスに、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="341fd-118">Type **ADT** and **A04** in the first and second message boxes, respectively.</span></span>            |
   | <span data-ttu-id="341fd-119">**MSH12**</span><span class="sxs-lookup"><span data-stu-id="341fd-119">**MSH12**</span></span> |                                           <span data-ttu-id="341fd-120">型**2.4**します。</span><span class="sxs-lookup"><span data-stu-id="341fd-120">Type **2.4**.</span></span>                                            |
   | <span data-ttu-id="341fd-121">**MSH15**</span><span class="sxs-lookup"><span data-stu-id="341fd-121">**MSH15**</span></span> |         <span data-ttu-id="341fd-122">選択**SU**メッセージの転送が成功した後に受信確認を送信します。</span><span class="sxs-lookup"><span data-stu-id="341fd-122">Select **SU** to send acknowledgments after successful transmission of a message.</span></span>          |
   | <span data-ttu-id="341fd-123">**MSH16**</span><span class="sxs-lookup"><span data-stu-id="341fd-123">**MSH16**</span></span> |                            <span data-ttu-id="341fd-124">選択**NE**受信確認を送信しません。</span><span class="sxs-lookup"><span data-stu-id="341fd-124">Select **NE** to never send acknowledgments.</span></span>                            |


7. <span data-ttu-id="341fd-125">クリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="341fd-125">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="341fd-126">構成情報がこのシナリオで必要ないため、BTAHL7 インターフェイス エンジンのシステムでは、パーティ情報を作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="341fd-126">You do not need to create party information for the BTAHL7 Interface Engine System, because configuration information is not required for this scenario.</span></span>  

   <span data-ttu-id="341fd-127">続行する[手順 9: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="341fd-127">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span></span>