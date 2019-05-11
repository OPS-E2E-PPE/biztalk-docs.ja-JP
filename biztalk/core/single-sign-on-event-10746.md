---
title: シングル サインオン:イベント 10746 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8189120b-923a-4c88-937e-f06565bcac56
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19bef7a20062761f1d019b786bd96581b302bec4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395494"
---
# <a name="single-sign-on-event-10746"></a><span data-ttu-id="3c02b-102">シングル サインオン:イベント 10746</span><span class="sxs-lookup"><span data-stu-id="3c02b-102">Single Sign-On: Event 10746</span></span>
## <a name="details"></a><span data-ttu-id="3c02b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3c02b-103">Details</span></span>  

|                 |                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3c02b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3c02b-104">Product Name</span></span>   |                                                           <span data-ttu-id="3c02b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3c02b-105">Enterprise Single Sign-On</span></span>                                                           |
| <span data-ttu-id="3c02b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3c02b-106">Product Version</span></span> |                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                           |
|    <span data-ttu-id="3c02b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3c02b-107">Event ID</span></span>     |                                                                     <span data-ttu-id="3c02b-108">10746</span><span class="sxs-lookup"><span data-stu-id="3c02b-108">10746</span></span>                                                                     |
|  <span data-ttu-id="3c02b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3c02b-109">Event Source</span></span>   |                                                                    <span data-ttu-id="3c02b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3c02b-110">ENTSSO</span></span>                                                                     |
|    <span data-ttu-id="3c02b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3c02b-111">Component</span></span>    |                                                                      <span data-ttu-id="3c02b-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="3c02b-112">N\A</span></span>                                                                      |
|  <span data-ttu-id="3c02b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3c02b-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="3c02b-114">SSO_WARN_PASSWORD_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="3c02b-114">SSO_WARN_PASSWORD_EXPIRED</span></span>                                                           |
|  <span data-ttu-id="3c02b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3c02b-115">Message Text</span></span>   | <span data-ttu-id="3c02b-116">外部アカウントのパスワードが expired.%r</span><span class="sxs-lookup"><span data-stu-id="3c02b-116">The password for the external account has expired.%r</span></span><br /><br /> <span data-ttu-id="3c02b-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="3c02b-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="3c02b-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="3c02b-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="3c02b-119">外部アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="3c02b-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="3c02b-120">説明</span><span class="sxs-lookup"><span data-stu-id="3c02b-120">Explanation</span></span>  
 <span data-ttu-id="3c02b-121">この警告イベントは、外部アカウントのパスワードの期限が切れたことを示します。</span><span class="sxs-lookup"><span data-stu-id="3c02b-121">This Warning event indicates that the password for the external account has expired.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3c02b-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3c02b-122">User Action</span></span>  
 <span data-ttu-id="3c02b-123">この警告を解決するには、関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c02b-123">To resolve this warning, check the system and application event logs for associated errors.</span></span>    

## <a name="more-info"></a><span data-ttu-id="3c02b-124">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3c02b-124">More info</span></span>
<span data-ttu-id="3c02b-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c02b-125">For more information, see the following resources:</span></span>  

- <span data-ttu-id="3c02b-126">**パスワード同期アダプターのプロパティ:オプション** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3c02b-126">**Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="3c02b-127">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="3c02b-127">Password Synchronization</span></span>](../core/password-synchronization2.md)
