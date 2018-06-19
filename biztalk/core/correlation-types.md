---
title: 関連付けの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, correlation types
- correlation types, correlation sets
- correlation types
- validating, correlation types
- correlation types, about correlation types
- correlation types, validating
ms.assetid: 1aa5ca5c-c37d-4091-9f5d-331a6b202d4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3da5fad8cb4edc1d6a528f481616b4f10efb71d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237778"
---
# <a name="correlation-types"></a><span data-ttu-id="4b730-102">関連付けの種類</span><span class="sxs-lookup"><span data-stu-id="4b730-102">Correlation Types</span></span>
<span data-ttu-id="4b730-103">各関連付けセットがに基づいて、**関連付けの種類**、これは単にプロパティの一覧です。</span><span class="sxs-lookup"><span data-stu-id="4b730-103">Each correlation set is based on a **correlation type**, which is simply a list of properties.</span></span> <span data-ttu-id="4b730-104">これらのプロパティは、メッセージ自体の中に存在するデータ プロパティ、またはメッセージ内で伝えられているデータに関連しないシステムまたはメッセージの詳細を説明するコンテキスト プロパティである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b730-104">These properties might be data properties, which are found in the message itself, or context properties, which describe details of the system or messages that are unrelated to the data being conveyed in the message.</span></span>  
  
 <span data-ttu-id="4b730-105">複数の関連付けセットで、1 つの関連付けの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b730-105">You can use a correlation type in more than one correlation set.</span></span> <span data-ttu-id="4b730-106">関連付けの種類のプロパティに別の値に関連付ける必要がある場合は、新しい関連付けセットを作成する必要があります: 各関連付けセットを 1 回だけ初期化できます。</span><span class="sxs-lookup"><span data-stu-id="4b730-106">If you need to correlate on different values for the properties in a correlation type, you must create a new correlation set—each correlation set can be initialized only once.</span></span>  
  
 <span data-ttu-id="4b730-107">プロパティ スキーマ内のプロパティを昇格して、メッセージ内の特定のプロパティがオーケストレーションからアクセスできることを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="4b730-107">You can promote properties in a property schema to declare that certain properties in a message are accessible to your orchestration.</span></span> <span data-ttu-id="4b730-108">詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b730-108">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4b730-109">システム定義プロパティを設定しない**BTS です。CorrelationToken**各メッセージに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="4b730-109">Do not set the system-defined property **BTS.CorrelationToken** that is associated with each message.</span></span> <span data-ttu-id="4b730-110">これはメッセージの関連付けの際にエンジンによって使用され、これを設定することによって、オーケストレーションのメッセージが失われる結果になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4b730-110">This is used by the engine in correlating messages, and setting it could result in your orchestration losing messages.</span></span>  
  
## <a name="validating-message-correlation-on-send-actions"></a><span data-ttu-id="4b730-111">送信アクションに対するメッセージの関連付けの検証</span><span class="sxs-lookup"><span data-stu-id="4b730-111">Validating Message Correlation on Send Actions</span></span>  
 <span data-ttu-id="4b730-112">オーケストレーションがその関連付けセット内のプロパティを確実に反映するように、オーケストレーションから送信するメッセージ プロパティを検証できます。</span><span class="sxs-lookup"><span data-stu-id="4b730-112">You can validate the properties of a message that you send from your orchestration to ensure that it reflects the properties in its correlation set.</span></span> <span data-ttu-id="4b730-113">既定では、この検証は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="4b730-113">By default, this validation is disabled.</span></span> <span data-ttu-id="4b730-114">これを有効にする方法については、次を参照してください。 [、オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b730-114">For information on how to enable it, see [Runtime Validation for the Orchestration Engine](../core/runtime-validation-for-the-orchestration-engine.md).</span></span>