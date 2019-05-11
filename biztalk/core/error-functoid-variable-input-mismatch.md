---
title: エラー - Functoid 変数の入力が一致しません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.functoidVariableInputMismatch
ms.assetid: fda3066b-d0de-4f61-b78f-4726f6796e1f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed171944d3d9e9dbb0de5b4c030ddc1af21ae8a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389083"
---
# <a name="error---functoid-variable-input-mismatch"></a><span data-ttu-id="69924-102">エラー - Functoid 変数の入力が一致しません</span><span class="sxs-lookup"><span data-stu-id="69924-102">Error - Functoid Variable Input Mismatch</span></span>
<span data-ttu-id="69924-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="69924-103">**Error Code**</span></span>  

 <span data-ttu-id="69924-104">btm1011</span><span class="sxs-lookup"><span data-stu-id="69924-104">btm1011</span></span>  

 <span data-ttu-id="69924-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="69924-105">**Explanation**</span></span>  

 <span data-ttu-id="69924-106">対象の functoid には、指定された入力パラメーターの正しい数はありません。</span><span class="sxs-lookup"><span data-stu-id="69924-106">The indicated functoid does not have the correct number of input parameters specified.</span></span> <span data-ttu-id="69924-107">入力パラメーターの数は、指定した範囲内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="69924-107">The number of input parameters must be in the specified range.</span></span>  

 <span data-ttu-id="69924-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="69924-108">**User Action**</span></span>  

 <span data-ttu-id="69924-109">1 つ以上の入力パラメーターの予想される順序に特に注意してください、対象の functoid の入力パラメーターの指定された数を指定する次のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="69924-109">Use one or more of the following methods to provide the indicated number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  

- <span data-ttu-id="69924-110">その他のリンクを作成するには、送信元スキーマまたはマップのグリッド ページで、対象の functoid の左側にある他の functoid の出力で、対象の functoid といずれかのノード間のリンクを作成するドラッグします。</span><span class="sxs-lookup"><span data-stu-id="69924-110">To create additional links, drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  

- <span data-ttu-id="69924-111">その他のリンクを作成する対象の functoid を選択、省略記号をクリックします (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティで、Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成して、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="69924-111">To create additional links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="69924-112">定数入力パラメーターの作成、指定された値、およびこのダイアログ ボックスで、その他の入力パラメーターを基準とした適切な順序で配置できます。</span><span class="sxs-lookup"><span data-stu-id="69924-112">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>  

- <span data-ttu-id="69924-113">リンクごとに、対象の functoid の左側に接続されている既存のリンクを削除するリンクを右クリックし をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="69924-113">To remove existing links, for each link connected to the left side of the indicated functoid, right-click the link and then click **Delete**.</span></span>  

- <span data-ttu-id="69924-114">既存のリンクを削除、対象の functoid を選択し、省略記号をクリックする (**.**) ボタンに関連付けられている、**入力パラメーター**プロパティ、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、し、**構成\<Functoid\> Functoid**ダイアログ ボックスで、削除を選択すると、クリックして入力パラメーターはすべて、 ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="69924-114">To remove existing links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete all input parameters by selecting and clicking the ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span> <span data-ttu-id="69924-115">このメソッドを使用して、定数入力パラメーターを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69924-115">You must use this method to delete constant input parameters.</span></span>
