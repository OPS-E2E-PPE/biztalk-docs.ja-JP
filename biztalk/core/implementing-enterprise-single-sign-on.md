---
title: エンタープライズ シングル サインオンを実装する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- EAI
- 64-bit environments, SSO support
- SSO, 64-bit support
- SSO
- SSO, service accounts
ms.assetid: 155a62fc-5dc5-4aee-9602-b970067c1bf2
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7dfd1c2a21bcbb5bfe1e7befe299540e59e7526
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382594"
---
# <a name="implementing-enterprise-single-sign-on"></a><span data-ttu-id="465da-102">エンタープライズ シングル サインオンの実装</span><span class="sxs-lookup"><span data-stu-id="465da-102">Implementing Enterprise Single Sign-On</span></span>
<span data-ttu-id="465da-103">エンタープライズ シングル サインオン (SSO) は、エンタープライズ アプリケーション統合 (EAI) ソリューションのためにエンドユーザーのシングル サインオンを有効にするサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="465da-103">Enterprise Single Sign-On (SSO) provides services to enable single sign-on to end users for enterprise application integration (EAI) solutions.</span></span> <span data-ttu-id="465da-104">SSO システムでは、Microsoft Windows アカウントをバックエンド資格情報にマップします。</span><span class="sxs-lookup"><span data-stu-id="465da-104">The SSO system maps Microsoft Windows accounts to back-end credentials.</span></span> <span data-ttu-id="465da-105">SSO には、両方のユーザーと管理者のパスワードとユーザー Id の管理が簡略化します。</span><span class="sxs-lookup"><span data-stu-id="465da-105">SSO simplifies the management of user IDs and passwords, both for users and administrators.</span></span> <span data-ttu-id="465da-106">Windows ネットワークに 1 回だけログインしてバックエンド システムとアプリケーションにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="465da-106">It enables users to access back-end systems and applications by logging on only once to the Windows network.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="465da-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="465da-107">In This Section</span></span>  
  
-   [<span data-ttu-id="465da-108">SSO について</span><span class="sxs-lookup"><span data-stu-id="465da-108">Understanding SSO</span></span>](../core/understanding-sso.md)  
  
-   [<span data-ttu-id="465da-109">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="465da-109">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="465da-110">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="465da-110">Using SSO</span></span>](../core/using-sso.md)  
  
-   [<span data-ttu-id="465da-111">SSO 展開のセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="465da-111">Securing Your Deployment of SSO</span></span>](../core/securing-your-deployment-of-sso.md)  
  
-   [<span data-ttu-id="465da-112">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="465da-112">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   [<span data-ttu-id="465da-113">SSO のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="465da-113">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)