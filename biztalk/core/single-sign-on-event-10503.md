---
title: 'シングル サインオン: イベント 10503 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53c02388304fa9fab0b518517ba51b2db94412f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271114"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="df427-102">シングル サインオン: イベント 10503</span><span class="sxs-lookup"><span data-stu-id="df427-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="df427-103">詳細</span><span class="sxs-lookup"><span data-stu-id="df427-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df427-104">製品名</span><span class="sxs-lookup"><span data-stu-id="df427-104">Product Name</span></span>|<span data-ttu-id="df427-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="df427-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="df427-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="df427-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="df427-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="df427-107">Event ID</span></span>|<span data-ttu-id="df427-108">10503</span><span class="sxs-lookup"><span data-stu-id="df427-108">10503</span></span>|  
|<span data-ttu-id="df427-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="df427-109">Event Source</span></span>|<span data-ttu-id="df427-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="df427-110">ENTSSO</span></span>|  
|<span data-ttu-id="df427-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df427-111">Component</span></span>|<span data-ttu-id="df427-112">N\A</span><span class="sxs-lookup"><span data-stu-id="df427-112">N\A</span></span>|  
|<span data-ttu-id="df427-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="df427-113">Symbolic Name</span></span>|<span data-ttu-id="df427-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="df427-114">SSO_ERROR_SERVICE_START_FAILED</span></span>|  
|<span data-ttu-id="df427-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="df427-115">Message Text</span></span>|<span data-ttu-id="df427-116">SSO サービスを開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="df427-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="df427-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="df427-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="df427-118">説明</span><span class="sxs-lookup"><span data-stu-id="df427-118">Explanation</span></span>  
 <span data-ttu-id="df427-119">このエラー イベントは、例外が発生したために ENTSSO サービスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="df427-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="df427-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="df427-120">User Action</span></span>  
 <span data-ttu-id="df427-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="df427-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="df427-122">ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="df427-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="df427-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="df427-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="df427-124">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="df427-124">Using SSO</span></span>](../core/using-sso.md)