---
title: "バッチ id に対する制御メッセージの作成に失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a5650ab649e9b0957e64f3cdecc13c725d64536
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="057b5-102">バッチ ID に対する制御メッセージの作成が失敗しました</span><span class="sxs-lookup"><span data-stu-id="057b5-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="057b5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="057b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="057b5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="057b5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="057b5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="057b5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="057b5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="057b5-106">Event ID</span></span>|-|  
|<span data-ttu-id="057b5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="057b5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="057b5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="057b5-108"> EDI</span></span>|  
|<span data-ttu-id="057b5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="057b5-109">Component</span></span>|<span data-ttu-id="057b5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="057b5-110">EDI Engine</span></span>|  
|<span data-ttu-id="057b5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="057b5-111">Symbolic Name</span></span>|<span data-ttu-id="057b5-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="057b5-112">CreateControlMessageFailed</span></span>|  
|<span data-ttu-id="057b5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="057b5-113">Message Text</span></span>|<span data-ttu-id="057b5-114">バッチ ID {0} に対する制御メッセージの作成が失敗しました。</span><span class="sxs-lookup"><span data-stu-id="057b5-114">Creation of Control Message failed for Batch id {0}.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="057b5-115">説明</span><span class="sxs-lookup"><span data-stu-id="057b5-115">Explanation</span></span>  
 <span data-ttu-id="057b5-116">このエラー/警告/情報イベントは、BizTalk Server がバッチを開始/停止できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="057b5-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="057b5-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="057b5-117">User Action</span></span>  
 <span data-ttu-id="057b5-118">このエラーを解決するには、指定された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に存在し、データベースが起動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="057b5-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>