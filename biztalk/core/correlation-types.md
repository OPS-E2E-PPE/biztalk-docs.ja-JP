---
title: 関連付けの種類 |Microsoft Docs
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
ms.openlocfilehash: eea1801632fbeea4eb598f3973923d2436e1d813
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390215"
---
# <a name="correlation-types"></a><span data-ttu-id="8e846-102">関連付けの種類</span><span class="sxs-lookup"><span data-stu-id="8e846-102">Correlation Types</span></span>
<span data-ttu-id="8e846-103">各関連付けセットがに基づいて、**関連付けの種類**、これは、プロパティの一覧だけです。</span><span class="sxs-lookup"><span data-stu-id="8e846-103">Each correlation set is based on a **correlation type**, which is simply a list of properties.</span></span> <span data-ttu-id="8e846-104">これらのプロパティには、データのプロパティは、メッセージ自体内にある、またはシステムまたはメッセージ内で伝えられているデータに関連のないメッセージの詳細を説明するコンテキスト プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8e846-104">These properties might be data properties, which are found in the message itself, or context properties, which describe details of the system or messages that are unrelated to the data being conveyed in the message.</span></span>  
  
 <span data-ttu-id="8e846-105">関連付けの種類は、1 つ以上の関連付けセットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8e846-105">You can use a correlation type in more than one correlation set.</span></span> <span data-ttu-id="8e846-106">関連付けの種類のプロパティに別の値に関連付ける必要がある場合は、新しい関連付けセットを作成する必要があります: 各関連付けセットを 1 回だけ初期化できます。</span><span class="sxs-lookup"><span data-stu-id="8e846-106">If you need to correlate on different values for the properties in a correlation type, you must create a new correlation set—each correlation set can be initialized only once.</span></span>  
  
 <span data-ttu-id="8e846-107">メッセージの特定のプロパティがオーケストレーションにアクセスできることを宣言するプロパティ スキーマのプロパティを昇格することができます。</span><span class="sxs-lookup"><span data-stu-id="8e846-107">You can promote properties in a property schema to declare that certain properties in a message are accessible to your orchestration.</span></span> <span data-ttu-id="8e846-108">詳細については、次を参照してください。[プロパティの昇格](../core/promoting-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="8e846-108">For more information, see [Promoting Properties](../core/promoting-properties.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8e846-109">システム定義のプロパティを設定しないでください**BTS します。CorrelationToken**各メッセージに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="8e846-109">Do not set the system-defined property **BTS.CorrelationToken** that is associated with each message.</span></span> <span data-ttu-id="8e846-110">これは、メッセージを関連付けるときに、エンジンによって使用し、オーケストレーション メッセージの損失になる可能性があります設定するとします。</span><span class="sxs-lookup"><span data-stu-id="8e846-110">This is used by the engine in correlating messages, and setting it could result in your orchestration losing messages.</span></span>  
  
## <a name="validating-message-correlation-on-send-actions"></a><span data-ttu-id="8e846-111">送信アクションに対するメッセージの関連付けの検証</span><span class="sxs-lookup"><span data-stu-id="8e846-111">Validating Message Correlation on Send Actions</span></span>  
 <span data-ttu-id="8e846-112">オーケストレーションから送信するメッセージのプロパティを検証する、関連付けセットのプロパティが反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8e846-112">You can validate the properties of a message that you send from your orchestration to ensure that it reflects the properties in its correlation set.</span></span> <span data-ttu-id="8e846-113">既定では、この検証は無効です。</span><span class="sxs-lookup"><span data-stu-id="8e846-113">By default, this validation is disabled.</span></span> <span data-ttu-id="8e846-114">これを有効にする方法については、次を参照してください。[オーケストレーション エンジンの実行時の検証](../core/runtime-validation-for-the-orchestration-engine.md)です。</span><span class="sxs-lookup"><span data-stu-id="8e846-114">For information on how to enable it, see [Runtime Validation for the Orchestration Engine](../core/runtime-validation-for-the-orchestration-engine.md).</span></span>