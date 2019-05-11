---
title: エラー - マップのテスト用の入力が有効ではありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.testMapInputsNotValid
ms.assetid: d885d366-92a3-4d2a-8e2b-58e06960864f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81aca2f6d941f281a2a720250714c76798762e6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346572"
---
# <a name="error---test-map-inputs-not-valid"></a><span data-ttu-id="53091-102">エラー - マップのテスト用の入力が無効です。</span><span class="sxs-lookup"><span data-stu-id="53091-102">Error - Test Map Inputs Not Valid</span></span>
<span data-ttu-id="53091-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="53091-103">**Error Code**</span></span>  
  
 <span data-ttu-id="53091-104">btm1036</span><span class="sxs-lookup"><span data-stu-id="53091-104">btm1036</span></span>  
  
 <span data-ttu-id="53091-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="53091-105">**Explanation**</span></span>  
  
 <span data-ttu-id="53091-106">マップのテスト操作の入力インスタンス メッセージ ファイルが指定されていないと、TestMap の入力の種類に設定されていない**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="53091-106">No input instance message file has been specified for the Test Map operation, and the type of the TestMap input is not set to **Generate Instance**.</span></span> <span data-ttu-id="53091-107">ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。</span><span class="sxs-lookup"><span data-stu-id="53091-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="53091-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="53091-108">**User Action**</span></span>  
  
 <span data-ttu-id="53091-109">必要に応じて、次のマップのプロパティのどちらかを設定します。</span><span class="sxs-lookup"><span data-stu-id="53091-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="53091-110">**TestMap の入力インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="53091-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="53091-111">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53091-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="53091-112">使用して、**入力ファイルの選択** ダイアログ ボックスで、インスタンス メッセージ マップの送信元スキーマに準拠しているファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="53091-112">Using the **Select Input File** dialog box, select an instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="53091-113">値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53091-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="53091-114">**TestMap の入力。**</span><span class="sxs-lookup"><span data-stu-id="53091-114">**TestMap Input.**</span></span> <span data-ttu-id="53091-115">入力インスタンス メッセージ ファイルを指定することを避けるためには、ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックスの値フィールドに、ドロップダウン リスト、マップ、 **TestMap の入力**プロパティを選択する**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="53091-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="53091-116">ファイルを指定するこの例では、必要があります、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="53091-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>