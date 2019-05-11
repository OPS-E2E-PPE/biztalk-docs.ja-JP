---
title: エラー - Functoid に入力がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db8ea58b62537d26b8bc088d84eefa6186dc8941
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348356"
---
# <a name="error---functoid-has-no-input"></a><span data-ttu-id="628c5-102">エラー - Functoid に入力がありません。</span><span class="sxs-lookup"><span data-stu-id="628c5-102">Error - Functoid Has No Input</span></span>
<span data-ttu-id="628c5-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="628c5-103">**Error Code**</span></span>  

 <span data-ttu-id="628c5-104">btm1012</span><span class="sxs-lookup"><span data-stu-id="628c5-104">btm1012</span></span>  

 <span data-ttu-id="628c5-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="628c5-105">**Explanation**</span></span>  

 <span data-ttu-id="628c5-106">対象の functoid には、少なくとも 1 つの入力パラメーターが必要ですが、入力パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="628c5-106">The indicated functoid requires at least one input parameter, but no input parameters have been specified.</span></span>  

 <span data-ttu-id="628c5-107">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="628c5-107">**User Action**</span></span>  

 <span data-ttu-id="628c5-108">入力パラメーターの予想される順序に特に注意してください、対象の functoid の入力パラメーターの適切な数を提供するのに、次のメソッドの一方または両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="628c5-108">Use one or both of the following methods to provide the appropriate number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  

- <span data-ttu-id="628c5-109">ドラッグすると、送信元スキーマまたはマップのグリッド ページで、対象の functoid の左側にある他の functoid の出力で、対象の functoid といずれかのノード間のリンクを作成します。</span><span class="sxs-lookup"><span data-stu-id="628c5-109">Drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  

- <span data-ttu-id="628c5-110">対象の functoid を選択し、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="628c5-110">Select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="628c5-111">定数入力パラメーターの作成、指定された値、およびこのダイアログ ボックスで、その他の入力パラメーターを基準とした適切な順序で配置できます。</span><span class="sxs-lookup"><span data-stu-id="628c5-111">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>
