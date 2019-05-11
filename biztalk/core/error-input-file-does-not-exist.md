---
title: エラー - 入力ファイルが存在しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e825ba6d0046e3be686cd155b5a8892a5ae8b99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388805"
---
# <a name="error---input-file-does-not-exist"></a><span data-ttu-id="2e3ba-102">エラー - 入力ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="2e3ba-102">Error - Input File Does Not Exist</span></span>
<span data-ttu-id="2e3ba-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="2e3ba-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2e3ba-104">btm1037</span><span class="sxs-lookup"><span data-stu-id="2e3ba-104">btm1037</span></span>  
  
 <span data-ttu-id="2e3ba-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e3ba-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2e3ba-106">マップのテスト操作が存在しないため、マップのテスト入力の種類に設定されていない指定した入力インスタンス メッセージ ファイル**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-106">The input instance message file specified for the Test Map operation does not exist, and the type of the Test Map input is not set to **Generate Instance**.</span></span> <span data-ttu-id="2e3ba-107">ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**、既存のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティをマップします。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an existing instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="2e3ba-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="2e3ba-108">**User Action**</span></span>  
  
 <span data-ttu-id="2e3ba-109">必要に応じて、次のマップのプロパティのどちらかを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="2e3ba-110">**TestMap の入力インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="2e3ba-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="2e3ba-111">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="2e3ba-112">使用して、**入力ファイルの選択**ダイアログ ボックスで、既存のインスタンスのメッセージ マップの送信元スキーマに準拠しているファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-112">Using the **Select Input File** dialog box, select an existing instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="2e3ba-113">値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="2e3ba-114">**TestMap の入力。**</span><span class="sxs-lookup"><span data-stu-id="2e3ba-114">**TestMap Input.**</span></span> <span data-ttu-id="2e3ba-115">入力インスタンス メッセージ ファイルを指定することを避けるためには、[ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト**のタブ、**プロパティ ページ**] ダイアログ ボックスの値フィールドに、ドロップダウン リスト、マップ、 **TestMap の入力**プロパティを選択する**インスタンスの生成**します。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab of the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="2e3ba-116">ファイルを指定するこの例では、必要があります、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2e3ba-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>