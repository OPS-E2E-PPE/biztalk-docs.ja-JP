---
title: シングル サインオン:イベント 10742 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe1849acf5ad6cbafb948465a0cbc8f8f06ba84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400573"
---
# <a name="single-sign-on-event-10742"></a><span data-ttu-id="bfc74-102">シングル サインオン:イベント 10742</span><span class="sxs-lookup"><span data-stu-id="bfc74-102">Single Sign-On: Event 10742</span></span>
## <a name="details"></a><span data-ttu-id="bfc74-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bfc74-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bfc74-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bfc74-104">Product Name</span></span>   |                                                                                                                                         <span data-ttu-id="bfc74-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bfc74-105">Enterprise Single Sign-On</span></span>                                                                                                                                          |
| <span data-ttu-id="bfc74-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bfc74-106">Product Version</span></span> |                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                         |
|    <span data-ttu-id="bfc74-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bfc74-107">Event ID</span></span>     |                                                                                                                                                   <span data-ttu-id="bfc74-108">10742</span><span class="sxs-lookup"><span data-stu-id="bfc74-108">10742</span></span>                                                                                                                                                    |
|  <span data-ttu-id="bfc74-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bfc74-109">Event Source</span></span>   |                                                                                                                                                   <span data-ttu-id="bfc74-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfc74-110">ENTSSO</span></span>                                                                                                                                                   |
|    <span data-ttu-id="bfc74-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfc74-111">Component</span></span>    |                                                                                                                                                    <span data-ttu-id="bfc74-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="bfc74-112">N\A</span></span>                                                                                                                                                     |
|  <span data-ttu-id="bfc74-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bfc74-113">Symbolic Name</span></span>  |                                                                                                                                         <span data-ttu-id="bfc74-114">SSO_WARN_NO_UPDATE_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="bfc74-114">SSO_WARN_NO_UPDATE_ADAPTER</span></span>                                                                                                                                         |
|  <span data-ttu-id="bfc74-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bfc74-115">Message Text</span></span>   | <span data-ttu-id="bfc74-116">クライアント ユーザーは adapter.%r を更新するには、SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfc74-116">The client user must be a member of the SSO Administrators account or the Application Administrators account to update the adapter.%r</span></span><br /><br /> <span data-ttu-id="bfc74-117">クライアント ユーザー: 1 %r</span><span class="sxs-lookup"><span data-stu-id="bfc74-117">Client User: %1%r</span></span><br /><br /> <span data-ttu-id="bfc74-118">SSO 管理者: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="bfc74-118">SSO Administrators: %2%r</span></span><br /><br /> <span data-ttu-id="bfc74-119">アプリケーション管理者: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="bfc74-119">Application Administrators: %3%r</span></span><br /><br /> <span data-ttu-id="bfc74-120">アダプター: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="bfc74-120">Adapter: %4%r</span></span><br /><br /> <span data-ttu-id="bfc74-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="bfc74-121">Error Code: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="bfc74-122">説明</span><span class="sxs-lookup"><span data-stu-id="bfc74-122">Explanation</span></span>  
 <span data-ttu-id="bfc74-123">この警告イベントは、指定したアダプターを更新しようとが行われたが、使用するユーザー アカウントが SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーではないために、完了できませんでしたを示します。</span><span class="sxs-lookup"><span data-stu-id="bfc74-123">This Warning event indicates that an attempt to update the specified adapter was made, but could not be completed because the user account used is not a member of the SSO Administrators account or the Application Administrators account.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bfc74-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bfc74-124">User Action</span></span>  
 <span data-ttu-id="bfc74-125">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bfc74-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="bfc74-126">SSO 管理者アカウントまたはアプリケーション管理者アカウントにユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="bfc74-126">Add user account to the SSO Administrators account or the Application Administrators account.</span></span>  

- <span data-ttu-id="bfc74-127">更新プログラムを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="bfc74-127">Retry update.</span></span>  

  <span data-ttu-id="bfc74-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfc74-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="bfc74-129">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="bfc74-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
