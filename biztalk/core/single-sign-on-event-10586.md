---
title: 'シングル サインオン: イベント 10586 |Microsoft Docs'
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
ms.openlocfilehash: 2b353c5d9fb569da7bcc35927e31ce5c3e68ae11
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978877"
---
# <a name="single-sign-on-event-10586"></a><span data-ttu-id="f1f8c-102">シングル サインオン: イベント 10586</span><span class="sxs-lookup"><span data-stu-id="f1f8c-102">Single Sign-On: Event 10586</span></span>
## <a name="details"></a><span data-ttu-id="f1f8c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f1f8c-103">Details</span></span>  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  <span data-ttu-id="f1f8c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f1f8c-104">Product Name</span></span>   |                  <span data-ttu-id="f1f8c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f1f8c-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="f1f8c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f1f8c-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    <span data-ttu-id="f1f8c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f1f8c-107">Event ID</span></span>     |                            <span data-ttu-id="f1f8c-108">10586</span><span class="sxs-lookup"><span data-stu-id="f1f8c-108">10586</span></span>                            |
|  <span data-ttu-id="f1f8c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f1f8c-109">Event Source</span></span>   |                           <span data-ttu-id="f1f8c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f1f8c-110">ENTSSO</span></span>                            |
|    <span data-ttu-id="f1f8c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f1f8c-111">Component</span></span>    |                             <span data-ttu-id="f1f8c-112">なし</span><span class="sxs-lookup"><span data-stu-id="f1f8c-112">N/A</span></span>                             |
|  <span data-ttu-id="f1f8c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f1f8c-113">Symbolic Name</span></span>  |                   <span data-ttu-id="f1f8c-114">SSO_WARN_CRED_CACHE_OFF</span><span class="sxs-lookup"><span data-stu-id="f1f8c-114">SSO_WARN_CRED_CACHE_OFF</span></span>                   |
|  <span data-ttu-id="f1f8c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f1f8c-115">Message Text</span></span>   | <span data-ttu-id="f1f8c-116">この SSO サーバーについて資格情報キャッシュが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f1f8c-116">The credential cache has been disabled for this SSO server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f1f8c-117">説明</span><span class="sxs-lookup"><span data-stu-id="f1f8c-117">Explanation</span></span>  
 <span data-ttu-id="f1f8c-118">一般的には有効になっている資格情報キャッシュが無効になっていました。</span><span class="sxs-lookup"><span data-stu-id="f1f8c-118">The credential cache, which is generally enabled, has been disabled.</span></span> <span data-ttu-id="f1f8c-119">資格情報キャッシュを有効または無効にできるのはシステム管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="f1f8c-119">Only a system administrator can enable or disable the credential cache.</span></span> <span data-ttu-id="f1f8c-120">資格情報キャッシュを無効にすると、パフォーマンスが低下する可能性がありますが、ENTSSO システムから、より新しい資格情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="f1f8c-120">Disabling the credential cache will sometimes result in more current credentials from the ENTSSO system, although it could slow down peformance.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1f8c-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f1f8c-121">User Action</span></span>  
 <span data-ttu-id="f1f8c-122">資格情報キャッシュを再度有効にするには、方法アプリケーション プロパティ テーブルを参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1f8c-122">To re-enable the credential cache, see the Afflilate Application Properties table in [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>