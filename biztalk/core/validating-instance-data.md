---
title: インスタンス データの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c3ca83-0abf-42ba-8e29-653ff12d5e20
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 939c13c246aaed7db40b723845d6f0a7b95817bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007155"
---
# <a name="validate-instance-data"></a><span data-ttu-id="f94c4-102">インスタンス データを検証します。</span><span class="sxs-lookup"><span data-stu-id="f94c4-102">Validate Instance Data</span></span>

## <a name="overview"></a><span data-ttu-id="f94c4-103">概要</span><span class="sxs-lookup"><span data-stu-id="f94c4-103">Overview</span></span>
<span data-ttu-id="f94c4-104">マップのテストを実行している際に、インスタンス データを送信元および送信先スキーマに照合して検証し、スキーマの構造に準拠していることを確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f94c4-104">During the process of testing a map, you may want to validate instance data against the source and destination schemas to verify that the instance data adheres to the schema structure.</span></span> <span data-ttu-id="f94c4-105">送信元または送信先スキーマに対してインスタンス メッセージを検証するには、ソリューション エクスプ ローラーでスキーマを右クリックし、**インスタンスの検証**です。</span><span class="sxs-lookup"><span data-stu-id="f94c4-105">To validate an instance message against the source or destination schema, right-click the schema in the Solution Explorer, and then click **Validate Instance**.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="f94c4-106">出力でカスタム データまたは定数を使用する場合、送信元のテスト データと送信先の定数値のデータ型が有効であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f94c4-106">If you use custom data or constants in your output, you must verify that the data types of your source test data and target constant values are valid.</span></span> <span data-ttu-id="f94c4-107">マップを検証するときに BizTalk マッパーには、インスタンス データに、スキーマによって定義されたすべてのデータ型に違反しているかどうかはチェックされません。</span><span class="sxs-lookup"><span data-stu-id="f94c4-107">When you validate a map, BizTalk Mapper does not check whether or not the instance data violates any data types defined by the schemas.</span></span> <span data-ttu-id="f94c4-108">データ型の確認は、マップのテストまたはインスタンス データの検証を行うと実行されます。</span><span class="sxs-lookup"><span data-stu-id="f94c4-108">This is done when you test the map or validate the instance data.</span></span>  

 <span data-ttu-id="f94c4-109">生成し、BizTalk エディターを使用してインスタンス データを検証する方法の詳細については、[インスタンス メッセージの生成と検証](../core/instance-message-generation-and-validation.md)と[インスタンスの検証](../core/instance-validation.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94c4-109">For more information about how to generate and validate instance data by using BizTalk Editor, see [Instance Message Generation and Validation](../core/instance-message-generation-and-validation.md) and [Instance Validation](../core/instance-validation.md).</span></span> <span data-ttu-id="f94c4-110">.</span><span class="sxs-lookup"><span data-stu-id="f94c4-110">.</span></span> <span data-ttu-id="f94c4-111">**値**BizTalk がインスタンス データがどのように生成するか、スキーマのノードのプロパティにも影響します。</span><span class="sxs-lookup"><span data-stu-id="f94c4-111">The **Value** property of the node of a schema also affects how BizTalk generates instance data.</span></span> <span data-ttu-id="f94c4-112">詳細については、、**スキーマのノード プロパティ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f94c4-112">For more information, see the **Schema Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="f94c4-113">参照</span><span class="sxs-lookup"><span data-stu-id="f94c4-113">See Also</span></span>  
- [<span data-ttu-id="f94c4-114">インスタンス メッセージの生成および検証</span><span class="sxs-lookup"><span data-stu-id="f94c4-114">Instance Message Generation and Validation</span></span>](../core/instance-message-generation-and-validation.md)   
- [<span data-ttu-id="f94c4-115">Visual Studio でのスキーマを検証する方法</span><span class="sxs-lookup"><span data-stu-id="f94c4-115">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)   
- <span data-ttu-id="f94c4-116">**マップ プロパティのリファレンス** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f94c4-116">**Map Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="f94c4-117">マップのテスト</span><span class="sxs-lookup"><span data-stu-id="f94c4-117">Testing Maps</span></span>](../core/testing-maps.md)
