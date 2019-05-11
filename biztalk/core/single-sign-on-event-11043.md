---
title: シングル サインオン:イベント 11043 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d24076ea1354d923f16deed837a26d67997a2da4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400974"
---
# <a name="single-sign-on-event-11043"></a><span data-ttu-id="9151e-102">シングル サインオン:イベント 11043</span><span class="sxs-lookup"><span data-stu-id="9151e-102">Single Sign-On: Event 11043</span></span>
## <a name="details"></a><span data-ttu-id="9151e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9151e-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="9151e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9151e-104">Product Name</span></span>   |                                                                                                                                             <span data-ttu-id="9151e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9151e-105">Enterprise Single Sign-On</span></span>                                                                                                                                             |
| <span data-ttu-id="9151e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9151e-106">Product Version</span></span> |                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                             |
|    <span data-ttu-id="9151e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9151e-107">Event ID</span></span>     |                                                                                                                                                       <span data-ttu-id="9151e-108">11043</span><span class="sxs-lookup"><span data-stu-id="9151e-108">11043</span></span>                                                                                                                                                       |
|  <span data-ttu-id="9151e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9151e-109">Event Source</span></span>   |                                                                                                                                                      <span data-ttu-id="9151e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9151e-110">ENTSSO</span></span>                                                                                                                                                       |
|    <span data-ttu-id="9151e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9151e-111">Component</span></span>    |                                                                                                                                                        <span data-ttu-id="9151e-112">なし</span><span class="sxs-lookup"><span data-stu-id="9151e-112">N/A</span></span>                                                                                                                                                        |
|  <span data-ttu-id="9151e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9151e-113">Symbolic Name</span></span>  |                                                                                                                                       <span data-ttu-id="9151e-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span><span class="sxs-lookup"><span data-stu-id="9151e-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span></span>                                                                                                                                        |
|  <span data-ttu-id="9151e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9151e-115">Message Text</span></span>   | <span data-ttu-id="9151e-116">パスワード同期アダプターは、外部パスワードを変更中にエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="9151e-116">The password sync adapter reported a failure while attempting to change the external password.</span></span> <span data-ttu-id="9151e-117">外部パスワードは SSO database.%r で更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="9151e-117">The external password was not updated in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="9151e-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="9151e-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="9151e-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="9151e-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="9151e-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="9151e-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="9151e-121">エラー メッセージ: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="9151e-121">Error Message: %4%r</span></span><br /><br /> <span data-ttu-id="9151e-122">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="9151e-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="9151e-123">説明</span><span class="sxs-lookup"><span data-stu-id="9151e-123">Explanation</span></span>  
 <span data-ttu-id="9151e-124">ENTSSO では、パスワードの変更をパスワード同期アダプターに送信するときに外部パスワードが正常に変更してください ENTSSO により SSO データベースで、前に。</span><span class="sxs-lookup"><span data-stu-id="9151e-124">When ENTSSO sends a password change to a password sync adapter, the external password must be successfully changed before ENTSSO makes it in the SSO database.</span></span> <span data-ttu-id="9151e-125">この場合が行われませんでした。</span><span class="sxs-lookup"><span data-stu-id="9151e-125">In this case, that did not occur.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9151e-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9151e-126">User Action</span></span>  
 <span data-ttu-id="9151e-127">警告メッセージの情報をメモし、システム管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="9151e-127">Note the information in the warning message and consult your system administrator.</span></span>