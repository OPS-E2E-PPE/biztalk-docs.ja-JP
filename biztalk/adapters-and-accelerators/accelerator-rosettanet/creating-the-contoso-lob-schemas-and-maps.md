---
title: Contoso LOB スキーマとマップの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, LOB
- LOBs, schemas
- private process tutorial, creating LOB schemas
- private process tutorial, creating maps
- maps
ms.assetid: fda8852a-51d8-4987-a187-834883a06d9b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc6cc5ae016a06e010ab1cf2fa6391cccfd4c4bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284205"
---
# <a name="creating-the-contoso-lob-schemas-and-maps"></a><span data-ttu-id="fc8ea-102">Contoso LOB スキーマとマップの作成</span><span class="sxs-lookup"><span data-stu-id="fc8ea-102">Creating the Contoso LOB Schemas and Maps</span></span>
<span data-ttu-id="fc8ea-103">このセクションでは、Contoso 組織が ERP システムで使用する基幹業務 (LOB) スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="fc8ea-103">In this section, you create the line-of-business (LOB) schemas that the Contoso organization uses in their ERP system.</span></span> <span data-ttu-id="fc8ea-104">Contoso の内部メッセージと受信と送信の RosettaNet メッセージの種類の間のデータ変換を作成するのにには、Microsoft® BizTalk Server マッパー ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc8ea-104">You use the Microsoft® BizTalk Server Mapper tool to create data transformations between the internal Contoso messages and the inbound and outbound RosettaNet message types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc8ea-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fc8ea-105">In This Section</span></span>  
  
-   [<span data-ttu-id="fc8ea-106">ステップ 1: Contoso Price and Availability Request のための新しい BizTalk ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="fc8ea-106">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)  
  
-   [<span data-ttu-id="fc8ea-107">手順 2:BizTalk エディターを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="fc8ea-107">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)  
  
-   [<span data-ttu-id="fc8ea-108">ステップ 3:BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成</span><span class="sxs-lookup"><span data-stu-id="fc8ea-108">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)