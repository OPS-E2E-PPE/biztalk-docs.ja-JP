---
title: EDI メッセージの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ee189ccd827c72fd177d65eaa49461e2287538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350360"
---
# <a name="edi-message-validation"></a><span data-ttu-id="ec06f-102">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-102">EDI Message Validation</span></span>
<span data-ttu-id="ec06f-103">EDI データは自己記述型タグ) (なし、区切られたファイルとして送信し、エンコードの規則がコピー先のアプリケーションが正常に解析およびダウン ストリーム処理の情報を利用することであることを確認する厳密な書式規則を適用するためです。</span><span class="sxs-lookup"><span data-stu-id="ec06f-103">EDI data is transmitted as delimited files (without self describing tags) and therefore the encoding rules enforce strict formatting rules to ensure the destination application is able to successfully parse and consume the information for downstream processing.</span></span>  
  
 <span data-ttu-id="ec06f-104">EDI 受信パイプラインと EDI 送信パイプライン Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 は、一連の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec06f-104">The EDI receive pipeline and EDI send pipeline in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 perform a series of validations.</span></span> <span data-ttu-id="ec06f-105">いくつかは常に実行します。他のユーザーは、アグリーメントでプロパティを有効にした場合、または、スキーマ内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="ec06f-105">Some are always performed; others are performed if enabled in agreement properties or in the schema.</span></span> <span data-ttu-id="ec06f-106">検証を構成する方法の詳細については、次を参照してください。 [、EDI インターチェンジが構成されているの検証方法](../core/how-validation-of-an-edi-interchange-is-configured.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec06f-106">For more information about how validation is configured, see [How Validation of an EDI Interchange Is Configured](../core/how-validation-of-an-edi-interchange-is-configured.md).</span></span>  
  
 <span data-ttu-id="ec06f-107">EDI インターチェンジの検証には、次のトピックで説明したようにいくつかの異なる種類検証にはが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec06f-107">Validation of an EDI interchange involves several different kinds of validation, as described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec06f-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ec06f-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ec06f-109">EDI インターチェンジの検証を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ec06f-109">How Validation of an EDI Interchange Is Configured</span></span>](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [<span data-ttu-id="ec06f-110">EDI 構造の検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-110">EDI Structural Validation</span></span>](../core/edi-structural-validation.md)  
  
-   [<span data-ttu-id="ec06f-111">アグリーメントのプロパティの検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-111">Agreement Properties Validation</span></span>](../core/agreement-properties-validation.md)  
  
-   [<span data-ttu-id="ec06f-112">EDI の種類 (データ要素) の検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-112">EDI Type (Data Element) Validation</span></span>](../core/edi-type-data-element-validation.md)  
  
-   [<span data-ttu-id="ec06f-113">拡張された (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-113">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)  
  
-   [<span data-ttu-id="ec06f-114">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-114">Schema Validation</span></span>](../core/schema-validation2.md)  
  
-   [<span data-ttu-id="ec06f-115">クロスフィールド/セグメント検証</span><span class="sxs-lookup"><span data-stu-id="ec06f-115">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)