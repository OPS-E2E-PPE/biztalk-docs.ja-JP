---
title: シングル サインオン:イベント 10653 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cfcc58ac3d16696e1d7c3ba3a103f1ecbdf3966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397659"
---
# <a name="single-sign-on-event-10653"></a><span data-ttu-id="69a6a-102">シングル サインオン:イベント 10653</span><span class="sxs-lookup"><span data-stu-id="69a6a-102">Single Sign-On: Event 10653</span></span>
## <a name="details"></a><span data-ttu-id="69a6a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="69a6a-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="69a6a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="69a6a-104">Product Name</span></span>   |                 <span data-ttu-id="69a6a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="69a6a-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="69a6a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="69a6a-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="69a6a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="69a6a-107">Event ID</span></span>     |                           <span data-ttu-id="69a6a-108">10653</span><span class="sxs-lookup"><span data-stu-id="69a6a-108">10653</span></span>                            |
|  <span data-ttu-id="69a6a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="69a6a-109">Event Source</span></span>   |                           <span data-ttu-id="69a6a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="69a6a-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="69a6a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="69a6a-111">Component</span></span>    |                            <span data-ttu-id="69a6a-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="69a6a-112">N\A</span></span>                             |
|  <span data-ttu-id="69a6a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="69a6a-113">Symbolic Name</span></span>  |        <span data-ttu-id="69a6a-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="69a6a-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="69a6a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="69a6a-115">Message Text</span></span>   |    <span data-ttu-id="69a6a-116">パスワード同期サーバー (アダプタ用) へのアクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="69a6a-116">Password sync server (for adapters) access denied.%r</span></span>    |

## <a name="explanation"></a><span data-ttu-id="69a6a-117">説明</span><span class="sxs-lookup"><span data-stu-id="69a6a-117">Explanation</span></span>  
 <span data-ttu-id="69a6a-118">このエラー イベントは、クライアントがサーバーに接続しようとしましたが、呼び出しが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="69a6a-118">This Error event indicates that a client attempted to contact the server but the call was refused.</span></span> <span data-ttu-id="69a6a-119">さまざまなプロトコルが正しくないかが不足しているセキュリティのアクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69a6a-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  

## <a name="user-action"></a><span data-ttu-id="69a6a-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="69a6a-120">User Action</span></span>  
 <span data-ttu-id="69a6a-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="69a6a-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="69a6a-122">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="69a6a-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="69a6a-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="69a6a-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="69a6a-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="69a6a-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
