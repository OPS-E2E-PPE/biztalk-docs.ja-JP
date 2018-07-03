---
title: ファクト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, facts
- facts, about facts
- Business Rule Composer, facts
- business rules, facts
- facts
ms.assetid: 8f8086e4-fa16-49e8-8191-3d397330937f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bddfeb22484358f68d93f279a42a69c67812ec17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017621"
---
# <a name="facts"></a><span data-ttu-id="a4f25-102">ファクト</span><span class="sxs-lookup"><span data-stu-id="a4f25-102">Facts</span></span>
<span data-ttu-id="a4f25-103">ファクトとは、実世界に関する個々の情報です。</span><span class="sxs-lookup"><span data-stu-id="a4f25-103">Facts are discrete pieces of information about the world.</span></span> <span data-ttu-id="a4f25-104">ファクトは多くのソース (イベント システム、ビジネス アプリケーションやデータベース テーブル内のオブジェクト) から取得できのビジネス ルール エンジンに渡す必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]次の要素のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4f25-104">Facts can originate from many sources (event systems, objects in business applications, database tables, and so on), and must be fed into the Business Rule engine in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using one of the following elements:</span></span>  
  
- <span data-ttu-id="a4f25-105">.NET オブジェクト (メソッド、プロパティ、およびフィールド)</span><span class="sxs-lookup"><span data-stu-id="a4f25-105">.NET objects (methods, properties, and fields)</span></span>  
  
- <span data-ttu-id="a4f25-106">XML ドキュメント (要素、属性、およびドキュメントのサブセクション)</span><span class="sxs-lookup"><span data-stu-id="a4f25-106">XML documents (elements, attributes, and document subsections)</span></span>  
  
- <span data-ttu-id="a4f25-107">データベース行セット (テーブル列の値)</span><span class="sxs-lookup"><span data-stu-id="a4f25-107">Database rowsets (values from table column)</span></span>  
  
  <span data-ttu-id="a4f25-108">ビジネス ルール作成ツールでは、ファクト エクスプローラーを使用して、さまざまなソースのデータを参照し、ルールに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a4f25-108">In the Business Rule Composer, you can use the Facts Explorer to browse and bring data into your rules from various sources.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a4f25-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a4f25-109">In This Section</span></span>  
  
-   [<span data-ttu-id="a4f25-110">.NET オブジェクトのファクト</span><span class="sxs-lookup"><span data-stu-id="a4f25-110">.NET Object Facts</span></span>](../core/net-object-facts.md)  
  
-   [<span data-ttu-id="a4f25-111">型指定されたファクト</span><span class="sxs-lookup"><span data-stu-id="a4f25-111">Typed Facts</span></span>](../core/typed-facts.md)  
  
-   [<span data-ttu-id="a4f25-112">短期間のファクトと長期間のファクト</span><span class="sxs-lookup"><span data-stu-id="a4f25-112">Short-Term Facts vs. Long-Term Facts</span></span>](../core/short-term-facts-vs-long-term-facts.md)  
  
## <a name="see-also"></a><span data-ttu-id="a4f25-113">参照</span><span class="sxs-lookup"><span data-stu-id="a4f25-113">See Also</span></span>  
 [<span data-ttu-id="a4f25-114">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="a4f25-114">Business Rules Engine</span></span>](../core/business-rules-engine.md)