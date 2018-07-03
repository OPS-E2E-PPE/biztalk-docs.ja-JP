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
ms.openlocfilehash: fc036be84bb64e794e6109e1ebc4ec730f382878
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023112"
---
# <a name="testing-schemas"></a><span data-ttu-id="70afa-102">スキーマのテスト</span><span class="sxs-lookup"><span data-stu-id="70afa-102">Testing Schemas</span></span>
<span data-ttu-id="70afa-103">スキーマを作成した後、XML 構造が正しいかどうかを検証したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="70afa-103">After you have created your schema, you may want to validate that it describes the XML structure you intend it to describe.</span></span> <span data-ttu-id="70afa-104">スキーマに対して次の 3 つの操作を実行して、検証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="70afa-104">You can perform the following three operations on your schema to validate it:</span></span>  
  
- <span data-ttu-id="70afa-105">**インスタンス生成**します。</span><span class="sxs-lookup"><span data-stu-id="70afa-105">**Instance generation**.</span></span> <span data-ttu-id="70afa-106">この結果、スキーマで指定された XML 要素および XML 属性と共にテスト データが作成されます。</span><span class="sxs-lookup"><span data-stu-id="70afa-106">This operation generates an instance message from a schema, creating test data to accompany the XML elements and attributes specified by the schema.</span></span>  
  
- <span data-ttu-id="70afa-107">**スキーマ検証**です。</span><span class="sxs-lookup"><span data-stu-id="70afa-107">**Schema validation**.</span></span> <span data-ttu-id="70afa-108">標準の XSD (XML Schema Definition) 言語のスキーマに準拠しているかどうかが検証されます。</span><span class="sxs-lookup"><span data-stu-id="70afa-108">This operation validates the internal consistency of a schema, assuring that it conforms to the XML Schema definition (XSD) language schema standard.</span></span>  
  
- <span data-ttu-id="70afa-109">**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="70afa-109">**Instance validation**.</span></span> <span data-ttu-id="70afa-110">この操作は、スキーマに対する特定のインスタンス メッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="70afa-110">This operation validates a given instance message against a schema.</span></span>  
  
  <span data-ttu-id="70afa-111">これらの 3 つの操作は、実稼働環境で運用する前にスキーマをテストする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="70afa-111">All three of these operations are useful for testing your schemas before putting them into use in a production environment.</span></span>  
  
  <span data-ttu-id="70afa-112">このセクションでは、これらの操作の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="70afa-112">This section describes these operations in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="70afa-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="70afa-113">In This Section</span></span>  
  
-   [<span data-ttu-id="70afa-114">Visual Studio でのスキーマを検証する方法</span><span class="sxs-lookup"><span data-stu-id="70afa-114">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [<span data-ttu-id="70afa-115">インスタンス メッセージを検証する方法</span><span class="sxs-lookup"><span data-stu-id="70afa-115">How to Validate Instance Messages</span></span>](../core/how-to-validate-instance-messages.md)  
  
-   [<span data-ttu-id="70afa-116">インスタンス メッセージを生成する方法</span><span class="sxs-lookup"><span data-stu-id="70afa-116">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)