---
title: 'シングル サインオン: イベント 10652 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62066b2fbbc47d07fa57f047313ed5ed8cda47d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270914"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="be5ab-102">シングル サインオン: イベント 10652</span><span class="sxs-lookup"><span data-stu-id="be5ab-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="be5ab-103">詳細</span><span class="sxs-lookup"><span data-stu-id="be5ab-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be5ab-104">製品名</span><span class="sxs-lookup"><span data-stu-id="be5ab-104">Product Name</span></span>|<span data-ttu-id="be5ab-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="be5ab-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="be5ab-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="be5ab-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="be5ab-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="be5ab-107">Event ID</span></span>|<span data-ttu-id="be5ab-108">10652</span><span class="sxs-lookup"><span data-stu-id="be5ab-108">10652</span></span>|  
|<span data-ttu-id="be5ab-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="be5ab-109">Event Source</span></span>|<span data-ttu-id="be5ab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="be5ab-110">ENTSSO</span></span>|  
|<span data-ttu-id="be5ab-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be5ab-111">Component</span></span>|<span data-ttu-id="be5ab-112">N\A</span><span class="sxs-lookup"><span data-stu-id="be5ab-112">N\A</span></span>|  
|<span data-ttu-id="be5ab-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="be5ab-113">Symbolic Name</span></span>|<span data-ttu-id="be5ab-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="be5ab-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>|  
|<span data-ttu-id="be5ab-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="be5ab-115">Message Text</span></span>|<span data-ttu-id="be5ab-116">パスワード同期サービスを初期化できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="be5ab-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="be5ab-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="be5ab-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="be5ab-118">説明</span><span class="sxs-lookup"><span data-stu-id="be5ab-118">Explanation</span></span>  
 <span data-ttu-id="be5ab-119">このエラー イベントは、例外が発生したためにパスワード同期サービスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="be5ab-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be5ab-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="be5ab-120">User Action</span></span>  
 <span data-ttu-id="be5ab-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be5ab-121">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="be5ab-122">ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="be5ab-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="be5ab-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="be5ab-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="be5ab-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="be5ab-124">Password Synchronization</span></span>](../core/password-synchronization2.md)