---
title: 'シングル サインオン: イベント 10749 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baf82eb2fc8312874947af3c035dc13bb8e39a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010977"
---
# <a name="single-sign-on-event-10749"></a><span data-ttu-id="9047a-102">シングル サインオン: イベント 10749</span><span class="sxs-lookup"><span data-stu-id="9047a-102">Single Sign-On: Event 10749</span></span>
## <a name="details"></a><span data-ttu-id="9047a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9047a-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9047a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9047a-104">Product Name</span></span>   |                                                                                                                      <span data-ttu-id="9047a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9047a-105">Enterprise Single Sign-On</span></span>                                                                                                                      |
| <span data-ttu-id="9047a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9047a-106">Product Version</span></span> |                                                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                      |
|    <span data-ttu-id="9047a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9047a-107">Event ID</span></span>     |                                                                                                                                <span data-ttu-id="9047a-108">10749</span><span class="sxs-lookup"><span data-stu-id="9047a-108">10749</span></span>                                                                                                                                |
|  <span data-ttu-id="9047a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9047a-109">Event Source</span></span>   |                                                                                                                               <span data-ttu-id="9047a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9047a-110">ENTSSO</span></span>                                                                                                                                |
|    <span data-ttu-id="9047a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9047a-111">Component</span></span>    |                                                                                                                                 <span data-ttu-id="9047a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="9047a-112">N\A</span></span>                                                                                                                                 |
|  <span data-ttu-id="9047a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9047a-113">Symbolic Name</span></span>  |                                                                                                                       <span data-ttu-id="9047a-114">SSO_WARN_PS_CLIENT_PING</span><span class="sxs-lookup"><span data-stu-id="9047a-114">SSO_WARN_PS_CLIENT_PING</span></span>                                                                                                                       |
|  <span data-ttu-id="9047a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9047a-115">Message Text</span></span>   | <span data-ttu-id="9047a-116">接続先 SSO サーバーに接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="9047a-116">Could not contact the destination SSO server.</span></span><br /><br /> <span data-ttu-id="9047a-117">サーバー上で SSO サービスが実行されており、サーバーに接続できることを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="9047a-117">Check that the SSO service is running on that server and that it can be contacted.%r</span></span><br /><br /> <span data-ttu-id="9047a-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9047a-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9047a-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="9047a-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="9047a-120">SSO サーバー名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="9047a-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="9047a-121">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="9047a-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="9047a-122">説明</span><span class="sxs-lookup"><span data-stu-id="9047a-122">Explanation</span></span>  
 <span data-ttu-id="9047a-123">この警告イベントは、SSO パスワード同期で、指定された接続先 SSO サーバーに接続できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="9047a-123">This Warning event indicates that SSO Password Sync could not contact the specified destination SSO server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9047a-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9047a-124">User Action</span></span>  
 <span data-ttu-id="9047a-125">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="9047a-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="9047a-126">ENTSSO サーバー スナップインを使用してサーバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9047a-126">Use the ENTSSO Servers Snap-In to check the server.</span></span>  

- <span data-ttu-id="9047a-127">エンタープライズ シングル サインオン サービスが実行されていない場合は、起動します。</span><span class="sxs-lookup"><span data-stu-id="9047a-127">Start the Enterprise Single Sign-On Service if it is not running.</span></span>  

- <span data-ttu-id="9047a-128">接続先 SSO サーバーへのネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="9047a-128">Check the network connection to the destination SSO server.</span></span>  

- <span data-ttu-id="9047a-129">接続先 SSO サーバー上のファイアウォールを確認します。</span><span class="sxs-lookup"><span data-stu-id="9047a-129">Check firewall on the destination SSO Server.</span></span>  

  <span data-ttu-id="9047a-130">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9047a-130">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="9047a-131">サーバー スナップインを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9047a-131">How to Use the Servers Snap-in</span></span>](../core/how-to-use-the-servers-snap-in.md)
