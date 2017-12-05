---
title: "エラー - Functoid の固定入力が一致しません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functoidFixedInputMismatch
ms.assetid: d235e7c3-efcf-4128-aef7-cdfdf1f317be
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8de4020105f357905e510be1694c0cf95a4af6c2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="error---functoid-fixed-input-mismatch"></a><span data-ttu-id="c9e1d-102">エラー - Functoid の固定入力が一致しません</span><span class="sxs-lookup"><span data-stu-id="c9e1d-102">Error - Functoid Fixed Input Mismatch</span></span>
<span data-ttu-id="c9e1d-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="c9e1d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="c9e1d-104">btm1010</span><span class="sxs-lookup"><span data-stu-id="c9e1d-104">btm1010</span></span>  
  
 <span data-ttu-id="c9e1d-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="c9e1d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="c9e1d-106">Functoid に指定されている入力パラメーターの数が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-106">The indicated functoid does not have the correct number of input parameters specified.</span></span> <span data-ttu-id="c9e1d-107">入力パラメーターの数は指定したものと同一である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-107">The number of input parameters must be exactly as specified.</span></span>  
  
 <span data-ttu-id="c9e1d-108">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="c9e1d-108">**User Action**</span></span>  
  
 <span data-ttu-id="c9e1d-109">次の方法の 1 つ以上を使用して、Functoid に、表示されている数の入力パラメーターを指定します。その際、想定されている入力パラメーターの順序に特に注意してください。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-109">Use one or more of the following methods to provide the indicated number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="c9e1d-110">リンクを追加するには、送信元スキーマまたは他の Functoid の出力のいずれかのノードと対象の Functoid の間をドラッグしてリンクを作成します。他の Functoid とは、マップ グリッド ページで対象の Functoid の左側に表示されている Functoid を指します。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-110">To create additional links, drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="c9e1d-111">その他のリンクを作成する対象の functoid を選択して、省略記号ボタンをクリックして (**.**) に関連付けられたボタン、**入力パラメーター**プロパティに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウを構成してで、入力パラメーターの順序を変更、**構成\<Functoid\> Functoid**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-111">To create additional links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid\> Functoid** dialog box.</span></span> <span data-ttu-id="c9e1d-112">このダイアログ ボックスでは、定数入力パラメーターを作成して値を設定し、他の入力パラメーターを考慮したうえで適切な順序に配置できます。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-112">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>  
  
-   <span data-ttu-id="c9e1d-113">対象の functoid の左側に接続されている各リンクについて、既存のリンクを削除するリンクを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-113">To remove existing links, for each link connected to the left side of the indicated functoid, right-click the link and then click **Delete**.</span></span>  
  
-   <span data-ttu-id="c9e1d-114">既存のリンクを削除する、対象の functoid を選択し、省略記号ボタンをクリックする (**.**) に関連付けられたボタン、**入力パラメーター**プロパティに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウでし、**構成\<Functoid\> Functoid**ダイアログ ボックスで、削除を選択しをクリックしてすべての入力パラメーター、 ![ ] (../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete")それぞれのボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-114">To remove existing links, select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then in the **Configure \<Functoid\> Functoid** dialog box, delete all input parameters by selecting and clicking the ![](../core/media/bts-tls-paramdelete.gif "bts_tls_paramdelete") button for each of them.</span></span> <span data-ttu-id="c9e1d-115">定数入力パラメーターを削除する場合は、この方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9e1d-115">You must use this method to delete constant input parameters.</span></span>