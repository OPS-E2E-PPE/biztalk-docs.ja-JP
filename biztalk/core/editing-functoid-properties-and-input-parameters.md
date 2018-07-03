---
title: Functoid のプロパティおよび入力パラメーターの編集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 257f92d7-8196-4c7c-98de-819996270e43
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e95e6d3c4c026038c8118bff3a00e6ddde824df
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982379"
---
# <a name="editing-functoid-properties-and-input-parameters"></a><span data-ttu-id="7b831-102">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="7b831-102">Editing Functoid Properties and Input Parameters</span></span>
<span data-ttu-id="7b831-103">Functoid のプロパティは、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="7b831-103">Functoid properties can be categorized as follows:</span></span>  
  
- <span data-ttu-id="7b831-104">**ラベル**と**入力パラメーター**します。</span><span class="sxs-lookup"><span data-stu-id="7b831-104">**Label** and **Input parameters**.</span></span> <span data-ttu-id="7b831-105">: これら 2 つのプロパティは、読み取り/書き込みが可能で、すべての Functoid で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b831-105">These two properties are read/write and are available for all functoids.</span></span> <span data-ttu-id="7b831-106">**ラベル**プロパティは、マップの維持に役立つことがある functoid の特定のインスタンスのわかりやすい名前を提供するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="7b831-106">The **Label** property provides a mechanism for providing a descriptive name for a particular instance of a functoid, which may help in maintaining maps.</span></span> <span data-ttu-id="7b831-107">**入力パラメーター**プロパティへのアクセスを提供する、**構成\<Functoid\> Functoid**  ダイアログ ボックスで、functoid の構成で中心的な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="7b831-107">The **Input parameters** property provides access to the **Configure \<Functoid\> Functoid** dialog box, which plays a central role in functoid configuration.</span></span>  
  
- <span data-ttu-id="7b831-108">**スクリプト**と**テーブル ループ グリッド**します。</span><span class="sxs-lookup"><span data-stu-id="7b831-108">**Script** and **Table Looping Grid**.</span></span> <span data-ttu-id="7b831-109">これら 2 つのプロパティに適用されるダイアログ ボックスへのアクセスを提供する、 **Scripting**と**テーブル ループ**functoid の場合、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="7b831-109">These two properties provide access to dialog boxes that are only applicable to the **Scripting** and **Table Looping** functoids, respectively.</span></span> <span data-ttu-id="7b831-110">これらのダイアログ ボックスは、**スクリプト Functoid の構成** ダイアログ ボックスおよび**テーブル ループ Functoid の構成** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="7b831-110">These dialog boxes are the **Configure Scripting Functoid** dialog box and the **Configure Table Looping Functoid** dialog box.</span></span>  
  
- <span data-ttu-id="7b831-111">**名前**、**ヘルプ**、**最大入力パラメーター**、および**最小入力パラメーター**します。</span><span class="sxs-lookup"><span data-stu-id="7b831-111">**Name**, **Help**, **Maximum Input Parameters**, and **Minimum Input Parameters**.</span></span> <span data-ttu-id="7b831-112">: これらの 4 つのプロパティは参照用で常に読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="7b831-112">These four are informational and always read-only.</span></span>  
  
  <span data-ttu-id="7b831-113">これらの functoid プロパティの概念については、次を参照してください。 [Functoid プロパティ](../core/functoid-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b831-113">For conceptual information about these functoid properties, see [Functoid Properties](../core/functoid-properties.md).</span></span>  
  
  <span data-ttu-id="7b831-114">このセクションで、操作と変更具体的には、構成用のスクリプト functoid の入力パラメーターを構成するための一般的な手順を含む、functoid のプロパティのための手順について説明します、**スクリプト** functoid のテーブル グリッドを構成して、**テーブル ループ**functoid。</span><span class="sxs-lookup"><span data-stu-id="7b831-114">This section provides step-by-step instructions for working with, and specifically modifying, the properties of functoids, including general instructions for configuring input parameters for functoids, configuring script for the **Scripting** functoid, and configuring table grid for the **Table Looping** functoid.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b831-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7b831-115">In This Section</span></span>  
  
-   [<span data-ttu-id="7b831-116">Functoid 入力パラメーターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7b831-116">How to Configure Functoid Input Parameters</span></span>](../core/how-to-configure-functoid-input-parameters.md)  
  
-   [<span data-ttu-id="7b831-117">スクリプト Functoid の構成方法</span><span class="sxs-lookup"><span data-stu-id="7b831-117">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)  
  
-   [<span data-ttu-id="7b831-118">テーブル ループを構成する方法とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="7b831-118">How to Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="7b831-119">Functoid、ラベルし、コメントする方法</span><span class="sxs-lookup"><span data-stu-id="7b831-119">How to Label and Comment a Functoid</span></span>](../core/how-to-label-and-comment-a-functoid.md)