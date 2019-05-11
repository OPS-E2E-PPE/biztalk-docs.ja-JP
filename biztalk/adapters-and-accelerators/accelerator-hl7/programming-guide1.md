---
title: プログラミング Guide1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, programming guide
- programming guide
ms.assetid: fb2d5e3b-1907-49c4-806d-a2604c702322
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8622f8bd3c20cc9b3c983a609a4d3aea310db4e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289982"
---
# <a name="programming-guide"></a><span data-ttu-id="a1d66-102">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a1d66-102">Programming Guide</span></span>
<span data-ttu-id="a1d66-103">Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]プログラミング ガイド BTAHL7 でコードを記述する開発者向けの概念と手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="a1d66-103">The Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] Programming Guide explains concepts and procedures for developers writing code with BTAHL7.</span></span> <span data-ttu-id="a1d66-104">このガイドを使用して、Microsoft と組み合わせて[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a1d66-104">Use this guide in conjunction with Microsoft [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1d66-105">このガイドを読む前に理解しておく必要があります[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]開発、BizTalk Server、および[HL7 アクセラレータや使用可能な BizTalk ツールの学習](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)します。</span><span class="sxs-lookup"><span data-stu-id="a1d66-105">Before reading this guide, you should be familiar with [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] development, BizTalk Server, and [Learn the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a1d66-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a1d66-106">In This Section</span></span>  
  
-   [<span data-ttu-id="a1d66-107">HL7 メッセージの処理</span><span class="sxs-lookup"><span data-stu-id="a1d66-107">Processing HL7 Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)  
  
-   [<span data-ttu-id="a1d66-108">HL7 2.X スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="a1d66-108">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)  
  
-   [<span data-ttu-id="a1d66-109">HL7 2. XML スキーマの使用</span><span class="sxs-lookup"><span data-stu-id="a1d66-109">Using HL7 2.XML Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)  
  
-   [<span data-ttu-id="a1d66-110">MLLP でエンコードされたメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="a1d66-110">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)  
  
-   [<span data-ttu-id="a1d66-111">受信確認の作成と処理</span><span class="sxs-lookup"><span data-stu-id="a1d66-111">Creating and Processing Acknowledgments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)  
  
-   [<span data-ttu-id="a1d66-112">動的データ検証の使用</span><span class="sxs-lookup"><span data-stu-id="a1d66-112">Using Dynamic Data Validation</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-dynamic-data-validation.md)  
  
-   [<span data-ttu-id="a1d66-113">監査およびログ イベント用の WMI シンクの作成</span><span class="sxs-lookup"><span data-stu-id="a1d66-113">Creating a WMI Sink for Auditing and Logging Events</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-a-wmi-sink-for-auditing-and-logging-events.md)  
  
-   [<span data-ttu-id="a1d66-114">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="a1d66-114">Additional Resources</span></span>](../../adapters-and-accelerators/accelerator-hl7/additional-resources.md)