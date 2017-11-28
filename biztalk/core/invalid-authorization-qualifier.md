---
title: "無効な認証修飾子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbf33e8bd42b18134bd31f02f791b306ece97272
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-authorization-qualifier"></a><span data-ttu-id="9e30d-102">認証修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="9e30d-102">Invalid Authorization Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="9e30d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9e30d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e30d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9e30d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="9e30d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9e30d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="9e30d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9e30d-106">Event ID</span></span>|-|  
|<span data-ttu-id="9e30d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9e30d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9e30d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9e30d-108"> EDI</span></span>|  
|<span data-ttu-id="9e30d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9e30d-109">Component</span></span>|<span data-ttu-id="9e30d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="9e30d-110">EDI Engine</span></span>|  
|<span data-ttu-id="9e30d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9e30d-111">Symbolic Name</span></span>|<span data-ttu-id="9e30d-112">X12Ta1InvalidAuthorizationQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="9e30d-112">X12Ta1InvalidAuthorizationQualifierDescription</span></span>|  
|<span data-ttu-id="9e30d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9e30d-113">Message Text</span></span>|<span data-ttu-id="9e30d-114">認証修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="9e30d-114">Invalid Authorization Qualifier</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e30d-115">説明</span><span class="sxs-lookup"><span data-stu-id="9e30d-115">Explanation</span></span>  
 <span data-ttu-id="9e30d-116">このエラー/警告/情報イベントは、ISA01 の認証修飾子の値が、スキーマで指定されているいずれの列挙値とも一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9e30d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Qualifier in ISA01 did not match any of the enumeration values specified by the schema.</span></span> <span data-ttu-id="9e30d-117">スキーマは、BaseArtifacts.dll 内の X12ServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="9e30d-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e30d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9e30d-118">User Action</span></span>  
 <span data-ttu-id="9e30d-119">このエラーを解決するには、ISA01 ヘッダーの値が X12ServiceSchema で指定されている列挙値の 1 つに一致することを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="9e30d-119">To resolve this error, make sure that the value in the ISA01 header matches one of the enumeration values specified by the X12ServiceSchema, and then have the interchange resent.</span></span>