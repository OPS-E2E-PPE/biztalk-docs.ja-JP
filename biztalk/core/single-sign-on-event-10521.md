---
title: "シングル サインオン: イベント 10521 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 827771fe479084719db18152fd86da7d1fc01a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10521"></a><span data-ttu-id="77043-102">シングル サインオン: イベント 10521</span><span class="sxs-lookup"><span data-stu-id="77043-102">Single Sign-On: Event 10521</span></span>
## <a name="details"></a><span data-ttu-id="77043-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77043-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77043-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77043-104">Product Name</span></span>|<span data-ttu-id="77043-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="77043-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="77043-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77043-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="77043-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77043-107">Event ID</span></span>|<span data-ttu-id="77043-108">10521</span><span class="sxs-lookup"><span data-stu-id="77043-108">10521</span></span>|  
|<span data-ttu-id="77043-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77043-109">Event Source</span></span>|<span data-ttu-id="77043-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77043-110">ENTSSO</span></span>|  
|<span data-ttu-id="77043-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77043-111">Component</span></span>|<span data-ttu-id="77043-112">N\A</span><span class="sxs-lookup"><span data-stu-id="77043-112">N\A</span></span>|  
|<span data-ttu-id="77043-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77043-113">Symbolic Name</span></span>|<span data-ttu-id="77043-114">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="77043-114">SSO_ERROR_SECRETS_NOT_LOADED</span></span>|  
|<span data-ttu-id="77043-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77043-115">Message Text</span></span>|<span data-ttu-id="77043-116">マスター シークレット サーバーのレジストリからシークレットを読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="77043-116">Could not load secrets from the registry of the master secret server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77043-117">説明</span><span class="sxs-lookup"><span data-stu-id="77043-117">Explanation</span></span>  
 <span data-ttu-id="77043-118">このエラー イベントは、マスター シークレットをレジストリから取得できない場合にマスター シークレット サーバーで発生します。</span><span class="sxs-lookup"><span data-stu-id="77043-118">This Error event occurs on the master secret server when the master secrets cannot be obtained from the registry.</span></span> <span data-ttu-id="77043-119">イベント ログに詳細を示す関連エラー メッセージが記録されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="77043-119">There may be related errors messages in the event log with further information.</span></span> <span data-ttu-id="77043-120">このエラーの最も大きな原因は、SSO サービスがレジストリにアクセスしようとしたときに、アクセス許可エラーまたは暗号化エラーが発生していることです。</span><span class="sxs-lookup"><span data-stu-id="77043-120">The most likely cause of this is that there has been a permissions error or an encryption error when the SSO service account attempted to access the registry.</span></span> <span data-ttu-id="77043-121">これは、SSO サービス アカウントが変更されたときに発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="77043-121">This can occur when the SSO service account has been changed.</span></span> <span data-ttu-id="77043-122">マスター シークレットは、SSO サービス アカウントの ID に基づくキーで暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="77043-122">The master secret is encrypted with a key that is based on the identity of the SSO service account.</span></span> <span data-ttu-id="77043-123">このアカウントが変更されると、レジストリ内にある既存のマスター シークレットの暗号化を解除できなくなります。</span><span class="sxs-lookup"><span data-stu-id="77043-123">If that account is changed, then the existing master secret in the registry can no longer be decrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77043-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77043-124">User Action</span></span>  
 <span data-ttu-id="77043-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="77043-125">To resolve this error, do the following:</span></span>  
  
-   <span data-ttu-id="77043-126">SSO サービス アカウントを変更する場合は、マスター シークレットをバックアップし、SSO サービス アカウントを変更した後、マスター シークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="77043-126">Change the SSO service account by backing-up the master secret, then changing the SSO service account, and then restoring the master secret.</span></span> <span data-ttu-id="77043-127">これによって、マスター シークレットを復元することができ、このエラーが修正されます。</span><span class="sxs-lookup"><span data-stu-id="77043-127">This can restore the master secret and should fix this error.</span></span>  
  
 <span data-ttu-id="77043-128">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="77043-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="77043-129">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="77043-129">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="77043-130">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="77043-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  
  
-   [<span data-ttu-id="77043-131">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="77043-131">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
-   [<span data-ttu-id="77043-132">SSO のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="77043-132">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)