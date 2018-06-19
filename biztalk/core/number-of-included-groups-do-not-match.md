---
title: 含まれているグループの数が一致しません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d61ac17-92cd-4a5e-81e6-e2c6fc4085bb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f02262012a5d02cebaf86fae5a4d19d9b5486d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263034"
---
# <a name="number-of-included-groups-do-not-match"></a><span data-ttu-id="2ea3e-102">含まれているグループの数が一致しません</span><span class="sxs-lookup"><span data-stu-id="2ea3e-102">Number of included groups do not match</span></span>
## <a name="details"></a><span data-ttu-id="2ea3e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2ea3e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2ea3e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2ea3e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2ea3e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2ea3e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2ea3e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2ea3e-106">Event ID</span></span>|-|  
|<span data-ttu-id="2ea3e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2ea3e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2ea3e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2ea3e-108"> EDI</span></span>|  
|<span data-ttu-id="2ea3e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2ea3e-109">Component</span></span>|<span data-ttu-id="2ea3e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="2ea3e-110">EDI Engine</span></span>|  
|<span data-ttu-id="2ea3e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2ea3e-111">Symbolic Name</span></span>|<span data-ttu-id="2ea3e-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span><span class="sxs-lookup"><span data-stu-id="2ea3e-112">X12Ta1InvalidNumberOfIncludedGroupsDescription</span></span>|  
|<span data-ttu-id="2ea3e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2ea3e-113">Message Text</span></span>|<span data-ttu-id="2ea3e-114">グループ数含まれているが一致しません</span><span class="sxs-lookup"><span data-stu-id="2ea3e-114">Number Of included groups do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2ea3e-115">説明</span><span class="sxs-lookup"><span data-stu-id="2ea3e-115">Explanation</span></span>  
 <span data-ttu-id="2ea3e-116">このエラー/警告/情報イベントは、インターチェンジに含まれているグループの数が、インターチェンジ トレーラー (IEA01 フィールド) 内の数と等しくないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2ea3e-116">This Error/Warning/Information event indicates that the number of groups in the interchange does not equal the number in the interchange trailer (IEA01 field).</span></span> <span data-ttu-id="2ea3e-117">これは、インターチェンジが保存されて、インターチェンジがエラーで中断されている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="2ea3e-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="2ea3e-118">(インターチェンジが保存され、トランザクション セットがエラーで中断している場合、またはインターチェンジが分割されている場合、エラー メッセージは通知されません)。</span><span class="sxs-lookup"><span data-stu-id="2ea3e-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2ea3e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2ea3e-119">User Action</span></span>  
 <span data-ttu-id="2ea3e-120">このエラーを解決するには、インターチェンジ トレーラーの IEA01 フィールド内の数が、インターチェンジ内のグループの数と同じであることを確認し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="2ea3e-120">To resolve this error, make sure that the number in the IEA01 field of the interchange trailer is the same as the number of groups in the interchange, and then resend the interchange.</span></span>