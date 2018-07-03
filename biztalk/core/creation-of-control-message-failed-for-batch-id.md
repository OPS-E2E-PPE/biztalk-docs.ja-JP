---
title: バッチ id に対する制御メッセージの作成に失敗しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f03078e7-46b0-4082-9d66-6b892152a12d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba63bc570ac29f95c70b5bc6e09050e26c435b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979803"
---
# <a name="creation-of-control-message-failed-for-batch-id"></a><span data-ttu-id="357ce-102">バッチ ID に対する制御メッセージの作成が失敗しました</span><span class="sxs-lookup"><span data-stu-id="357ce-102">Creation of Control Message failed for Batch id</span></span>
## <a name="details"></a><span data-ttu-id="357ce-103">詳細</span><span class="sxs-lookup"><span data-stu-id="357ce-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="357ce-104">製品名</span><span class="sxs-lookup"><span data-stu-id="357ce-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="357ce-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="357ce-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="357ce-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="357ce-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="357ce-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="357ce-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="357ce-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="357ce-108"> EDI</span></span> |
|    <span data-ttu-id="357ce-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="357ce-109">Component</span></span>    |                                       <span data-ttu-id="357ce-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="357ce-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="357ce-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="357ce-111">Symbolic Name</span></span>  |                               <span data-ttu-id="357ce-112">CreateControlMessageFailed</span><span class="sxs-lookup"><span data-stu-id="357ce-112">CreateControlMessageFailed</span></span>                               |
|  <span data-ttu-id="357ce-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="357ce-113">Message Text</span></span>   |                  <span data-ttu-id="357ce-114">バッチ id に対する制御メッセージの作成に失敗しました{0}します。</span><span class="sxs-lookup"><span data-stu-id="357ce-114">Creation of Control Message failed for Batch id {0}.</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="357ce-115">説明</span><span class="sxs-lookup"><span data-stu-id="357ce-115">Explanation</span></span>  
 <span data-ttu-id="357ce-116">このエラー/警告/情報イベントは、BizTalk Server がバッチを開始/停止できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="357ce-116">This Error/Warning/Information event indicates BizTalk Server was start/stop a batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="357ce-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="357ce-117">User Action</span></span>  
 <span data-ttu-id="357ce-118">このエラーを解決するには、指定された ID のバッチが親アグリーメントの [アグリーメントのプロパティ] に存在し、データベースが起動していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="357ce-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and the database is up.</span></span>