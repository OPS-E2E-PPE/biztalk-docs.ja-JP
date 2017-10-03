---
title: "データ要素に無効な文字 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db7e2c72-f2cc-4157-aa26-062d2cc1210b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc805fbede667013b56088b3d2c29913157c2fe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-character-in-data-element"></a><span data-ttu-id="c15cb-102">データ要素に無効な文字があります</span><span class="sxs-lookup"><span data-stu-id="c15cb-102">Invalid character in data element</span></span>
## <a name="details"></a><span data-ttu-id="c15cb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c15cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c15cb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c15cb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c15cb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c15cb-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c15cb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c15cb-106">Event ID</span></span>|-|  
|<span data-ttu-id="c15cb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c15cb-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c15cb-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c15cb-108"> EDI</span></span>|  
|<span data-ttu-id="c15cb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c15cb-109">Component</span></span>|<span data-ttu-id="c15cb-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c15cb-110">EDI Engine</span></span>|  
|<span data-ttu-id="c15cb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c15cb-111">Symbolic Name</span></span>|<span data-ttu-id="c15cb-112">X12DeInvalidCharacterInDataElementDescription</span><span class="sxs-lookup"><span data-stu-id="c15cb-112">X12DeInvalidCharacterInDataElementDescription</span></span>|  
|<span data-ttu-id="c15cb-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c15cb-113">Message Text</span></span>|<span data-ttu-id="c15cb-114">データ要素に無効な文字があります</span><span class="sxs-lookup"><span data-stu-id="c15cb-114">Invalid character in data element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c15cb-115">説明</span><span class="sxs-lookup"><span data-stu-id="c15cb-115">Explanation</span></span>  
 <span data-ttu-id="c15cb-116">このエラー/警告/情報イベントは、データ要素の値が EDI スキーマで指定された値に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c15cb-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a data element did not conform to the value specified in the EDI schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c15cb-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c15cb-117">User Action</span></span>  
 <span data-ttu-id="c15cb-118">このエラーを解決するには、データ要素の値が EDI スキーマに準拠していることを確認し、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="c15cb-118">To resolve this error, make sure that the value in the data element conforms to the EDI schema, and then have the interchange resent.</span></span>