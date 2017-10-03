---
title: "プログラミング Guide1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, programming guide
- programming guide
ms.assetid: fb2d5e3b-1907-49c4-806d-a2604c702322
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb77912db0bfb3eaf5cc4ad22c4737d443d90998
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="programming-guide"></a><span data-ttu-id="143d1-102">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="143d1-102">Programming Guide</span></span>
<span data-ttu-id="143d1-103">[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]プログラミング ガイド BTAHL7 でコードを記述する開発者向けの概念と手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="143d1-103">The [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Programming Guide explains concepts and procedures for developers writing code with BTAHL7.</span></span> <span data-ttu-id="143d1-104">このガイドを使用すると組み合わせて[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="143d1-104">Use this guide in conjunction with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="143d1-105">このガイドを読む前に理解すると[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]開発、 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、および[HL7 アクセラレータと使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)です。</span><span class="sxs-lookup"><span data-stu-id="143d1-105">Before reading this guide, you should be familiar with [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] development, [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)], and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="143d1-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="143d1-106">In This Section</span></span>  
  
-   [<span data-ttu-id="143d1-107">HL7 メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="143d1-107">Processing HL7 Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)  
  
-   [<span data-ttu-id="143d1-108">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="143d1-108">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)  
  
-   [<span data-ttu-id="143d1-109">HL7 2. XML スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="143d1-109">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)  
  
-   [<span data-ttu-id="143d1-110">MLLP でエンコードされたメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="143d1-110">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)  
  
-   [<span data-ttu-id="143d1-111">作成して、受信確認の処理</span><span class="sxs-lookup"><span data-stu-id="143d1-111">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)  
  
-   [<span data-ttu-id="143d1-112">動的なデータ検証を使用します。</span><span class="sxs-lookup"><span data-stu-id="143d1-112">Using Dynamic Data Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-dynamic-data-validation.md)  
  
-   [<span data-ttu-id="143d1-113">監査イベントおよびログ記録用の WMI シンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="143d1-113">Creating a WMI Sink for Auditing and Logging Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-a-wmi-sink-for-auditing-and-logging-events.md)  
  
-   [<span data-ttu-id="143d1-114">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="143d1-114">Additional Resources</span></span>](../../adapters-and-accelerators/accelerator-hl7/additional-resources.md)