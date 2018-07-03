---
title: 比較演算子が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8383230d-9bf6-4bc5-9300-4cfd0ad38f28
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87b44f68168570c229b66cb6ee767cf38229dc74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989715"
---
# <a name="the-comparison-operator-is-not-valid"></a><span data-ttu-id="ffd81-102">比較演算子が無効です</span><span class="sxs-lookup"><span data-stu-id="ffd81-102">The comparison operator is not valid</span></span>
## <a name="details"></a><span data-ttu-id="ffd81-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ffd81-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ffd81-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ffd81-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ffd81-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ffd81-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ffd81-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ffd81-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ffd81-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ffd81-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ffd81-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ffd81-108"> EDI</span></span> |
|    <span data-ttu-id="ffd81-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ffd81-109">Component</span></span>    |                                    <span data-ttu-id="ffd81-110">バッチ処理エンジン</span><span class="sxs-lookup"><span data-stu-id="ffd81-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="ffd81-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ffd81-111">Symbolic Name</span></span>  |                               <span data-ttu-id="ffd81-112">InvalidComparisonOperator</span><span class="sxs-lookup"><span data-stu-id="ffd81-112">InvalidComparisonOperator</span></span>                                |
|  <span data-ttu-id="ffd81-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ffd81-113">Message Text</span></span>   |             <span data-ttu-id="ffd81-114">比較演算子が無効です。</span><span class="sxs-lookup"><span data-stu-id="ffd81-114">The comparison operator is not valid.</span></span> <span data-ttu-id="ffd81-115">例外メッセージ = {0}</span><span class="sxs-lookup"><span data-stu-id="ffd81-115">Exception message = {0}</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="ffd81-116">説明</span><span class="sxs-lookup"><span data-stu-id="ffd81-116">Explanation</span></span>  
 <span data-ttu-id="ffd81-117">このエラー/警告/情報イベントは、[バッチ フィルター] ダイアログ ボックスの行に入力された比較演算子が、プロパティと値に対して有効ではなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ffd81-117">This Error/Warning/Information event indicates that the comparison operator entered for a row of the Batch Filter dialog box was not valid for the property and the value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ffd81-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ffd81-118">User Action</span></span>  
 <span data-ttu-id="ffd81-119">このエラーを解決するには、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジ バッチ作成用の設定] ページで [バッチ フィルター] ダイアログ ボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="ffd81-119">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="ffd81-120">[バッチ フィルター] グリッドの行に入力された比較演算子が、プロパティと値に対して有効なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ffd81-120">Make sure that the comparison operators entered for rows in the Batch Filter grid are valid for the property and the value.</span></span>