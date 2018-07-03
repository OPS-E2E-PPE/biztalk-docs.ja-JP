---
title: 無効な区切り記号の許容範囲外である少なくとも 1 つの区切り記号の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a54467c6d611aefd58d2dfd51c21974c3a5df7c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022512"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="aed9c-102">1 つ以上の区切り記号が有効範囲外であるため、設定されている区切り記号は無効です</span><span class="sxs-lookup"><span data-stu-id="aed9c-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="aed9c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="aed9c-103">Details</span></span>  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="aed9c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="aed9c-104">Product Name</span></span>   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| <span data-ttu-id="aed9c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="aed9c-105">Product Version</span></span> |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    <span data-ttu-id="aed9c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="aed9c-106">Event ID</span></span>     |                                                   -                                                    |
|  <span data-ttu-id="aed9c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="aed9c-107">Event Source</span></span>   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="aed9c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="aed9c-108"> EDI</span></span>         |
|    <span data-ttu-id="aed9c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="aed9c-109">Component</span></span>    |                                               <span data-ttu-id="aed9c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="aed9c-110">EDI Engine</span></span>                                               |
|  <span data-ttu-id="aed9c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="aed9c-111">Symbolic Name</span></span>  |                                          <span data-ttu-id="aed9c-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="aed9c-112">DelimiterOutOfRange</span></span>                                           |
|  <span data-ttu-id="aed9c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="aed9c-113">Message Text</span></span>   | <span data-ttu-id="aed9c-114">無効な区切り記号セット{0}、区切り記号の少なくとも 1 つは、0 127 までからの許容範囲外です</span><span class="sxs-lookup"><span data-stu-id="aed9c-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="aed9c-115">説明</span><span class="sxs-lookup"><span data-stu-id="aed9c-115">Explanation</span></span>  
 <span data-ttu-id="aed9c-116">このエラー/警告/情報イベントは、インターチェンジの 1 つ以上の区切り記号が、ASCII 文字セットの値の範囲外だったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="aed9c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aed9c-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="aed9c-117">User Action</span></span>  
 <span data-ttu-id="aed9c-118">このエラーを解決するには、インターチェンジの各区切り記号が ASCII 文字セットの範囲内であることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="aed9c-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>