---
title: エンタープライズ シングル サインオンを実装する |Microsoft ドキュメント
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
ms.openlocfilehash: dfd4aaf39456c68c744384aa05ff5664e781aa3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256466"
---
# <a name="implementing-enterprise-single-sign-on"></a><span data-ttu-id="cf63e-102">エンタープライズ シングル サインオンの実装</span><span class="sxs-lookup"><span data-stu-id="cf63e-102">Implementing Enterprise Single Sign-On</span></span>
<span data-ttu-id="cf63e-103">エンタープライズ シングル サインオン (SSO) では、エンド ユーザーのエンタープライズ アプリケーション統合 (EAI) ソリューションへのシングル サインオンを有効にするサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf63e-103">Enterprise Single Sign-On (SSO) provides services to enable single sign-on to end users for enterprise application integration (EAI) solutions.</span></span> <span data-ttu-id="cf63e-104">SSO システムによって、Microsoft Windows アカウントがバックエンド資格情報にマップされます。</span><span class="sxs-lookup"><span data-stu-id="cf63e-104">The SSO system maps Microsoft Windows accounts to back-end credentials.</span></span> <span data-ttu-id="cf63e-105">SSO を使用すると、ユーザーと管理者の両方のユーザー ID およびパスワードの管理が簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="cf63e-105">SSO simplifies the management of user IDs and passwords, both for users and administrators.</span></span> <span data-ttu-id="cf63e-106">また、ユーザーは Windows ネットワークに 1 回ログオンするだけで、バックエンド システムおよびバックエンド アプリケーションにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf63e-106">It enables users to access back-end systems and applications by logging on only once to the Windows network.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf63e-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cf63e-107">In This Section</span></span>  
  
-   [<span data-ttu-id="cf63e-108">SSO について</span><span class="sxs-lookup"><span data-stu-id="cf63e-108">Understanding SSO</span></span>](../core/understanding-sso.md)  
  
-   [<span data-ttu-id="cf63e-109">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="cf63e-109">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="cf63e-110">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="cf63e-110">Using SSO</span></span>](../core/using-sso.md)  
  
-   [<span data-ttu-id="cf63e-111">SSO 展開のセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="cf63e-111">Securing Your Deployment of SSO</span></span>](../core/securing-your-deployment-of-sso.md)  
  
-   [<span data-ttu-id="cf63e-112">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="cf63e-112">Password Synchronization</span></span>](../core/password-synchronization2.md)  
  
-   [<span data-ttu-id="cf63e-113">SSO のセキュリティに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="cf63e-113">SSO Security Recommendations</span></span>](../core/sso-security-recommendations.md)