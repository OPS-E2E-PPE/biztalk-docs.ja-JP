---
title: 'シングル サインオン: イベント 10662 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe707f23-ad54-4adb-a755-8d706a75efa4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b941aa09b31f7e671625a7521843cd1059076da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270954"
---
# <a name="single-sign-on-event-10662"></a><span data-ttu-id="3090a-102">シングル サインオン: イベント 10662</span><span class="sxs-lookup"><span data-stu-id="3090a-102">Single Sign-On: Event 10662</span></span>
## <a name="details"></a><span data-ttu-id="3090a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3090a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3090a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3090a-104">Product Name</span></span>|<span data-ttu-id="3090a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3090a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3090a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3090a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3090a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3090a-107">Event ID</span></span>|<span data-ttu-id="3090a-108">10662</span><span class="sxs-lookup"><span data-stu-id="3090a-108">10662</span></span>|  
|<span data-ttu-id="3090a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3090a-109">Event Source</span></span>|<span data-ttu-id="3090a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3090a-110">ENTSSO</span></span>|  
|<span data-ttu-id="3090a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3090a-111">Component</span></span>|<span data-ttu-id="3090a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="3090a-112">N\A</span></span>|  
|<span data-ttu-id="3090a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3090a-113">Symbolic Name</span></span>|<span data-ttu-id="3090a-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="3090a-114">SSO_INFO_WINDOWS_PASSWORD_CHANGE_RECEIVED</span></span>|  
|<span data-ttu-id="3090a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3090a-115">Message Text</span></span>|<span data-ttu-id="3090a-116">PCNS から Windows パスワード変更を受信しました。%r</span><span class="sxs-lookup"><span data-stu-id="3090a-116">A Windows password change was received from PCNS.%r</span></span><br /><br /> <span data-ttu-id="3090a-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3090a-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3090a-118">Windows アカウント: %2 %r</span><span class="sxs-lookup"><span data-stu-id="3090a-118">Windows Account: %2%r</span></span><br /><br /> <span data-ttu-id="3090a-119">追加データ: %3 %r</span><span class="sxs-lookup"><span data-stu-id="3090a-119">Additional Data: %3%r</span></span><br /><br /> <span data-ttu-id="3090a-120">クライアント ユーザー: %4</span><span class="sxs-lookup"><span data-stu-id="3090a-120">Client User: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3090a-121">説明</span><span class="sxs-lookup"><span data-stu-id="3090a-121">Explanation</span></span>  
 <span data-ttu-id="3090a-122">この情報イベントは、Windows パスワードの変更をパスワード変更通知サービスから受け取ったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3090a-122">This Information event indicates that a Windows password change was received from Password Change Notification Services.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3090a-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3090a-123">User Action</span></span>  
  
-   <span data-ttu-id="3090a-124">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3090a-124">No user action is necessary.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="3090a-125">詳細</span><span class="sxs-lookup"><span data-stu-id="3090a-125">More info</span></span>
  
-   [<span data-ttu-id="3090a-126">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="3090a-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   <span data-ttu-id="3090a-127">**パスワード同期アダプターのプロパティ: オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3090a-127">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>