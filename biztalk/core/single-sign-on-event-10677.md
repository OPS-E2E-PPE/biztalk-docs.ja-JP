---
title: シングル サインオン:イベント 10677 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2894792b-e1c9-4c24-875d-9193cbb5cd35
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54aeeca39a0efc16b10c7054aeafe5788c6e76af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397453"
---
# <a name="single-sign-on-event-10677"></a><span data-ttu-id="9c7df-102">シングル サインオン:イベント 10677</span><span class="sxs-lookup"><span data-stu-id="9c7df-102">Single Sign-On: Event 10677</span></span>
## <a name="details"></a><span data-ttu-id="9c7df-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9c7df-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c7df-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9c7df-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="9c7df-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9c7df-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="9c7df-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9c7df-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="9c7df-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9c7df-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="9c7df-108">10677</span><span class="sxs-lookup"><span data-stu-id="9c7df-108">10677</span></span>                                                                                                                               |
|  <span data-ttu-id="9c7df-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9c7df-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="9c7df-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9c7df-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="9c7df-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9c7df-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="9c7df-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="9c7df-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="9c7df-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9c7df-113">Symbolic Name</span></span>  |                                                                                                                  <span data-ttu-id="9c7df-114">SSO_WARN_NO_EXISTING_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="9c7df-114">SSO_WARN_NO_EXISTING_PASSWORD</span></span>                                                                                                                   |
|  <span data-ttu-id="9c7df-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9c7df-115">Message Text</span></span>   | <span data-ttu-id="9c7df-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="9c7df-116">External password change.</span></span> <span data-ttu-id="9c7df-117">この外部 account.%r の既存の資格情報がないために、古いパスワードを検証できません。</span><span class="sxs-lookup"><span data-stu-id="9c7df-117">The old password cannot be verified because there are no existing credentials for this external account.%r</span></span><br /><br /> <span data-ttu-id="9c7df-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9c7df-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9c7df-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="9c7df-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="9c7df-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="9c7df-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="9c7df-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="9c7df-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="9c7df-122">説明</span><span class="sxs-lookup"><span data-stu-id="9c7df-122">Explanation</span></span>  
 <span data-ttu-id="9c7df-123">この警告イベントは、古いパスワードに既存の資格情報があるないため、外部パスワード変更が発生することはできませんを示します。</span><span class="sxs-lookup"><span data-stu-id="9c7df-123">This Warning event indicates that an external password change cannot occur because the old password does not have existing credentials.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9c7df-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9c7df-124">User Action</span></span>  
 <span data-ttu-id="9c7df-125">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c7df-125">To resolve this warning, do one or more of the following:</span></span>  

-   <span data-ttu-id="9c7df-126">アダプター (イベント ログ メッセージ名) に割り当てられているどのアプリケーションを決定し、SSO 管理ツールを使用して、この外部アカウントの外部資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="9c7df-126">Determine which Applications were assigned to this Adapter (name in event log message) and then use the SSO administration tools to set the external credentials for this external account.</span></span> <span data-ttu-id="9c7df-127">それらのアプリケーションのすべてでは、(特定のアカウント) の外部パスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c7df-127">You must set the external password (for the given account) in all of those Applications.</span></span>  

## <a name="more-info"></a><span data-ttu-id="9c7df-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9c7df-128">More info</span></span>

- [<span data-ttu-id="9c7df-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="9c7df-129">Password Synchronization</span></span>](../core/password-synchronization2.md)  

- <span data-ttu-id="9c7df-130">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7df-130">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
