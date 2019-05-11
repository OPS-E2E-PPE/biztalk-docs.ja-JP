---
title: シングル サインオン:イベント 10586 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 757c84a4affa65493428cabd3fdb955f5415d234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271041"
---
# <a name="single-sign-on-event-10586"></a><span data-ttu-id="f6616-102">シングル サインオン:イベント 10586</span><span class="sxs-lookup"><span data-stu-id="f6616-102">Single Sign-On: Event 10586</span></span>
## <a name="details"></a><span data-ttu-id="f6616-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f6616-103">Details</span></span>  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  <span data-ttu-id="f6616-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f6616-104">Product Name</span></span>   |                  <span data-ttu-id="f6616-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f6616-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="f6616-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f6616-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    <span data-ttu-id="f6616-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f6616-107">Event ID</span></span>     |                            <span data-ttu-id="f6616-108">10586</span><span class="sxs-lookup"><span data-stu-id="f6616-108">10586</span></span>                            |
|  <span data-ttu-id="f6616-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f6616-109">Event Source</span></span>   |                           <span data-ttu-id="f6616-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f6616-110">ENTSSO</span></span>                            |
|    <span data-ttu-id="f6616-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6616-111">Component</span></span>    |                             <span data-ttu-id="f6616-112">なし</span><span class="sxs-lookup"><span data-stu-id="f6616-112">N/A</span></span>                             |
|  <span data-ttu-id="f6616-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f6616-113">Symbolic Name</span></span>  |                   <span data-ttu-id="f6616-114">SSO_WARN_CRED_CACHE_OFF</span><span class="sxs-lookup"><span data-stu-id="f6616-114">SSO_WARN_CRED_CACHE_OFF</span></span>                   |
|  <span data-ttu-id="f6616-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f6616-115">Message Text</span></span>   | <span data-ttu-id="f6616-116">この SSO サーバーの資格情報キャッシュを無効にされています。</span><span class="sxs-lookup"><span data-stu-id="f6616-116">The credential cache has been disabled for this SSO server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f6616-117">説明</span><span class="sxs-lookup"><span data-stu-id="f6616-117">Explanation</span></span>  
 <span data-ttu-id="f6616-118">一般に、有効になっている資格情報キャッシュが無効になりました。</span><span class="sxs-lookup"><span data-stu-id="f6616-118">The credential cache, which is generally enabled, has been disabled.</span></span> <span data-ttu-id="f6616-119">システム管理者だけでは、有効にしたり、資格情報キャッシュを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f6616-119">Only a system administrator can enable or disable the credential cache.</span></span> <span data-ttu-id="f6616-120">資格情報キャッシュを無効にすることがありますになります、ENTSSO システムからの最新の資格情報が、パフォーマンス低下することできます。</span><span class="sxs-lookup"><span data-stu-id="f6616-120">Disabling the credential cache will sometimes result in more current credentials from the ENTSSO system, although it could slow down peformance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6616-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f6616-121">User Action</span></span>  
 <span data-ttu-id="f6616-122">資格情報キャッシュを再度有効にするには、方法アプリケーション プロパティ テーブルを参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="f6616-122">To re-enable the credential cache, see the Afflilate Application Properties table in [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>