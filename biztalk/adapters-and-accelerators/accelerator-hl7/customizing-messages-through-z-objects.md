---
title: Z オブジェクト経由でメッセージをカスタマイズする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Z objects
- customizing, messages
- Z objects, customizing messages
- customizing, Z objects
- messages, customizing
ms.assetid: 5bf514f8-d270-42d9-80fa-f10a6f6a20ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab08d367e28fdde77e19bccd777d27ceb5e0315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255544"
---
# <a name="customizing-messages-through-z-objects"></a><span data-ttu-id="4bb6e-102">Z オブジェクト経由でメッセージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-102">Customizing Messages through Z Objects</span></span>
<span data-ttu-id="4bb6e-103">認識、HL7 可能性があります、包括的では対応していませんインターフェイス パートナーのセットごとの特定の要件をすべてに重要です。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-103">It is important to recognize that, as comprehensive as HL7 may be, it does not address all the particular requirements of every set of interface partners.</span></span> <span data-ttu-id="4bb6e-104">時間をアプリケーションの特定のデータ要件を超えるデータ HL7 を提供する定義があります。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-104">There will be times in which the specific data requirements of an application go beyond the data definitions that HL7 provides.</span></span> <span data-ttu-id="4bb6e-105">HL7 は、インターフェイスの開発者は、データは、標準を超えるニーズがあるときに使用できる方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-105">HL7 has provided methods that interface developers can use when their data needs go beyond the standard.</span></span> <span data-ttu-id="4bb6e-106">残念ながら、時間を HL7 インターフェイスの実装は完全には、標準の内容は、いずれかの誤用の既存のコンテンツを持ちまたは単に既存のセグメントに新しい資料が追加されても。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-106">Unfortunately, there are also times in which the implementers of HL7 interfaces do not fully grasp the contents of the standard, and either misuse pre-existing content or simply add new material to existing segments.</span></span>  
  
 <span data-ttu-id="4bb6e-107">HL7 標準オブジェクトを呼び出すサポートされているカスタマイズ (またはローカライズ)"Z"、"Z"文字で、名前が始まるためです。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-107">HL7 standards call the supported customization (or localizations) "Z objects", because their names begin with the letter "Z".</span></span> <span data-ttu-id="4bb6e-108">HL7 メッセージの 2 種類のカスタマイズを行うことができます: 宣言と宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="4bb6e-108">You can perform two types of customizations on HL7 messages: declared and undeclared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bb6e-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4bb6e-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4bb6e-110">宣言済みのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4bb6e-110">Declared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)  
  
-   [<span data-ttu-id="4bb6e-111">未宣言のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4bb6e-111">Undeclared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)