---
title: "必須データ要素がありません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b0c2d415b977c069e351d90fa5ad68b430c3f2f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="508be-102">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="508be-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="508be-103">詳細</span><span class="sxs-lookup"><span data-stu-id="508be-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="508be-104">製品名</span><span class="sxs-lookup"><span data-stu-id="508be-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="508be-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="508be-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="508be-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="508be-106">Event ID</span></span>|-|  
|<span data-ttu-id="508be-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="508be-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="508be-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="508be-108"> EDI</span></span>|  
|<span data-ttu-id="508be-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="508be-109">Component</span></span>|<span data-ttu-id="508be-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="508be-110">EDI Engine</span></span>|  
|<span data-ttu-id="508be-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="508be-111">Symbolic Name</span></span>|<span data-ttu-id="508be-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="508be-112">X12DeMandatoryDataElementMissingDescription</span></span>|  
|<span data-ttu-id="508be-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="508be-113">Message Text</span></span>|<span data-ttu-id="508be-114">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="508be-114">Mandatory data element missing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="508be-115">説明</span><span class="sxs-lookup"><span data-stu-id="508be-115">Explanation</span></span>  
 <span data-ttu-id="508be-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) データ要素がインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="508be-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="508be-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="508be-117">User Action</span></span>  
 <span data-ttu-id="508be-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのデータ要素がインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="508be-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>