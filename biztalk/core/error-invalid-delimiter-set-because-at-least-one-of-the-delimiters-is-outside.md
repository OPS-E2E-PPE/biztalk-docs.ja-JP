---
title: "無効な区切り記号の許容範囲外にあるため、区切り記号の少なくとも 1 つの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="e3d65-102">1 つ以上の区切り記号が有効範囲外であるため、設定されている区切り記号は無効です</span><span class="sxs-lookup"><span data-stu-id="e3d65-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="e3d65-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e3d65-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e3d65-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e3d65-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="e3d65-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e3d65-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="e3d65-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e3d65-106">Event ID</span></span>|-|  
|<span data-ttu-id="e3d65-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e3d65-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="e3d65-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="e3d65-108"> EDI</span></span>|  
|<span data-ttu-id="e3d65-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e3d65-109">Component</span></span>|<span data-ttu-id="e3d65-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="e3d65-110">EDI Engine</span></span>|  
|<span data-ttu-id="e3d65-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e3d65-111">Symbolic Name</span></span>|<span data-ttu-id="e3d65-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="e3d65-112">DelimiterOutOfRange</span></span>|  
|<span data-ttu-id="e3d65-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e3d65-113">Message Text</span></span>|<span data-ttu-id="e3d65-114">無効な区切り記号が設定されています ({0})。1 つ以上の区切り記号が、有効範囲である 0 ～ 127 の範囲外です。</span><span class="sxs-lookup"><span data-stu-id="e3d65-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e3d65-115">説明</span><span class="sxs-lookup"><span data-stu-id="e3d65-115">Explanation</span></span>  
 <span data-ttu-id="e3d65-116">このエラー/警告/情報イベントは、インターチェンジの 1 つ以上の区切り記号が、ASCII 文字セットの値の範囲外だったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e3d65-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e3d65-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e3d65-117">User Action</span></span>  
 <span data-ttu-id="e3d65-118">このエラーを解決するには、インターチェンジの各区切り記号が ASCII 文字セットの範囲内であることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="e3d65-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>