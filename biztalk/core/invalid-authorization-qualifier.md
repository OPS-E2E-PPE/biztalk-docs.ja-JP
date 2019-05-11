---
title: 無効な認証修飾子 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bc2a9f83-833f-4ea0-9421-7382ee1b1a54
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b39c4b6d21af8f7d7bc7fed2834760d2594a31ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330920"
---
# <a name="invalid-authorization-qualifier"></a><span data-ttu-id="ab7b8-102">認証修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="ab7b8-102">Invalid Authorization Qualifier</span></span>
## <a name="details"></a><span data-ttu-id="ab7b8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ab7b8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ab7b8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ab7b8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ab7b8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ab7b8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ab7b8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ab7b8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ab7b8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ab7b8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ab7b8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ab7b8-108">EDI</span></span> |
|    <span data-ttu-id="ab7b8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ab7b8-109">Component</span></span>    |                                       <span data-ttu-id="ab7b8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ab7b8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ab7b8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ab7b8-111">Symbolic Name</span></span>  |                     <span data-ttu-id="ab7b8-112">X12Ta1InvalidAuthorizationQualifierDescription</span><span class="sxs-lookup"><span data-stu-id="ab7b8-112">X12Ta1InvalidAuthorizationQualifierDescription</span></span>                     |
|  <span data-ttu-id="ab7b8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ab7b8-113">Message Text</span></span>   |                            <span data-ttu-id="ab7b8-114">認証修飾子が無効です</span><span class="sxs-lookup"><span data-stu-id="ab7b8-114">Invalid Authorization Qualifier</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="ab7b8-115">説明</span><span class="sxs-lookup"><span data-stu-id="ab7b8-115">Explanation</span></span>  
 <span data-ttu-id="ab7b8-116">このエラー/警告/情報イベントは、ISA01 の認証修飾子の値が、スキーマで指定されているいずれの列挙値とも一致しなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ab7b8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the Authorization Qualifier in ISA01 did not match any of the enumeration values specified by the schema.</span></span> <span data-ttu-id="ab7b8-117">スキーマは、BaseArtifacts.dll 内の X12ServiceSchema です。</span><span class="sxs-lookup"><span data-stu-id="ab7b8-117">The schema is the X12ServiceSchema in BaseArtifacts.dll.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ab7b8-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ab7b8-118">User Action</span></span>  
 <span data-ttu-id="ab7b8-119">このエラーを解決するには、ISA01 ヘッダーの値が X12ServiceSchema で指定されている列挙値の 1 つに一致することを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="ab7b8-119">To resolve this error, make sure that the value in the ISA01 header matches one of the enumeration values specified by the X12ServiceSchema, and then have the interchange resent.</span></span>