---
title: インターチェンジに正しくない形式の ISA が含まれているか、サービス スキーマが利用できなかった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d285f6-26fb-4a3b-a959-a17623321b20
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce469b25a2ba15c3038ea9079c3f22fc4f8c0c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010715"
---
# <a name="the-interchange-contained-a-malformed-isa-or-the-service-schema-was-not-available"></a><span data-ttu-id="67bad-102">インターチェンジに正しくない形式の ISA が含まれていたか、サービス スキーマを使用できませんでした</span><span class="sxs-lookup"><span data-stu-id="67bad-102">The interchange contained a malformed ISA or the Service schema was not available</span></span>
## <a name="details"></a><span data-ttu-id="67bad-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67bad-103">Details</span></span>  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="67bad-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67bad-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| <span data-ttu-id="67bad-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67bad-105">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                             |
|    <span data-ttu-id="67bad-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67bad-106">Event ID</span></span>     |                                                         -                                                          |
|  <span data-ttu-id="67bad-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67bad-107">Event Source</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="67bad-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="67bad-108"> EDI</span></span>               |
|    <span data-ttu-id="67bad-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67bad-109">Component</span></span>    |                                                     <span data-ttu-id="67bad-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="67bad-110">EDI Engine</span></span>                                                     |
|  <span data-ttu-id="67bad-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67bad-111">Symbolic Name</span></span>  |                                                 <span data-ttu-id="67bad-112">MalformedIsaError</span><span class="sxs-lookup"><span data-stu-id="67bad-112">MalformedIsaError</span></span>                                                  |
|  <span data-ttu-id="67bad-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67bad-113">Message Text</span></span>   | <span data-ttu-id="67bad-114">インターチェンジに正しくない形式の ISA が含まれていたかサービス スキーマを使用できなかったため、このインターチェンジ全体が拒否されています</span><span class="sxs-lookup"><span data-stu-id="67bad-114">The interchange contained a malformed ISA or the Service schema was not available, it is being rejected completely</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="67bad-115">説明</span><span class="sxs-lookup"><span data-stu-id="67bad-115">Explanation</span></span>  
 <span data-ttu-id="67bad-116">このエラー/警告/情報イベントは、インターチェンジの ISA または IEA セグメントが X12ServiceSchema に準拠していなかったか、または (BaseArtifacts.dll 内の) X12ServiceSchema が展開されなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="67bad-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange, because the ISA or IEA segments in the interchange did not conform to the X12ServiceSchema, or the X12ServiceSchema (in BaseArtifacts.dll) was not deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67bad-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67bad-117">User Action</span></span>  
 <span data-ttu-id="67bad-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67bad-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="67bad-119">インターチェンジの送信者に対して、ISA および IEA セグメントを変更し、X12ServiceSchema に準拠させるように依頼します。</span><span class="sxs-lookup"><span data-stu-id="67bad-119">Have the sender of the interchange change the ISA and IEA segments so that they conform to the X12ServiceSchema.</span></span>  
  
-   <span data-ttu-id="67bad-120">BaseArtifacts.dll に X12ServiceSchema が含まれていることと、X12ServiceSchema が展開されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67bad-120">Ensure that BaseArtifacts.dll includes the X12ServiceSchema and is deployed.</span></span> <span data-ttu-id="67bad-121">そのためには、BizTalk Server 管理コンソールを開き、[BizTalk EDI アプリケーション] ノードの [スキーマ] ノードを開いて、X12ServiceSchema が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67bad-121">You can do so by opening the BizTalk Server Administration Console, opening the BizTalk EDI Application node and then the Schemas node, and verifying that X12ServiceSchema is listed.</span></span>