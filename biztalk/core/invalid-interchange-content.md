---
title: 無効なインターチェンジの内容 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b2352c3-d233-4d79-be31-b32dde29c8ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 320715ee685b60284d710510521fc7599db22f87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381276"
---
# <a name="invalid-interchange-content"></a><span data-ttu-id="04de8-102">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="04de8-102">Invalid Interchange Content</span></span>
## <a name="details"></a><span data-ttu-id="04de8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="04de8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="04de8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="04de8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="04de8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="04de8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="04de8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04de8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="04de8-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="04de8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="04de8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="04de8-108">EDI</span></span> |
|    <span data-ttu-id="04de8-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="04de8-109">Component</span></span>    |                                       <span data-ttu-id="04de8-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="04de8-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="04de8-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="04de8-111">Symbolic Name</span></span>  |                       <span data-ttu-id="04de8-112">X12Ta1InvalidInterchangeContentDescription</span><span class="sxs-lookup"><span data-stu-id="04de8-112">X12Ta1InvalidInterchangeContentDescription</span></span>                       |
|  <span data-ttu-id="04de8-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="04de8-113">Message Text</span></span>   |                              <span data-ttu-id="04de8-114">インターチェンジの内容が無効です。</span><span class="sxs-lookup"><span data-stu-id="04de8-114">Invalid Interchange Content</span></span>                               |
  
## <a name="explanation"></a><span data-ttu-id="04de8-115">説明</span><span class="sxs-lookup"><span data-stu-id="04de8-115">Explanation</span></span>  
 <span data-ttu-id="04de8-116">このエラー/警告/情報イベントは、インターチェンジのデータが、BizTalk Server によって実行されるメッセージの検証に失敗したため、受信パイプラインで受信インターチェンジを処理できなかったか、または送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="04de8-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the data in the interchange did not pass message validation performed by BizTalk Server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04de8-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="04de8-117">User Action</span></span>  
 <span data-ttu-id="04de8-118">このエラーを解決するには、検証に失敗したインターチェンジの部分と、失敗した検証を確認します。</span><span class="sxs-lookup"><span data-stu-id="04de8-118">To resolve this error, identify which part of the interchange failed validation, and which validation it failed.</span></span> <span data-ttu-id="04de8-119">検証に失敗した問題を解決して、インターチェンジを再送信してもらいます。</span><span class="sxs-lookup"><span data-stu-id="04de8-119">Resolve the issue that caused validation to fail, and then have the interchange resent.</span></span>