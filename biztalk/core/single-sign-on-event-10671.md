---
title: シングル サインオン:イベント 10671 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06c5564f-6412-4e83-9bec-03264e992ebe
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84f3b434cc328b9356e3f5a7db380c92366c210c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397511"
---
# <a name="single-sign-on-event-10671"></a><span data-ttu-id="380bc-102">シングル サインオン:イベント 10671</span><span class="sxs-lookup"><span data-stu-id="380bc-102">Single Sign-On: Event 10671</span></span>
## <a name="details"></a><span data-ttu-id="380bc-103">詳細</span><span class="sxs-lookup"><span data-stu-id="380bc-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="380bc-104">製品名</span><span class="sxs-lookup"><span data-stu-id="380bc-104">Product Name</span></span>   |                                                                                                                                                                                  <span data-ttu-id="380bc-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="380bc-105">Enterprise Single Sign-On</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="380bc-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="380bc-106">Product Version</span></span> |                                                                                                                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                  |
|    <span data-ttu-id="380bc-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="380bc-107">Event ID</span></span>     |                                                                                                                                                                                            <span data-ttu-id="380bc-108">10671</span><span class="sxs-lookup"><span data-stu-id="380bc-108">10671</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="380bc-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="380bc-109">Event Source</span></span>   |                                                                                                                                                                                           <span data-ttu-id="380bc-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="380bc-110">ENTSSO</span></span>                                                                                                                                                                                            |
|    <span data-ttu-id="380bc-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="380bc-111">Component</span></span>    |                                                                                                                                                                                             <span data-ttu-id="380bc-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="380bc-112">N\A</span></span>                                                                                                                                                                                             |
|  <span data-ttu-id="380bc-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="380bc-113">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="380bc-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="380bc-114">SSO_INFO_EXTERNAL_MAPPING_CONFLICT_ALLOWED</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="380bc-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="380bc-115">Message Text</span></span>   | <span data-ttu-id="380bc-116">Windows パスワードの変更と同じ外部 system.%r では、複数のアカウントへの変更を、します。</span><span class="sxs-lookup"><span data-stu-id="380bc-116">A Windows password change will cause changes to more than one account on the same external system.%r</span></span><br /><br /> <span data-ttu-id="380bc-117">この外部システムのアダプタで構成されているマッピング conflicts.%r を許可するため、これは許可します。</span><span class="sxs-lookup"><span data-stu-id="380bc-117">This is allowed because the adapter for this external system is configured to allow mapping conflicts.%r</span></span><br /><br /> <span data-ttu-id="380bc-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="380bc-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="380bc-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="380bc-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="380bc-120">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="380bc-120">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="380bc-121">外部アカウント 1: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="380bc-121">External Account 1: %4%r</span></span><br /><br /> <span data-ttu-id="380bc-122">外部アカウント 2: %5</span><span class="sxs-lookup"><span data-stu-id="380bc-122">External Account 2: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="380bc-123">説明</span><span class="sxs-lookup"><span data-stu-id="380bc-123">Explanation</span></span>  
 <span data-ttu-id="380bc-124">この情報イベントでは、Windows パスワードの変更が、同じ外部システムでは、複数のアカウントへの変更を発生はことを示します。</span><span class="sxs-lookup"><span data-stu-id="380bc-124">This Information event indicates that a Windows password change will cause changes to more than one account on the same external system.</span></span>  

## <a name="user-action"></a><span data-ttu-id="380bc-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="380bc-125">User Action</span></span>  

-   <span data-ttu-id="380bc-126">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="380bc-126">No user action is necessary.</span></span>  

## <a name="more-info"></a><span data-ttu-id="380bc-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="380bc-127">More info</span></span>

- <span data-ttu-id="380bc-128">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="380bc-128">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="380bc-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="380bc-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
