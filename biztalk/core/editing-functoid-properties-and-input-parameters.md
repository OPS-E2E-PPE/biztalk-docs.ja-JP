---
title: Functoid のプロパティおよび入力パラメーターを編集 |Microsoft ドキュメント
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
ms.openlocfilehash: a3d87396713b7fa8f7874b921e6ee9097399d1c6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968621"
---
# <a name="editing-functoid-properties-and-input-parameters"></a><span data-ttu-id="8eb4e-102">Functoid のプロパティおよび入力パラメーターの編集</span><span class="sxs-lookup"><span data-stu-id="8eb4e-102">Editing Functoid Properties and Input Parameters</span></span>
<span data-ttu-id="8eb4e-103">Functoid のプロパティは、次のように分類できます。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-103">Functoid properties can be categorized as follows:</span></span>  
  
-   <span data-ttu-id="8eb4e-104">**ラベル**と**入力パラメーター**です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-104">**Label** and **Input parameters**.</span></span> <span data-ttu-id="8eb4e-105">: これら 2 つのプロパティは、読み取り/書き込みが可能で、すべての Functoid で使用できます。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-105">These two properties are read/write and are available for all functoids.</span></span> <span data-ttu-id="8eb4e-106">**ラベル**プロパティは、functoid は、マップの維持に役立つ場合がありますの特定のインスタンスのわかりやすい名前を指定するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-106">The **Label** property provides a mechanism for providing a descriptive name for a particular instance of a functoid, which may help in maintaining maps.</span></span> <span data-ttu-id="8eb4e-107">**入力パラメーター**プロパティへのアクセスを提供する、**構成\<Functoid\> Functoid**  ダイアログ ボックスは、functoid の構成で中心的な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-107">The **Input parameters** property provides access to the **Configure \<Functoid\> Functoid** dialog box, which plays a central role in functoid configuration.</span></span>  
  
-   <span data-ttu-id="8eb4e-108">**スクリプト**と**テーブル ループ グリッド**です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-108">**Script** and **Table Looping Grid**.</span></span> <span data-ttu-id="8eb4e-109">これら 2 つのプロパティのみに適用されるダイアログ ボックスへのアクセスを提供する、**スクリプト**と**テーブル ループ**functoid、それぞれします。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-109">These two properties provide access to dialog boxes that are only applicable to the **Scripting** and **Table Looping** functoids, respectively.</span></span> <span data-ttu-id="8eb4e-110">これらのダイアログ ボックスは、**スクリプト Functoid の構成** ダイアログ ボックスおよび**テーブル ループ Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-110">These dialog boxes are the **Configure Scripting Functoid** dialog box and the **Configure Table Looping Functoid** dialog box.</span></span>  
  
-   <span data-ttu-id="8eb4e-111">**名前**、**ヘルプ**、**最大入力パラメーター**、および**最小入力パラメーター**です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-111">**Name**, **Help**, **Maximum Input Parameters**, and **Minimum Input Parameters**.</span></span> <span data-ttu-id="8eb4e-112">: これらの 4 つのプロパティは参照用で常に読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-112">These four are informational and always read-only.</span></span>  
  
 <span data-ttu-id="8eb4e-113">これらの functoid プロパティの概念については、次を参照してください。 [Functoid プロパティ](../core/functoid-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-113">For conceptual information about these functoid properties, see [Functoid Properties](../core/functoid-properties.md).</span></span>  
  
 <span data-ttu-id="8eb4e-114">このセクションで手順を使用し、具体的にはのプロパティおよび変更のスクリプトを構成する functoid の入力パラメーターを構成するための一般的な手順を含む functoid についてを説明する、**スクリプト** functoid、および構成のテーブル グリッドを**テーブル ループ**functoid です。</span><span class="sxs-lookup"><span data-stu-id="8eb4e-114">This section provides step-by-step instructions for working with, and specifically modifying, the properties of functoids, including general instructions for configuring input parameters for functoids, configuring script for the **Scripting** functoid, and configuring table grid for the **Table Looping** functoid.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8eb4e-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8eb4e-115">In This Section</span></span>  
  
-   [<span data-ttu-id="8eb4e-116">Functoid 入力パラメーターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8eb4e-116">How to Configure Functoid Input Parameters</span></span>](../core/how-to-configure-functoid-input-parameters.md)  
  
-   [<span data-ttu-id="8eb4e-117">スクリプト Functoid を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8eb4e-117">How to Configure the Scripting Functoid</span></span>](../core/how-to-configure-the-scripting-functoid.md)  
  
-   [<span data-ttu-id="8eb4e-118">テーブル ループを構成する方法とテーブル抽出 Functoid</span><span class="sxs-lookup"><span data-stu-id="8eb4e-118">How to Configure the Table Looping and Table Extractor Functoids</span></span>](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)  
  
-   [<span data-ttu-id="8eb4e-119">ラベルとコメント、Functoid をする方法</span><span class="sxs-lookup"><span data-stu-id="8eb4e-119">How to Label and Comment a Functoid</span></span>](../core/how-to-label-and-comment-a-functoid.md)