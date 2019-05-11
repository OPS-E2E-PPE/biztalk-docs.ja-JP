---
title: エラー - ネイティブの入力ファイルが存在しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fab62637232795a3cabb15d2ee4830e13e28477a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347331"
---
# <a name="error---native-input-file-does-not-exist"></a><span data-ttu-id="f6af0-102">エラー - ネイティブの入力ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="f6af0-102">Error - Native Input File Does Not Exist</span></span>
<span data-ttu-id="f6af0-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="f6af0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f6af0-104">btm1040</span><span class="sxs-lookup"><span data-stu-id="f6af0-104">btm1040</span></span>  
  
 <span data-ttu-id="f6af0-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="f6af0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f6af0-106">マップのテスト操作に指定されたネイティブ入力インスタンス メッセージ ファイルが存在しません。</span><span class="sxs-lookup"><span data-stu-id="f6af0-106">The native input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="f6af0-107">ときの値、 **TestMap の入力**マップ プロパティに設定されて**ネイティブ**、既存のネイティブ インスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6af0-107">When the value of the **TestMap Input** map property is set to **Native**, you must specify an existing native instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="f6af0-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="f6af0-108">**User Action**</span></span>  
  
 <span data-ttu-id="f6af0-109">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップの省略記号 (をクリックします。**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6af0-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="f6af0-110">**入力ファイルの選択**ダイアログ ボックスで、既存のネイティブ インスタンスのマップの送信元スキーマに準拠したメッセージ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="f6af0-110">In the **Select Input File** dialog box, select an existing native instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="f6af0-111">値フィールドに直接このネイティブ ファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6af0-111">Alternatively, you can type the path of this native file directly into the value field of the **TestMap Input Instance** property.</span></span>