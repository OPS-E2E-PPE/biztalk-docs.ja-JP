---
title: 'シングル サインオン: イベント 10654 |Microsoft Docs'
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
ms.openlocfilehash: 6ca59040b340d033ab6c355c0440378f09d87000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974483"
---
# <a name="single-sign-on-event-10654"></a><span data-ttu-id="657ae-102">シングル サインオン: イベント 10654</span><span class="sxs-lookup"><span data-stu-id="657ae-102">Single Sign-On: Event 10654</span></span>
## <a name="details"></a><span data-ttu-id="657ae-103">詳細</span><span class="sxs-lookup"><span data-stu-id="657ae-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="657ae-104">製品名</span><span class="sxs-lookup"><span data-stu-id="657ae-104">Product Name</span></span>   |                 <span data-ttu-id="657ae-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="657ae-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="657ae-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="657ae-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="657ae-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="657ae-107">Event ID</span></span>     |                           <span data-ttu-id="657ae-108">10654</span><span class="sxs-lookup"><span data-stu-id="657ae-108">10654</span></span>                            |
|  <span data-ttu-id="657ae-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="657ae-109">Event Source</span></span>   |                           <span data-ttu-id="657ae-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="657ae-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="657ae-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="657ae-111">Component</span></span>    |                            <span data-ttu-id="657ae-112">N\A</span><span class="sxs-lookup"><span data-stu-id="657ae-112">N\A</span></span>                             |
|  <span data-ttu-id="657ae-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="657ae-113">Symbolic Name</span></span>  |        <span data-ttu-id="657ae-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="657ae-114">SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="657ae-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="657ae-115">Message Text</span></span>   |    <span data-ttu-id="657ae-116">パスワード同期サーバーへの (Windows の) アクセスは拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="657ae-116">Password sync server (for Windows) access denied.%r</span></span>     |

## <a name="explanation"></a><span data-ttu-id="657ae-117">説明</span><span class="sxs-lookup"><span data-stu-id="657ae-117">Explanation</span></span>  
 <span data-ttu-id="657ae-118">このエラー イベントは、メッセージが [名前] サーバーに送信されたが、応答がブロックされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="657ae-118">This Error event indicates that a message was sent to the [name] server but the reply was blocked.</span></span> <span data-ttu-id="657ae-119">原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="657ae-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions on the server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="657ae-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="657ae-120">User Action</span></span>  
 <span data-ttu-id="657ae-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="657ae-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="657ae-122">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="657ae-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="657ae-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="657ae-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="657ae-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="657ae-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
