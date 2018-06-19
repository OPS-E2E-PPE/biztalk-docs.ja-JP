---
title: EDI メッセージの検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238826"
---
# <a name="edi-message-validation"></a><span data-ttu-id="3b156-102">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="3b156-102">EDI Message Validation</span></span>
<span data-ttu-id="3b156-103">EDI データは、自己記述型タグを持たない区切られたファイルとして送信されます。そのため、エンコーディング規則は厳密な書式規則を適用して、送信先アプリケーションが下流の処理で情報を正常に解析および利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b156-103">EDI data is transmitted as delimited files (without self describing tags) and therefore the encoding rules enforce strict formatting rules to ensure the destination application is able to successfully parse and consume the information for downstream processing.</span></span>  
  
 <span data-ttu-id="3b156-104">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 の EDI 受信パイプラインと EDI 送信パイプラインは、一連の検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="3b156-104">The EDI receive pipeline and EDI send pipeline in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 perform a series of validations.</span></span> <span data-ttu-id="3b156-105">これらの検証には、常に実行されるものと、アグリーメント プロパティまたはスキーマで有効にされた場合に実行されるものとがあります。</span><span class="sxs-lookup"><span data-stu-id="3b156-105">Some are always performed; others are performed if enabled in agreement properties or in the schema.</span></span> <span data-ttu-id="3b156-106">検証を構成する方法の詳細については、次を参照してください。 [、EDI インターチェンジが構成されているの検証方法](../core/how-validation-of-an-edi-interchange-is-configured.md)です。</span><span class="sxs-lookup"><span data-stu-id="3b156-106">For more information about how validation is configured, see [How Validation of an EDI Interchange Is Configured](../core/how-validation-of-an-edi-interchange-is-configured.md).</span></span>  
  
 <span data-ttu-id="3b156-107">EDI インターチェンジの検証には、以下のトピックで説明するように、さまざまな種類の検証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b156-107">Validation of an EDI interchange involves several different kinds of validation, as described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b156-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3b156-108">In This Section</span></span>  
  
-   [<span data-ttu-id="3b156-109">EDI インターチェンジの検証を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3b156-109">How Validation of an EDI Interchange Is Configured</span></span>](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [<span data-ttu-id="3b156-110">EDI 構造検証</span><span class="sxs-lookup"><span data-stu-id="3b156-110">EDI Structural Validation</span></span>](../core/edi-structural-validation.md)  
  
-   [<span data-ttu-id="3b156-111">アグリーメントのプロパティの検証</span><span class="sxs-lookup"><span data-stu-id="3b156-111">Agreement Properties Validation</span></span>](../core/agreement-properties-validation.md)  
  
-   [<span data-ttu-id="3b156-112">EDI の種類 (データ要素) の検証</span><span class="sxs-lookup"><span data-stu-id="3b156-112">EDI Type (Data Element) Validation</span></span>](../core/edi-type-data-element-validation.md)  
  
-   [<span data-ttu-id="3b156-113">拡張 (BTS-XSD) 検証</span><span class="sxs-lookup"><span data-stu-id="3b156-113">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)  
  
-   [<span data-ttu-id="3b156-114">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="3b156-114">Schema Validation</span></span>](../core/schema-validation2.md)  
  
-   [<span data-ttu-id="3b156-115">クロス フィールド セグメント検証</span><span class="sxs-lookup"><span data-stu-id="3b156-115">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)