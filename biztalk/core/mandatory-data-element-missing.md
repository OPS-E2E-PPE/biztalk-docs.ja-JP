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
ms.openlocfilehash: 61911e53061b0c4ec84b73f533f85a868a0088aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65327625"
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="bf338-102">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="bf338-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="bf338-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bf338-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="bf338-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bf338-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="bf338-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bf338-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="bf338-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bf338-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="bf338-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bf338-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="bf338-108">EDI</span><span class="sxs-lookup"><span data-stu-id="bf338-108">EDI</span></span> |
|    <span data-ttu-id="bf338-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf338-109">Component</span></span>    |                                       <span data-ttu-id="bf338-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="bf338-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="bf338-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bf338-111">Symbolic Name</span></span>  |                      <span data-ttu-id="bf338-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="bf338-112">X12DeMandatoryDataElementMissingDescription</span></span>                       |
|  <span data-ttu-id="bf338-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bf338-113">Message Text</span></span>   |                             <span data-ttu-id="bf338-114">必須のデータ要素がありません</span><span class="sxs-lookup"><span data-stu-id="bf338-114">Mandatory data element missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="bf338-115">説明</span><span class="sxs-lookup"><span data-stu-id="bf338-115">Explanation</span></span>  
 <span data-ttu-id="bf338-116">このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) データ要素がインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf338-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bf338-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bf338-117">User Action</span></span>  
 <span data-ttu-id="bf338-118">このエラーを解決するには、メッセージ スキーマで要求されているすべてのデータ要素がインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="bf338-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>