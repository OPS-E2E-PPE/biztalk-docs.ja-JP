---
title: 'シングル サインオン: イベント 10555 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a44b3c72659cec8295e7a6625e7b6d94259283c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000307"
---
# <a name="single-sign-on-event-10555"></a><span data-ttu-id="87ea9-102">シングル サインオン: イベント 10555</span><span class="sxs-lookup"><span data-stu-id="87ea9-102">Single Sign-On: Event 10555</span></span>
## <a name="details"></a><span data-ttu-id="87ea9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="87ea9-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="87ea9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="87ea9-104">Product Name</span></span>   |                 <span data-ttu-id="87ea9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="87ea9-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="87ea9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="87ea9-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="87ea9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="87ea9-107">Event ID</span></span>     |                           <span data-ttu-id="87ea9-108">10555</span><span class="sxs-lookup"><span data-stu-id="87ea9-108">10555</span></span>                            |
|  <span data-ttu-id="87ea9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="87ea9-109">Event Source</span></span>   |                           <span data-ttu-id="87ea9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="87ea9-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="87ea9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="87ea9-111">Component</span></span>    |                            <span data-ttu-id="87ea9-112">なし</span><span class="sxs-lookup"><span data-stu-id="87ea9-112">N/A</span></span>                             |
|  <span data-ttu-id="87ea9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="87ea9-113">Symbolic Name</span></span>  |          <span data-ttu-id="87ea9-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="87ea9-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span></span>           |
|  <span data-ttu-id="87ea9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="87ea9-115">Message Text</span></span>   | <span data-ttu-id="87ea9-116">シークレット サーバー アクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="87ea9-116">Secret server access denied.%r</span></span><br /><br /> <span data-ttu-id="87ea9-117">クライアント ユーザー: %1</span><span class="sxs-lookup"><span data-stu-id="87ea9-117">Client User: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="87ea9-118">説明</span><span class="sxs-lookup"><span data-stu-id="87ea9-118">Explanation</span></span>  
 <span data-ttu-id="87ea9-119">メッセージはサーバーに送信されましたが、応答はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="87ea9-119">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="87ea9-120">原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="87ea9-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87ea9-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="87ea9-121">User Action</span></span>  
 <span data-ttu-id="87ea9-122">エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="87ea9-122">Note the information in the error log and contact product support services.</span></span>