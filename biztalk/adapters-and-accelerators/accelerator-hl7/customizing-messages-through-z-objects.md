---
title: "Z オブジェクト経由でメッセージをカスタマイズする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, Z objects
- customizing, messages
- Z objects, customizing messages
- customizing, Z objects
- messages, customizing
ms.assetid: 5bf514f8-d270-42d9-80fa-f10a6f6a20ad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e01e5f106c690d506364dd2040702cdad0c3adcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-messages-through-z-objects"></a><span data-ttu-id="3f039-102">Z オブジェクト経由でメッセージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="3f039-102">Customizing Messages through Z Objects</span></span>
<span data-ttu-id="3f039-103">ことが重要、HL7 可能性があります、包括的では対処できませんインターフェイス パートナーの各セットの特定の要件をすべて認識します。</span><span class="sxs-lookup"><span data-stu-id="3f039-103">It is important to recognize that, as comprehensive as HL7 may be, it does not address all the particular requirements of every set of interface partners.</span></span> <span data-ttu-id="3f039-104">これで、アプリケーションの特定のデータ要件を超えてデータ HL7 を提供する定義時間になります。</span><span class="sxs-lookup"><span data-stu-id="3f039-104">There will be times in which the specific data requirements of an application go beyond the data definitions that HL7 provides.</span></span> <span data-ttu-id="3f039-105">HL7 がインターフェイスの開発者が、データは、標準を超える必要があるときに使用できるメソッドを提供しています。</span><span class="sxs-lookup"><span data-stu-id="3f039-105">HL7 has provided methods that interface developers can use when their data needs go beyond the standard.</span></span> <span data-ttu-id="3f039-106">残念ながらも、時間で HL7 インターフェイスの実装は完全には、標準の内容は、いずれかの誤用の既存のコンテンツを持ちまたは単に新しいマテリアルを既存のセグメントに追加します。</span><span class="sxs-lookup"><span data-stu-id="3f039-106">Unfortunately, there are also times in which the implementers of HL7 interfaces do not fully grasp the contents of the standard, and either misuse pre-existing content or simply add new material to existing segments.</span></span>  
  
 <span data-ttu-id="3f039-107">HL7 標準オブジェクトを呼び出すサポートされているカスタマイズ (またはローカライズ)"Z"、その名前が、文字"Z"で始まるためです。</span><span class="sxs-lookup"><span data-stu-id="3f039-107">HL7 standards call the supported customization (or localizations) "Z objects", because their names begin with the letter "Z".</span></span> <span data-ttu-id="3f039-108">HL7 メッセージで 2 種類のカスタマイズを行うことができます: 宣言と宣言されていません。</span><span class="sxs-lookup"><span data-stu-id="3f039-108">You can perform two types of customizations on HL7 messages: declared and undeclared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3f039-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3f039-109">In This Section</span></span>  
  
-   [<span data-ttu-id="3f039-110">宣言のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3f039-110">Declared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)  
  
-   [<span data-ttu-id="3f039-111">宣言されていないカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="3f039-111">Undeclared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)