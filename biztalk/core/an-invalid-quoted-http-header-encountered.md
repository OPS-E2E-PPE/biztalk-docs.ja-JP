---
title: 無効な HTTP ヘッダーが検出されました引用符で囲まれた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff1372dc2eea57843d6d671e617aeeb2b8e90dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359339"
---
# <a name="an-invalid-quoted-http-header-encountered"></a><span data-ttu-id="bc106-102">発生した無効な引用符で囲まれた HTTP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="bc106-102">An invalid quoted HTTP header encountered</span></span>
## <a name="details"></a><span data-ttu-id="bc106-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bc106-103">Details</span></span>  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bc106-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bc106-104">Product Name</span></span>   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="bc106-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bc106-105">Product Version</span></span> |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    <span data-ttu-id="bc106-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bc106-106">Event ID</span></span>     |                                                      -                                                       |
|  <span data-ttu-id="bc106-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bc106-107">Event Source</span></span>   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bc106-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bc106-108">EDI</span></span>            |
|    <span data-ttu-id="bc106-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc106-109">Component</span></span>    |                                                  <span data-ttu-id="bc106-110">AS2 エンジン</span><span class="sxs-lookup"><span data-stu-id="bc106-110">AS2 Engine</span></span>                                                  |
|  <span data-ttu-id="bc106-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bc106-111">Symbolic Name</span></span>  |                                                      -                                                       |
|  <span data-ttu-id="bc106-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bc106-112">Message Text</span></span>   | <span data-ttu-id="bc106-113">無効な引用符で囲まれた HTTP ヘッダーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="bc106-113">An invalid quoted HTTP header encountered.</span></span>  <span data-ttu-id="bc106-114">詳細は次のとおりです。ヘッダー名:"{0}"ヘッダーの値:"{1}"</span><span class="sxs-lookup"><span data-stu-id="bc106-114">Details are as follows:  Header Name: "{0}"  Header Value: "{1}"</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bc106-115">説明</span><span class="sxs-lookup"><span data-stu-id="bc106-115">Explanation</span></span>  
 <span data-ttu-id="bc106-116">このエラー/警告/情報イベントは、AS2 受信パイプラインまたはため、AS2 送信パイプラインが AS2 メッセージを処理できなかったことを示します、AS2 の名前からまたは AS2 のメッセージのメッセージを HTTP ヘッダーが正しく示されていません。</span><span class="sxs-lookup"><span data-stu-id="bc106-116">This Error/Warning/Information event indicates that the AS2 receive pipeline or the AS2 send pipeline could not process the AS2 message because the name of the AS2-From or AS2-To HTTP header in the message was not quoted correctly.</span></span> <span data-ttu-id="bc106-117">ヘッダー名は、スペース、円記号、または二重引用符で囲んだ名前に対応するために引用符で囲まれました。</span><span class="sxs-lookup"><span data-stu-id="bc106-117">The header name is quoted in order to accommodate a space, backslash, or double quotes within the name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bc106-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bc106-118">User Action</span></span>  
 <span data-ttu-id="bc106-119">このエラーを解決するのには、規則に従って、AS2 メッセージのヘッダー名を引用符に記載されている RFC 4130 のセクション 6.2「AS2 System Identifiers」"MIME ベース セキュリティで保護されたピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"。</span><span class="sxs-lookup"><span data-stu-id="bc106-119">To resolve this error, quote the header name in the AS2 message in accordance with the rules stated in section 6.2, "AS2 System Identifiers", in RFC 4130, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)".</span></span>