---
title: 'シングル サインオン: イベント 10600 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cab2c98-d576-488c-aba5-093b34489bb7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86a4bf3671da5b49e981a652d311136a9ae5c0eb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972051"
---
# <a name="single-sign-on-event-10600"></a><span data-ttu-id="9d78b-102">シングル サインオン: イベント 10600</span><span class="sxs-lookup"><span data-stu-id="9d78b-102">Single Sign-On: Event 10600</span></span>
## <a name="details"></a><span data-ttu-id="9d78b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9d78b-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="9d78b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9d78b-104">Product Name</span></span>   |                 <span data-ttu-id="9d78b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9d78b-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="9d78b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9d78b-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="9d78b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9d78b-107">Event ID</span></span>     |                           <span data-ttu-id="9d78b-108">10600</span><span class="sxs-lookup"><span data-stu-id="9d78b-108">10600</span></span>                            |
|  <span data-ttu-id="9d78b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9d78b-109">Event Source</span></span>   |                           <span data-ttu-id="9d78b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9d78b-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="9d78b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9d78b-111">Component</span></span>    |                            <span data-ttu-id="9d78b-112">なし</span><span class="sxs-lookup"><span data-stu-id="9d78b-112">N/A</span></span>                             |
|  <span data-ttu-id="9d78b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9d78b-113">Symbolic Name</span></span>  |            <span data-ttu-id="9d78b-114">SSO_ERROR_CS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="9d78b-114">SSO_ERROR_CS_CALLBACK_ACCESS_DENIED</span></span>             |
|  <span data-ttu-id="9d78b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9d78b-115">Message Text</span></span>   |            <span data-ttu-id="9d78b-116">構成ストア サーバーへのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="9d78b-116">Config Store server access denied.%r</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="9d78b-117">説明</span><span class="sxs-lookup"><span data-stu-id="9d78b-117">Explanation</span></span>  
 <span data-ttu-id="9d78b-118">構成ストア サーバーに対してメッセージが送信されましたが、受け付けられませんでした。</span><span class="sxs-lookup"><span data-stu-id="9d78b-118">A message was sent to the Config Store server but was not accepted.</span></span> <span data-ttu-id="9d78b-119">原因として、プロトコルが正しくない、セキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="9d78b-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d78b-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9d78b-120">User Action</span></span>  
 <span data-ttu-id="9d78b-121">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="9d78b-121">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>