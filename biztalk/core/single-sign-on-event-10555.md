---
title: 'シングル サインオン: イベント 10555 |Microsoft ドキュメント'
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
ms.openlocfilehash: a22cf26269a661673008a715fe0bfb2a442f30b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270330"
---
# <a name="single-sign-on-event-10555"></a><span data-ttu-id="d08ab-102">シングル サインオン: イベント 10555</span><span class="sxs-lookup"><span data-stu-id="d08ab-102">Single Sign-On: Event 10555</span></span>
## <a name="details"></a><span data-ttu-id="d08ab-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d08ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d08ab-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d08ab-104">Product Name</span></span>|<span data-ttu-id="d08ab-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d08ab-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d08ab-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d08ab-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d08ab-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d08ab-107">Event ID</span></span>|<span data-ttu-id="d08ab-108">10555</span><span class="sxs-lookup"><span data-stu-id="d08ab-108">10555</span></span>|  
|<span data-ttu-id="d08ab-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d08ab-109">Event Source</span></span>|<span data-ttu-id="d08ab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d08ab-110">ENTSSO</span></span>|  
|<span data-ttu-id="d08ab-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d08ab-111">Component</span></span>|<span data-ttu-id="d08ab-112">なし</span><span class="sxs-lookup"><span data-stu-id="d08ab-112">N/A</span></span>|  
|<span data-ttu-id="d08ab-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d08ab-113">Symbolic Name</span></span>|<span data-ttu-id="d08ab-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="d08ab-114">SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED</span></span>|  
|<span data-ttu-id="d08ab-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d08ab-115">Message Text</span></span>|<span data-ttu-id="d08ab-116">シークレット サーバー アクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="d08ab-116">Secret server access denied.%r</span></span><br /><br /> <span data-ttu-id="d08ab-117">クライアント ユーザー: %1</span><span class="sxs-lookup"><span data-stu-id="d08ab-117">Client User: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d08ab-118">説明</span><span class="sxs-lookup"><span data-stu-id="d08ab-118">Explanation</span></span>  
 <span data-ttu-id="d08ab-119">メッセージはサーバーに送信されましたが、応答はブロックされました。</span><span class="sxs-lookup"><span data-stu-id="d08ab-119">A message was sent to the server but the reply was blocked.</span></span> <span data-ttu-id="d08ab-120">原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="d08ab-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d08ab-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d08ab-121">User Action</span></span>  
 <span data-ttu-id="d08ab-122">エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="d08ab-122">Note the information in the error log and contact product support services.</span></span>