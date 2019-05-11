---
title: エラー - XML 入力ファイルが存在しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xmlInputFileDoesNotExist
ms.assetid: d222e615-60c8-46f5-a8de-fc59650978c7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 202d86ceee251db8a2ae66f85ac90f005e311f53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346194"
---
# <a name="error---xml-input-file-does-not-exist"></a><span data-ttu-id="ac7ea-102">エラー - XML 入力ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="ac7ea-102">Error - XML Input File Does Not Exist</span></span>
<span data-ttu-id="ac7ea-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="ac7ea-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ac7ea-104">btm1039</span><span class="sxs-lookup"><span data-stu-id="ac7ea-104">btm1039</span></span>  
  
 <span data-ttu-id="ac7ea-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="ac7ea-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ac7ea-106">マップのテスト操作用に指定する XML 入力インスタンス メッセージ ファイルが存在しません。</span><span class="sxs-lookup"><span data-stu-id="ac7ea-106">The XML input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="ac7ea-107">ときの値、 **TestMap の入力**マップ プロパティが XML での既存の XML インスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティにマップします。</span><span class="sxs-lookup"><span data-stu-id="ac7ea-107">When the value of the **TestMap Input** map property is set to XML, you must specify an existing XML instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="ac7ea-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="ac7ea-108">**User Action**</span></span>  
  
 <span data-ttu-id="ac7ea-109">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac7ea-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="ac7ea-110">使用して、**入力ファイルの選択**ダイアログ ボックスで、既存の XML インスタンスのマップの送信元スキーマに準拠したメッセージ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="ac7ea-110">Using the **Select Input File** dialog box, select an existing XML instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="ac7ea-111">またはの [値] フィールドに直接この XML ファイルのパスを入力することができます、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ac7ea-111">Alternatively, you can type the path of this XML file directly into the value field of the **TestMap Input Instance** property.</span></span>