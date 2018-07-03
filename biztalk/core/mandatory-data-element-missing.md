---
title: 必須データ要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966491"
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="c1acc-102">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="c1acc-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="c1acc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c1acc-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c1acc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c1acc-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c1acc-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c1acc-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c1acc-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c1acc-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c1acc-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c1acc-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c1acc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c1acc-108"> EDI</span></span> |
|    <span data-ttu-id="c1acc-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c1acc-109">Component</span></span>    |                                       <span data-ttu-id="c1acc-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c1acc-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c1acc-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c1acc-111">Symbolic Name</span></span>  |                      <span data-ttu-id="c1acc-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="c1acc-112">X12DeMandatoryDataElementMissingDescription</span></span>                       |
|  <span data-ttu-id="c1acc-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c1acc-113">Message Text</span></span>   |                             <span data-ttu-id="c1acc-114">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="c1acc-114">Mandatory data element missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="c1acc-115">説明</span><span class="sxs-lookup"><span data-stu-id="c1acc-115">Explanation</span></span>  
 <span data-ttu-id="c1acc-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) データ要素がインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c1acc-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c1acc-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c1acc-117">User Action</span></span>  
 <span data-ttu-id="c1acc-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのデータ要素がインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="c1acc-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>