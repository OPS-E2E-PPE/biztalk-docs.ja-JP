---
title: ボキャブラリ |Microsoft Docs
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
ms.openlocfilehash: 18e513687db2b291462843811d296c15d3509288
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320851"
---
# <a name="vocabularies"></a><span data-ttu-id="d38ab-102">ボキャブラリ</span><span class="sxs-lookup"><span data-stu-id="d38ab-102">Vocabularies</span></span>
<span data-ttu-id="d38ab-103">ルール条件およびアクションの定義に使用される用語は通常、ドメインまたは業界固有の命名規則によって表されます。</span><span class="sxs-lookup"><span data-stu-id="d38ab-103">The terms used to define rule conditions and actions are usually expressed by domain or industry-specific nomenclature.</span></span> <span data-ttu-id="d38ab-104">たとえば、電子メール ユーザーに書き込むメッセージとしてルール「から受信した」メッセージ"間、送受信した後、"保険のビジネス アナリストが「危険要素」および「補償範囲額」としてルールを記述</span><span class="sxs-lookup"><span data-stu-id="d38ab-104">For example, an e-mail user writes rules in terms of messages "received from" and messages "received after," while an insurance business analyst writes rules in terms of "risk factors" and "coverage amount."</span></span>  
  
 <span data-ttu-id="d38ab-105">このドメインに固有の用語を基になると、ルールの条件とルールのアクションを実装するテクノロジ アイテム (オブジェクト、データベース テーブル、および XML ドキュメント)。</span><span class="sxs-lookup"><span data-stu-id="d38ab-105">Underlying this domain-specific terminology are the technology artifacts (objects, database tables, and XML documents) that implement rule conditions and rule actions.</span></span> <span data-ttu-id="d38ab-106">Vocabulariesare では、ビジネス セマンティクスと実装の間のギャップを埋めるために設計されています。</span><span class="sxs-lookup"><span data-stu-id="d38ab-106">Vocabulariesare designed to bridge the gap between business semantics and implementation.</span></span>  
  
 <span data-ttu-id="d38ab-107">たとえば、承認状態のデータ バインディングは可能性がありますに特定のデータベース、SQL クエリとして表される特定の行で特定の列をポイントします。</span><span class="sxs-lookup"><span data-stu-id="d38ab-107">For example, a data binding for an approval status might point to a certain column in a certain row in a certain database, represented as an SQL query.</span></span> <span data-ttu-id="d38ab-108">ルールでこのような複雑な表現を挿入する代わりに、「状態です」のフレンドリ名をデータ バインドに関連付けられている、ボキャブラリの定義を作成する場合があります代わりに</span><span class="sxs-lookup"><span data-stu-id="d38ab-108">Instead of inserting this sort of complex representation in a rule, you might instead create a vocabulary definition, associated with that data binding, with a friendly name of "Status."</span></span> <span data-ttu-id="d38ab-109">その後、ルールの任意の数の"Status"を含めることができ、ルール エンジンは、テーブルから、対応するデータを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="d38ab-109">Subsequently you can include "Status" in any number of rules, and the rule engine can retrieve the corresponding data from the table.</span></span>  
  
 <span data-ttu-id="d38ab-110">A*ボキャブラリ*ルール条件およびアクションで使用されるファクトのフレンドリ名で構成される定義のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d38ab-110">A *vocabulary* is a collection of definitions consisting of friendly names for the facts used in rule conditions and actions.</span></span> <span data-ttu-id="d38ab-111">ボキャブラリの定義するルール読み、理解、および特定のビジネス ドメイン内のユーザーで共有できます。</span><span class="sxs-lookup"><span data-stu-id="d38ab-111">Vocabulary definitions make the rules easier to read, understand, and share by people in a particular business domain.</span></span>  
  
 <span data-ttu-id="d38ab-112">ビジネス ルール作成ツールを使用して、共有ルール ストアに配置し、ボキャブラリを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="d38ab-112">You can use the Business Rule Composer to define vocabularies that are then placed in the shared rule store.</span></span> <span data-ttu-id="d38ab-113">ボキャブラリは、ルールの作成を新規または既存のアプリケーションに統合するツールの開発者でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d38ab-113">Vocabularies can also be consumed by tool developers responsible for integrating rule authoring into new or existing applications.</span></span>  
  
 <span data-ttu-id="d38ab-114">ボキャブラリを使用する前にバージョンを設定およびルール ストアに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d38ab-114">Before you can use a vocabulary, it must be stamped with a version and published in your rule store.</span></span> <span data-ttu-id="d38ab-115">これは、ボキャブラリの定義が変更されないことを保証するためにし、参照整合性を維持します。</span><span class="sxs-lookup"><span data-stu-id="d38ab-115">This is to guarantee that the definitions in the vocabulary will not change, and to preserve referential integrity.</span></span> <span data-ttu-id="d38ab-116">これは、ボキャブラリの特定のバージョンを使用するポリシーが、基になるボキャブラリ変更により、予期しない失敗ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d38ab-116">This means that any policies that use that particular version of the vocabulary will not fail unexpectedly due to changes in the underlying vocabulary.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d38ab-117">参照</span><span class="sxs-lookup"><span data-stu-id="d38ab-117">See Also</span></span>  
 [<span data-ttu-id="d38ab-118">ビジネス ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="d38ab-118">Business Rules Engine</span></span>](../core/business-rules-engine.md)