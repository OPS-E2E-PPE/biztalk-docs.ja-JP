---
title: シングル サインオン:イベント 10655 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d357eaf5433823f8b21f6d6a6757f06c59bdbd9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397637"
---
# <a name="single-sign-on-event-10655"></a><span data-ttu-id="bf877-102">シングル サインオン:イベント 10655</span><span class="sxs-lookup"><span data-stu-id="bf877-102">Single Sign-On: Event 10655</span></span>
## <a name="details"></a><span data-ttu-id="bf877-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bf877-103">Details</span></span>  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  <span data-ttu-id="bf877-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bf877-104">Product Name</span></span>   |                          <span data-ttu-id="bf877-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bf877-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="bf877-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bf877-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    <span data-ttu-id="bf877-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bf877-107">Event ID</span></span>     |                                    <span data-ttu-id="bf877-108">10655</span><span class="sxs-lookup"><span data-stu-id="bf877-108">10655</span></span>                                     |
|  <span data-ttu-id="bf877-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bf877-109">Event Source</span></span>   |                                    <span data-ttu-id="bf877-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bf877-110">ENTSSO</span></span>                                    |
|    <span data-ttu-id="bf877-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bf877-111">Component</span></span>    |                                     <span data-ttu-id="bf877-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="bf877-112">N\A</span></span>                                      |
|  <span data-ttu-id="bf877-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bf877-113">Symbolic Name</span></span>  |                   <span data-ttu-id="bf877-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="bf877-114">SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED</span></span>                   |
|  <span data-ttu-id="bf877-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bf877-115">Message Text</span></span>   | <span data-ttu-id="bf877-116">パスワード同期サーバー (ping) 用アクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="bf877-116">Password sync server (for ping) access denied.%r</span></span><br /><br /> <span data-ttu-id="bf877-117">クライアント ユーザー: %1</span><span class="sxs-lookup"><span data-stu-id="bf877-117">Client User: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="bf877-118">説明</span><span class="sxs-lookup"><span data-stu-id="bf877-118">Explanation</span></span>  
 <span data-ttu-id="bf877-119">このエラー イベントは、[名前] サーバーにメッセージが送信されましたが、応答がブロックされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="bf877-119">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="bf877-120">さまざまなプロトコルが正しくないやサーバー上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf877-120">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bf877-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bf877-121">User Action</span></span>  
 <span data-ttu-id="bf877-122">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bf877-122">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="bf877-123">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="bf877-123">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="bf877-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="bf877-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bf877-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="bf877-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
