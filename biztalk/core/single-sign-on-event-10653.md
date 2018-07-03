---
title: 'シングル サインオン: イベント 10653 |Microsoft Docs'
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
ms.openlocfilehash: a9f0edb3ce5fa7f8fb59c4b65914a9c8b6640adc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969459"
---
# <a name="single-sign-on-event-10653"></a><span data-ttu-id="2c4a6-102">シングル サインオン: イベント 10653</span><span class="sxs-lookup"><span data-stu-id="2c4a6-102">Single Sign-On: Event 10653</span></span>
## <a name="details"></a><span data-ttu-id="2c4a6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2c4a6-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="2c4a6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2c4a6-104">Product Name</span></span>   |                 <span data-ttu-id="2c4a6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2c4a6-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="2c4a6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2c4a6-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="2c4a6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2c4a6-107">Event ID</span></span>     |                           <span data-ttu-id="2c4a6-108">10653</span><span class="sxs-lookup"><span data-stu-id="2c4a6-108">10653</span></span>                            |
|  <span data-ttu-id="2c4a6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2c4a6-109">Event Source</span></span>   |                           <span data-ttu-id="2c4a6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2c4a6-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="2c4a6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2c4a6-111">Component</span></span>    |                            <span data-ttu-id="2c4a6-112">N\A</span><span class="sxs-lookup"><span data-stu-id="2c4a6-112">N\A</span></span>                             |
|  <span data-ttu-id="2c4a6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2c4a6-113">Symbolic Name</span></span>  |        <span data-ttu-id="2c4a6-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="2c4a6-114">SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED</span></span>         |
|  <span data-ttu-id="2c4a6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2c4a6-115">Message Text</span></span>   |    <span data-ttu-id="2c4a6-116">パスワード同期サーバーへの (アダプターの) アクセスは拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="2c4a6-116">Password sync server (for adapters) access denied.%r</span></span>    |

## <a name="explanation"></a><span data-ttu-id="2c4a6-117">説明</span><span class="sxs-lookup"><span data-stu-id="2c4a6-117">Explanation</span></span>  
 <span data-ttu-id="2c4a6-118">このエラー イベントは、クライアントがサーバーに接続しようとしたが、呼び出しが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="2c4a6-118">This Error event indicates that a client attempted to contact the server but the call was refused.</span></span> <span data-ttu-id="2c4a6-119">原因として、プロトコルが正しくない、セキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。</span><span class="sxs-lookup"><span data-stu-id="2c4a6-119">This can be caused by a number of different reasons, such as incorrect protocol or insufficient security permissions.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2c4a6-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2c4a6-120">User Action</span></span>  
 <span data-ttu-id="2c4a6-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2c4a6-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="2c4a6-122">このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="2c4a6-122">Note the information in this message, and any relevant information in the event log, and contact Microsoft Product Support Services.</span></span>  

  <span data-ttu-id="2c4a6-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="2c4a6-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="2c4a6-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="2c4a6-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
