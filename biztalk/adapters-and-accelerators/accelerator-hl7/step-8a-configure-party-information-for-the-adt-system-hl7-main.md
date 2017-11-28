---
title: "手順 8 a.: ADT System_hl7_main のパーティ情報を構成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9285b926edb5ca4f1dccf18ed2d5f76b3af14ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a><span data-ttu-id="865ee-102">手順 8 a.: ADT System_hl7_main のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="865ee-102">Step 8A: Configure Party Information for the ADT System_hl7_main</span></span>
<span data-ttu-id="865ee-103">この手順では、ADT システム用のパーティ情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="865ee-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="865ee-104">ADT システム パーティ情報を構成するには</span><span class="sxs-lookup"><span data-stu-id="865ee-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="865ee-105">BizTalk 管理コンソールで  **BizTalk Server 管理コンソール**、順に展開**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-105">In the BizTalk Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="865ee-106">右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-106">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="865ee-107">パーティのプロパティ ダイアログ ボックスで、**名前**フィールドに「 **ADT**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-107">In the Party Properties dialog box, in the **Name** field, type **ADT**.</span></span> <span data-ttu-id="865ee-108">(このボックスに入力した値は、元の HL7 メッセージ インスタンス QRY^Q01.txt MSH3 を一致する必要があります)</span><span class="sxs-lookup"><span data-stu-id="865ee-108">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="865ee-109">コンソール ツリーでクリックして**送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-109">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="865ee-110">**送信ポート** ウィンドウの**名前**最初の行では、次のように選択します。 **ADT_Send**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-110">In the **Send Port** pane, for **Name** in the first row, select **ADT_Send**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="865ee-111">をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン > Accelerator 用 HL7**、クリックして**BTAHL7構成のエクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-111">Click **Start**, point to **Programs**, point to **Microsoft  BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="865ee-112">BTAHL7 構成エクスプ ローラーで、をクリックして、**受信確認**タブです。**受信確認の種類** **EnhancedMode**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-112">In BTAHL7 Configuration Explorer, click the **Acknowledgment** tab. For **Acknowledgment Type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="865ee-113">Inboiund メッセージ ウィンドウで、受信確認プロパティの**MSH15 - 受信確認の種類をそのまま使用** **AL**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-113">In the Acknowledgment Properties in Inboiund Message pane, for **MSH15 - Accept Acknowledgment Type**, select **AL**.</span></span>  
  
8.  <span data-ttu-id="865ee-114">受信確認プロパティ ウィンドウの**MSH16 - アプリケーションの受信確認の種類** **NE**です。</span><span class="sxs-lookup"><span data-stu-id="865ee-114">In the Acknowledgment Properties pane, for **MSH16 - Application Acknowledgment Type**, select **NE**.</span></span>  
  
9. <span data-ttu-id="865ee-115">をクリックして**保存**、BTAHL7 構成エクスプ ローラーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="865ee-115">Click **Save**, and then close BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="865ee-116">進みます[手順 8B: HI システム用のパーティ情報を構成する](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="865ee-116">Proceed to [Step 8B: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).</span></span>