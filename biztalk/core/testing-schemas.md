---
title: スキーマのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8331026992e9715793cf366409cb68904e5058c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298969"
---
# <a name="testing-schemas"></a><span data-ttu-id="cc80f-102">スキーマのテスト</span><span class="sxs-lookup"><span data-stu-id="cc80f-102">Testing Schemas</span></span>
<span data-ttu-id="cc80f-103">スキーマを作成すると、意図を記述する XML 構造が説明されているかを検証したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc80f-103">After you have created your schema, you may want to validate that it describes the XML structure you intend it to describe.</span></span> <span data-ttu-id="cc80f-104">検証するのには、スキーマに次の 3 つの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cc80f-104">You can perform the following three operations on your schema to validate it:</span></span>  
  
- <span data-ttu-id="cc80f-105">**インスタンス生成**します。</span><span class="sxs-lookup"><span data-stu-id="cc80f-105">**Instance generation**.</span></span> <span data-ttu-id="cc80f-106">この操作は、XML 要素と、スキーマで指定された属性に付随するテスト データの作成、スキーマからインスタンス メッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="cc80f-106">This operation generates an instance message from a schema, creating test data to accompany the XML elements and attributes specified by the schema.</span></span>  
  
- <span data-ttu-id="cc80f-107">**スキーマ検証**です。</span><span class="sxs-lookup"><span data-stu-id="cc80f-107">**Schema validation**.</span></span> <span data-ttu-id="cc80f-108">この操作は、XML スキーマ定義 (XSD) 言語スキーマの標準に準拠しているスキーマの内部の一貫性を検証します。</span><span class="sxs-lookup"><span data-stu-id="cc80f-108">This operation validates the internal consistency of a schema, assuring that it conforms to the XML Schema definition (XSD) language schema standard.</span></span>  
  
- <span data-ttu-id="cc80f-109">**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="cc80f-109">**Instance validation**.</span></span> <span data-ttu-id="cc80f-110">この操作は、スキーマに対する特定のインスタンス メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="cc80f-110">This operation validates a given instance message against a schema.</span></span>  
  
  <span data-ttu-id="cc80f-111">これらの操作の 3 つすべては運用環境で使用して配置する前に、スキーマのテストに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cc80f-111">All three of these operations are useful for testing your schemas before putting them into use in a production environment.</span></span>  
  
  <span data-ttu-id="cc80f-112">このセクションでは、これらの操作をさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="cc80f-112">This section describes these operations in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc80f-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cc80f-113">In This Section</span></span>  
  
-   [<span data-ttu-id="cc80f-114">Visual Studio でのスキーマを検証する方法</span><span class="sxs-lookup"><span data-stu-id="cc80f-114">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [<span data-ttu-id="cc80f-115">インスタンス メッセージを検証する方法</span><span class="sxs-lookup"><span data-stu-id="cc80f-115">How to Validate Instance Messages</span></span>](../core/how-to-validate-instance-messages.md)  
  
-   [<span data-ttu-id="cc80f-116">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="cc80f-116">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)