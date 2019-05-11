---
title: シングル サインオン:イベント 10521 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00d427ff-74d0-45f5-bb55-ab12b564d767
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccb36c1306736fed435099c46254ee34d0079a1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394352"
---
# <a name="single-sign-on-event-10521"></a><span data-ttu-id="3e556-102">シングル サインオン:イベント 10521</span><span class="sxs-lookup"><span data-stu-id="3e556-102">Single Sign-On: Event 10521</span></span>
## <a name="details"></a><span data-ttu-id="3e556-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3e556-103">Details</span></span>  

|                 |                                                                       |
|-----------------|-----------------------------------------------------------------------|
|  <span data-ttu-id="3e556-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3e556-104">Product Name</span></span>   |                       <span data-ttu-id="3e556-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3e556-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="3e556-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3e556-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    <span data-ttu-id="3e556-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3e556-107">Event ID</span></span>     |                                 <span data-ttu-id="3e556-108">10521</span><span class="sxs-lookup"><span data-stu-id="3e556-108">10521</span></span>                                 |
|  <span data-ttu-id="3e556-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3e556-109">Event Source</span></span>   |                                <span data-ttu-id="3e556-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3e556-110">ENTSSO</span></span>                                 |
|    <span data-ttu-id="3e556-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3e556-111">Component</span></span>    |                                  <span data-ttu-id="3e556-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="3e556-112">N\A</span></span>                                  |
|  <span data-ttu-id="3e556-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3e556-113">Symbolic Name</span></span>  |                     <span data-ttu-id="3e556-114">SSO_ERROR_SECRETS_NOT_LOADED</span><span class="sxs-lookup"><span data-stu-id="3e556-114">SSO_ERROR_SECRETS_NOT_LOADED</span></span>                      |
|  <span data-ttu-id="3e556-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3e556-115">Message Text</span></span>   | <span data-ttu-id="3e556-116">マスター シークレット サーバーのレジストリからシークレットを読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="3e556-116">Could not load secrets from the registry of the master secret server.</span></span> |

## <a name="explanation"></a><span data-ttu-id="3e556-117">説明</span><span class="sxs-lookup"><span data-stu-id="3e556-117">Explanation</span></span>  
 <span data-ttu-id="3e556-118">マスター シークレットは、レジストリから取得することはできません、マスター シークレット サーバーでこのエラー イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="3e556-118">This Error event occurs on the master secret server when the master secrets cannot be obtained from the registry.</span></span> <span data-ttu-id="3e556-119">さらに情報をイベント ログに関連するエラー メッセージが可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e556-119">There may be related errors messages in the event log with further information.</span></span> <span data-ttu-id="3e556-120">これの最も可能性の高い原因があったこと、アクセス許可エラーまたは暗号化エラー SSO サービス アカウントは、レジストリにアクセスしようとした場合です。</span><span class="sxs-lookup"><span data-stu-id="3e556-120">The most likely cause of this is that there has been a permissions error or an encryption error when the SSO service account attempted to access the registry.</span></span> <span data-ttu-id="3e556-121">これは、SSO サービス アカウントが変更されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="3e556-121">This can occur when the SSO service account has been changed.</span></span> <span data-ttu-id="3e556-122">マスター シークレットは、SSO サービス アカウントの id に基づくキーで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="3e556-122">The master secret is encrypted with a key that is based on the identity of the SSO service account.</span></span> <span data-ttu-id="3e556-123">そのアカウントが変更された場合、レジストリ内の既存のマスター シークレットは不要になった解読できません。</span><span class="sxs-lookup"><span data-stu-id="3e556-123">If that account is changed, then the existing master secret in the registry can no longer be decrypted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3e556-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3e556-124">User Action</span></span>  
 <span data-ttu-id="3e556-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3e556-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="3e556-126">マスター シークレットをバックアップするは、SSO サービス アカウントを変更し、マスタ シークレットを復元し、SSO サービス アカウントを変更します。</span><span class="sxs-lookup"><span data-stu-id="3e556-126">Change the SSO service account by backing-up the master secret, then changing the SSO service account, and then restoring the master secret.</span></span> <span data-ttu-id="3e556-127">これは、マスター シークレットを復元でき、このエラーを修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e556-127">This can restore the master secret and should fix this error.</span></span>  

  <span data-ttu-id="3e556-128">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="3e556-128">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="3e556-129">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="3e556-129">Master Secret Server</span></span>](../core/master-secret-server.md)  

- [<span data-ttu-id="3e556-130">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="3e556-130">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)  

- [<span data-ttu-id="3e556-131">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="3e556-131">Configuring SSO</span></span>](../core/configuring-sso.md)  

- [<span data-ttu-id="3e556-132">SSO のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="3e556-132">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)
