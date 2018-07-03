---
title: 'シングル サインオン: イベント 10552 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f85ae0b3-d8f8-4341-8bd3-423e85402d58
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4f78ce40f827e6c06e59e1382aba8faac0337f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001211"
---
# <a name="single-sign-on-event-10552"></a><span data-ttu-id="db903-102">シングル サインオン: イベント 10552</span><span class="sxs-lookup"><span data-stu-id="db903-102">Single Sign-On: Event 10552</span></span>
## <a name="details"></a><span data-ttu-id="db903-103">詳細</span><span class="sxs-lookup"><span data-stu-id="db903-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="db903-104">製品名</span><span class="sxs-lookup"><span data-stu-id="db903-104">Product Name</span></span>   |                 <span data-ttu-id="db903-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="db903-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="db903-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="db903-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="db903-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="db903-107">Event ID</span></span>     |                           <span data-ttu-id="db903-108">10552</span><span class="sxs-lookup"><span data-stu-id="db903-108">10552</span></span>                            |
|  <span data-ttu-id="db903-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="db903-109">Event Source</span></span>   |                           <span data-ttu-id="db903-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="db903-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="db903-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="db903-111">Component</span></span>    |                            <span data-ttu-id="db903-112">なし</span><span class="sxs-lookup"><span data-stu-id="db903-112">N/A</span></span>                             |
|  <span data-ttu-id="db903-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="db903-113">Symbolic Name</span></span>  |          <span data-ttu-id="db903-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="db903-114">SSO_ERROR_MAPPING_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="db903-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="db903-115">Message Text</span></span>   |              <span data-ttu-id="db903-116">マッピング サーバーのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="db903-116">Mapping server access denied.%r</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="db903-117">説明</span><span class="sxs-lookup"><span data-stu-id="db903-117">Explanation</span></span>  
 <span data-ttu-id="db903-118">クライアントがマッピング サーバーを呼び出しましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="db903-118">A call was made from a client to the mapping server but was not accepted.</span></span> <span data-ttu-id="db903-119">原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="db903-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the client.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db903-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="db903-120">User Action</span></span>  
 <span data-ttu-id="db903-121">エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="db903-121">Note the information in the error log and contact product support services.</span></span>