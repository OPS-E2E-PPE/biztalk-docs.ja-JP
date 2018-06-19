---
title: ボキャブラリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, vocabularies
- vocabularies, about vocabularies
- vocabularies
- Business Rules Engine, vocabularies
ms.assetid: 591673a0-2c4d-41ca-9997-b363c086dd66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9e20dfead51d54822d3316c8819d04a259cfa83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288010"
---
# <a name="vocabularies"></a><span data-ttu-id="73fe0-102">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="73fe0-102">Vocabularies</span></span>
<span data-ttu-id="73fe0-103">ルールの条件やアクションを定義するために使用される用語は、通常、分野固有または業界固有の用語体系に従って表現されます。</span><span class="sxs-lookup"><span data-stu-id="73fe0-103">The terms used to define rule conditions and actions are usually expressed by domain or industry-specific nomenclature.</span></span> <span data-ttu-id="73fe0-104">たとえば、電子メールを使用するユーザーが "差出人" や "特定日時以降に受信" したメッセージとしてルールを記述したり、保険のビジネス アナリストが "危険要素" および "補償範囲額" としてルールを記述したりします。</span><span class="sxs-lookup"><span data-stu-id="73fe0-104">For example, an e-mail user writes rules in terms of messages "received from" and messages "received after," while an insurance business analyst writes rules in terms of "risk factors" and "coverage amount."</span></span>  
  
 <span data-ttu-id="73fe0-105">この分野固有の用語の背景には、ルールの条件やルールのアクションを実装するテクノロジ アイテム (オブジェクト、データベース テーブル、および XML ドキュメント) が存在します。</span><span class="sxs-lookup"><span data-stu-id="73fe0-105">Underlying this domain-specific terminology are the technology artifacts (objects, database tables, and XML documents) that implement rule conditions and rule actions.</span></span> <span data-ttu-id="73fe0-106">Vocabulariesare では、ビジネス セマンティクスと実装の間のギャップを埋めるために設計されています。</span><span class="sxs-lookup"><span data-stu-id="73fe0-106">Vocabulariesare designed to bridge the gap between business semantics and implementation.</span></span>  
  
 <span data-ttu-id="73fe0-107">たとえば、承認状態のデータ バインドは、SQL クエリとして表される特定のデータベースの特定の行の単一の列を示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="73fe0-107">For example, a data binding for an approval status might point to a certain column in a certain row in a certain database, represented as an SQL query.</span></span> <span data-ttu-id="73fe0-108">ルールに直接このような複雑な表現を挿入する代わりに、たとえば、データ バインドに関連付けるボキャブラリ定義をフレンドリ名 "Status" で作成します。</span><span class="sxs-lookup"><span data-stu-id="73fe0-108">Instead of inserting this sort of complex representation in a rule, you might instead create a vocabulary definition, associated with that data binding, with a friendly name of "Status."</span></span> <span data-ttu-id="73fe0-109">後で任意の数のルールに "Status" を含めることができるので、ルール エンジンは、テーブルから対応するデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="73fe0-109">Subsequently you can include "Status" in any number of rules, and the rule engine can retrieve the corresponding data from the table.</span></span>  
  
 <span data-ttu-id="73fe0-110">A*ボキャブラリ*ルール条件およびアクションで使用されるファクトのフレンドリ名で構成される定義のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="73fe0-110">A *vocabulary* is a collection of definitions consisting of friendly names for the facts used in rule conditions and actions.</span></span> <span data-ttu-id="73fe0-111">ボキャブラリを定義すると、特定のビジネス分野のユーザーによるルールの参照、理解、および共有が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="73fe0-111">Vocabulary definitions make the rules easier to read, understand, and share by people in a particular business domain.</span></span>  
  
 <span data-ttu-id="73fe0-112">ビジネス ルール作成ツールを使用して、共有されているルール ストアに置くボキャブラリを定義できます。</span><span class="sxs-lookup"><span data-stu-id="73fe0-112">You can use the Business Rule Composer to define vocabularies that are then placed in the shared rule store.</span></span> <span data-ttu-id="73fe0-113">ルール作成を新しいアプリケーション (または既存のアプリケーション) に統合するツールの開発者も、ボキャブラリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="73fe0-113">Vocabularies can also be consumed by tool developers responsible for integrating rule authoring into new or existing applications.</span></span>  
  
 <span data-ttu-id="73fe0-114">ボキャブラリを使用する前に、ボキャブラリにバージョンを設定し、使用しているルール ストアにボキャブラリを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73fe0-114">Before you can use a vocabulary, it must be stamped with a version and published in your rule store.</span></span> <span data-ttu-id="73fe0-115">これにより、ボキャブラリの定義は変更されずに参照整合性が確保されます。</span><span class="sxs-lookup"><span data-stu-id="73fe0-115">This is to guarantee that the definitions in the vocabulary will not change, and to preserve referential integrity.</span></span> <span data-ttu-id="73fe0-116">つまり、基になるボキャブラリが変更されても、ボキャブラリの特定のバージョンを使用するポリシーで予期しないエラーが発生することがありません。</span><span class="sxs-lookup"><span data-stu-id="73fe0-116">This means that any policies that use that particular version of the vocabulary will not fail unexpectedly due to changes in the underlying vocabulary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73fe0-117">参照</span><span class="sxs-lookup"><span data-stu-id="73fe0-117">See Also</span></span>  
 [<span data-ttu-id="73fe0-118">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="73fe0-118">Business Rules Engine</span></span>](../core/business-rules-engine.md)