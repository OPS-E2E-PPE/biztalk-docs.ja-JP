---
title: Contoso LOB スキーマとマップの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: 45f9fd544b690031a14a53b829e5647890bf8e67
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004339"
---
# <a name="creating-the-contoso-lob-schemas-and-maps"></a><span data-ttu-id="bea7a-102">Contoso LOB スキーマとマップの作成</span><span class="sxs-lookup"><span data-stu-id="bea7a-102">Creating the Contoso LOB Schemas and Maps</span></span>
<span data-ttu-id="bea7a-103">ここでは、Contoso 組織が ERP システムで使用する基幹業務 (LOB) スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-103">In this section, you create the line-of-business (LOB) schemas that the Contoso organization uses in their ERP system.</span></span> <span data-ttu-id="bea7a-104">使用する、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server マッパー ツールを Contoso の内部メッセージおよび受信と送信の RosettaNet メッセージの種類間のデータ変換を作成します。</span><span class="sxs-lookup"><span data-stu-id="bea7a-104">You use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server Mapper tool to create data transformations between the internal Contoso messages and the inbound and outbound RosettaNet message types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bea7a-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bea7a-105">In This Section</span></span>  
  
-   [<span data-ttu-id="bea7a-106">手順 1: Contoso Price and Availability Request のための新しい BizTalk ソリューションの作成</span><span class="sxs-lookup"><span data-stu-id="bea7a-106">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)  
  
-   [<span data-ttu-id="bea7a-107">手順 2: BizTalk エディターを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション スキーマの作成</span><span class="sxs-lookup"><span data-stu-id="bea7a-107">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)  
  
-   [<span data-ttu-id="bea7a-108">手順 3: BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成</span><span class="sxs-lookup"><span data-stu-id="bea7a-108">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)