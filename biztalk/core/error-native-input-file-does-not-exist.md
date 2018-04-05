---
title: エラー - ネイティブの入力ファイルが存在しない |Microsoft ドキュメント
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
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-input-file-does-not-exist"></a><span data-ttu-id="13fd1-102">エラー - ネイティブの入力ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="13fd1-102">Error - Native Input File Does Not Exist</span></span>
<span data-ttu-id="13fd1-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="13fd1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="13fd1-104">btm1040</span><span class="sxs-lookup"><span data-stu-id="13fd1-104">btm1040</span></span>  
  
 <span data-ttu-id="13fd1-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="13fd1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="13fd1-106">マップのテスト操作で使用するように指定されたネイティブ入力インスタンス メッセージ ファイルが存在しません。</span><span class="sxs-lookup"><span data-stu-id="13fd1-106">The native input instance message file specified for the Test Map operation does not exist.</span></span> <span data-ttu-id="13fd1-107">ときの値、 **TestMap の入力**マップのプロパティに設定されている**ネイティブ**、既存のネイティブ インスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。</span><span class="sxs-lookup"><span data-stu-id="13fd1-107">When the value of the **TestMap Input** map property is set to **Native**, you must specify an existing native instance message file for the **TestMap Input Instance** map property.</span></span>  
  
 <span data-ttu-id="13fd1-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="13fd1-108">**User Action**</span></span>  
  
 <span data-ttu-id="13fd1-109">ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="13fd1-109">Right-click the relevant map in Solution Explorer, click **Properties**, and then on the **Test Map** tab in the **Property Pages** dialog box for the map, click the ellipsis (**...**) button in the value field of the **TestMap Input Instance** property.</span></span> <span data-ttu-id="13fd1-110">**入力ファイルの選択**ダイアログ ボックスで、既存のネイティブ インスタンス マップの送信元スキーマに準拠したメッセージ ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="13fd1-110">In the **Select Input File** dialog box, select an existing native instance message file that conforms to the source schema of the map.</span></span> <span data-ttu-id="13fd1-111">値フィールドに直接このネイティブ ファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="13fd1-111">Alternatively, you can type the path of this native file directly into the value field of the **TestMap Input Instance** property.</span></span>