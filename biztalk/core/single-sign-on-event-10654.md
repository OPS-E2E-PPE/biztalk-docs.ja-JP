---
title: シングル サインオン:イベント 10654 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703462b0d4988a60bc0d6fc6b11629fe3dbe0502
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397649"
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="fe7fb-102">シングル サインオン:イベント 10654</span><span class="sxs-lookup"><span data-stu-id="fe7fb-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="fe7fb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fe7fb-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="fe7fb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fe7fb-104">Product Name</span></span>   |                 <span data-ttu-id="fe7fb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fe7fb-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="fe7fb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fe7fb-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="fe7fb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fe7fb-107">Event ID</span></span>     |                           <span data-ttu-id="fe7fb-108">10654</span><span class="sxs-lookup"><span data-stu-id="fe7fb-108">10654</span></span>                            |
|  <span data-ttu-id="fe7fb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fe7fb-109">Event Source</span></span>   |                           <span data-ttu-id="fe7fb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fe7fb-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="fe7fb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fe7fb-111">Component</span></span>    |                            <span data-ttu-id="fe7fb-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="fe7fb-112">N\A</span></span>                             |
|  <span data-ttu-id="fe7fb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fe7fb-113">Symbolic Name</span></span>  |        <span data-ttu-id="fe7fb-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="fe7fb-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="fe7fb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fe7fb-115">Message Text</span></span>   |    <span data-ttu-id="fe7fb-116">パスワード同期サーバー (Windows) 用アクセス denied.%r</span><span class="sxs-lookup"><span data-stu-id="fe7fb-116">Password sync server (for Windows) access denied.%r</span></span>     |

## <a name="explanation"></a><span data-ttu-id="fe7fb-117">説明</span><span class="sxs-lookup"><span data-stu-id="fe7fb-117">Explanation</span></span>  
 <span data-ttu-id="fe7fb-118">このエラー イベントは、[名前] サーバーにメッセージが送信されましたが、応答がブロックされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="fe7fb-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="fe7fb-119">さまざまなプロトコルが正しくないやサーバー上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe7fb-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fe7fb-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fe7fb-120">User Action</span></span>  
 <span data-ttu-id="fe7fb-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fe7fb-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="fe7fb-122">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="fe7fb-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="fe7fb-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="fe7fb-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="fe7fb-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="fe7fb-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
