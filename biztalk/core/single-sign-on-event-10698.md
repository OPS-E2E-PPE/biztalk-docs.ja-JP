---
title: 'シングル サインオン: イベント 10698 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ca4d65927e7e9d01f7c73eb64a19bc613496f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270386"
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="d19fc-102">シングル サインオン: イベント 10698</span><span class="sxs-lookup"><span data-stu-id="d19fc-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="d19fc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d19fc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d19fc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d19fc-104">Product Name</span></span>|<span data-ttu-id="d19fc-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d19fc-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="d19fc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d19fc-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="d19fc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d19fc-107">Event ID</span></span>|<span data-ttu-id="d19fc-108">10698</span><span class="sxs-lookup"><span data-stu-id="d19fc-108">10698</span></span>|  
|<span data-ttu-id="d19fc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d19fc-109">Event Source</span></span>|<span data-ttu-id="d19fc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d19fc-110">ENTSSO</span></span>|  
|<span data-ttu-id="d19fc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d19fc-111">Component</span></span>|<span data-ttu-id="d19fc-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d19fc-112">N\A</span></span>|  
|<span data-ttu-id="d19fc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d19fc-113">Symbolic Name</span></span>|<span data-ttu-id="d19fc-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="d19fc-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>|  
|<span data-ttu-id="d19fc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d19fc-115">Message Text</span></span>|<span data-ttu-id="d19fc-116">再生ファイルまたは進行状況ファイルが削除されました。%r</span><span class="sxs-lookup"><span data-stu-id="d19fc-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="d19fc-117">ファイル名: %1</span><span class="sxs-lookup"><span data-stu-id="d19fc-117">File Name: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d19fc-118">説明</span><span class="sxs-lookup"><span data-stu-id="d19fc-118">Explanation</span></span>  
 <span data-ttu-id="d19fc-119">この情報イベントは、SSO が再生ファイルまたは進行状況ファイルを削除したことを示します。</span><span class="sxs-lookup"><span data-stu-id="d19fc-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  
  
 <span data-ttu-id="d19fc-120">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d19fc-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d19fc-121">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="d19fc-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d19fc-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d19fc-122">User Action</span></span>  
  
-   <span data-ttu-id="d19fc-123">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d19fc-123">No user action is necessary.</span></span>  
  
 <span data-ttu-id="d19fc-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="d19fc-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="d19fc-125">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d19fc-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="d19fc-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d19fc-126">Password Synchronization</span></span>](../core/password-synchronization2.md)