---
title: シングル サインオン:イベント 10714 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59d8509f-cc3e-40fa-ba3d-3dcb0e73c67a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 087592befd7f65241fdc413886f8245467f1e534
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397205"
---
# <a name="single-sign-on-event-10714"></a><span data-ttu-id="77f96-102">シングル サインオン:イベント 10714</span><span class="sxs-lookup"><span data-stu-id="77f96-102">Single Sign-On: Event 10714</span></span>
## <a name="details"></a><span data-ttu-id="77f96-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77f96-103">Details</span></span>  

|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="77f96-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77f96-104">Product Name</span></span>   |                                     <span data-ttu-id="77f96-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="77f96-105">Enterprise Single Sign-On</span></span>                                     |
| <span data-ttu-id="77f96-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77f96-106">Product Version</span></span> |                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                     |
|    <span data-ttu-id="77f96-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77f96-107">Event ID</span></span>     |                                               <span data-ttu-id="77f96-108">10714</span><span class="sxs-lookup"><span data-stu-id="77f96-108">10714</span></span>                                               |
|  <span data-ttu-id="77f96-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77f96-109">Event Source</span></span>   |                                              <span data-ttu-id="77f96-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77f96-110">ENTSSO</span></span>                                               |
|    <span data-ttu-id="77f96-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77f96-111">Component</span></span>    |                                                <span data-ttu-id="77f96-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="77f96-112">N\A</span></span>                                                |
|  <span data-ttu-id="77f96-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77f96-113">Symbolic Name</span></span>  |                             <span data-ttu-id="77f96-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="77f96-114">SSO_WARN_PS_NOTIFICATION_RETRIES_EXPIRED</span></span>                              |
|  <span data-ttu-id="77f96-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77f96-115">Message Text</span></span>   | <span data-ttu-id="77f96-116">再試行が期限切れ、notification.%r の破棄</span><span class="sxs-lookup"><span data-stu-id="77f96-116">Retries expired, discarding notification.%r</span></span><br /><br /> <span data-ttu-id="77f96-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="77f96-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="77f96-118">アダプタ: %2</span><span class="sxs-lookup"><span data-stu-id="77f96-118">Adapter: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="77f96-119">説明</span><span class="sxs-lookup"><span data-stu-id="77f96-119">Explanation</span></span>  
 <span data-ttu-id="77f96-120">この警告イベントは、パスワード同期通知の再試行が期限切れになり、通知が破棄されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="77f96-120">This Warning event indicates that the Password Sync notification retries have expired, and the notification has been discarded.</span></span>  

 <span data-ttu-id="77f96-121">(外部システムに Windows) からパスワードの変更は、パスワード同期アダプターに配信される、パスワード同期アダプターは、パスワードの変更が正常に処理されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="77f96-121">When a password change (from Windows to an external system) is delivered to a password sync adapter, the password sync adapter acknowledges that it has successfully processed the password change.</span></span> <span data-ttu-id="77f96-122">指定した時間内にパスワードの変更が存在しない場合、または変更時に別の問題が発生した場合は、パスワードの変更はもう一度、パスワード同期アダプターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="77f96-122">If the password change does not occur within a specified amount of time, or if another problem occurs during the change, the password change is delivered to the password sync adapter again.</span></span> <span data-ttu-id="77f96-123">これは、限られた回数 (最大試行回数) と、パスワード変更通知は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="77f96-123">This is done a limited number of times (max retries) and then the password change notification is discarded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="77f96-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77f96-124">User Action</span></span>  
 <span data-ttu-id="77f96-125">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="77f96-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="77f96-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="77f96-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="77f96-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77f96-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="77f96-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="77f96-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="77f96-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="77f96-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
