---
title: "エラー - 入力ファイルが存在しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.inputFileDoesNotExist
ms.assetid: 6cd2f076-6c3e-46e3-8be4-dad2d9b95d37
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a14221857ebb567020a52c2ff0939b506d28937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---input-file-does-not-exist"></a><span data-ttu-id="8f0a6-102">エラー - 入力ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="8f0a6-102">Error - Input File Does Not Exist</span></span>
<span data-ttu-id="8f0a6-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="8f0a6-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8f0a6-104">btm1037</span><span class="sxs-lookup"><span data-stu-id="8f0a6-104">btm1037</span></span>  
  
 <span data-ttu-id="8f0a6-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="8f0a6-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8f0a6-106">マップのテスト操作が存在しないと、マップのテストの入力の型に設定されていない指定した入力インスタンス メッセージ ファイル**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-106">The input instance message file specified for the Test Map operation does not exist, and the type of the Test Map input is not set to **Generate Instance**.</span></span> <span data-ttu-id="8f0a6-107">ときの値、 **TestMap の入力**マップのプロパティに設定されていない**インスタンスの生成**、既存のインスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティをマップします。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-107">When the value of the **TestMap Input** map property is not set to **Generate Instance**, you must specify an existing instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="8f0a6-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="8f0a6-108">**User Action**</span></span>  
  
 <span data-ttu-id="8f0a6-109">適宜、以下のマップ プロパティのいずれかを設定します。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-109">As appropriate, set one or the other of the following map properties:</span></span>  
  
-   <span data-ttu-id="8f0a6-110">**TestMap の入力インスタンス。**</span><span class="sxs-lookup"><span data-stu-id="8f0a6-110">**TestMap Input Instance.**</span></span> <span data-ttu-id="8f0a6-111">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-111">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="8f0a6-112">使用して、**入力ファイルの選択**ダイアログ ボックスで、既存のインスタンス メッセージ マップの送信元スキーマに準拠しているファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-112">Using the **Select Input File** dialog box, select an existing instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="8f0a6-113">値フィールドに直接このファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-113">Alternatively, you can type the path of this file directly into the value field of the **TestMap Input Instance** property.</span></span>  
  
-   <span data-ttu-id="8f0a6-114">**TestMap の入力します。**</span><span class="sxs-lookup"><span data-stu-id="8f0a6-114">**TestMap Input.**</span></span> <span data-ttu-id="8f0a6-115">入力インスタンス メッセージ ファイルを指定することを回避するのには、ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト**のタブ、**プロパティ ページ**の値フィールドに使用して、ドロップダウン リスト、マップのダイアログ ボックス、 **TestMap の入力**プロパティを選択する**インスタンスの生成**です。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-115">To avoid specifying an input instance message file, right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab of the **Property Pages** dialog box for the map, use the drop-down list in the value field of the **TestMap Input** property to select **Generate Instance**.</span></span> <span data-ttu-id="8f0a6-116">ここでは、必要がありますいないファイルを指定するため、 **TestMap の入力インスタンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="8f0a6-116">In this case, you need not specify a file for the **TestMap Input Instance** property.</span></span>