---
title: SSO の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19825ec6f420b8ec3e30f5dead09ad1d901503f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355197"
---
# <a name="configuring-sso"></a><span data-ttu-id="b1a3b-102">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-102">Configuring SSO</span></span>
<span data-ttu-id="b1a3b-103">コマンド ライン ユーティリティ、UI ツール、または COM コンポーネントまたは Microsoft .NET インターフェイスを使用して、エンタープライズ シングル サインオン構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-103">You can configure Enterprise Single Sign-On by using command line utilities, UI tools, or COM or Microsoft .NET interfaces.</span></span>  
  
## <a name="sso-command-line-utilities"></a><span data-ttu-id="b1a3b-104">SSO コマンド ライン ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="b1a3b-104">SSO command line utilities</span></span>  
 <span data-ttu-id="b1a3b-105">次の 3 つの異なるコマンド ライン ユーティリティを使用して、エンタープライズ シングル サインオンのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-105">You use three different command line utilities to perform Enterprise Single Sign-On tasks:</span></span>  
  
 <span data-ttu-id="b1a3b-106">**SSOConfig します。**</span><span class="sxs-lookup"><span data-stu-id="b1a3b-106">**SSOConfig.**</span></span> <span data-ttu-id="b1a3b-107">SSO 管理者は SSO データベースを構成して、マスター シークレットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-107">Enables an SSO administrator to configure the SSO database and to manage the master secret.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1a3b-108">構成ウィザードでは、SSO データベースとマスター シークレット サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-108">The Configuration Wizard creates the SSO database and the master secret server.</span></span>  
  
 <span data-ttu-id="b1a3b-109">**SSOManage します。**</span><span class="sxs-lookup"><span data-stu-id="b1a3b-109">**SSOManage.**</span></span> <span data-ttu-id="b1a3b-110">SSO 管理者、SSO 関連管理者、およびアプリケーション管理者、SSO データベースを更新する、追加、削除、アプリケーションの管理と、ユーザーのマッピングの管理と、関連会社の資格情報をアプリケーションのユーザー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-110">Enables SSO administrators, SSO affiliate administrators, and application administrators to update the SSO database to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="b1a3b-111">一部の操作は、SSO 管理者によってのみ実行できるまたは、だけで、SSO 管理者と SSO 関連管理者。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-111">Some operations can be performed only by the SSO administrators, or, only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="b1a3b-112">アプリケーション管理者が実行できるすべての操作は、SSO 管理者と SSO 関連管理者でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-112">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and the SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="b1a3b-113">**SSOClient します。**</span><span class="sxs-lookup"><span data-stu-id="b1a3b-113">**SSOClient.**</span></span> <span data-ttu-id="b1a3b-114">シングル サインオンをユーザーが自分のユーザー マッピングを管理し、自分の資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-114">Enables Single Sign-On users to manage their own user mappings and set their credentials.</span></span>  
  
 <span data-ttu-id="b1a3b-115">SSO アカウントの詳細については、次を参照してください。 [SSO ユーザー グループ](../core/sso-user-groups.md)します。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-115">For more information about the SSO accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
## <a name="sso-ui-tools"></a><span data-ttu-id="b1a3b-116">SSO UI ツール</span><span class="sxs-lookup"><span data-stu-id="b1a3b-116">SSO UI tools</span></span>  
 <span data-ttu-id="b1a3b-117">**エンタープライズ SSO MMC スナップイン。**</span><span class="sxs-lookup"><span data-stu-id="b1a3b-117">**Enterprise SSO MMC Snap-in.**</span></span> <span data-ttu-id="b1a3b-118">SSO 管理者、SSO 関連管理者、およびアプリケーション管理者と、SSO データベースの更新を追加、削除し、アプリケーションの管理、ユーザーのマッピングの管理、アプリケーションのユーザーに、関連会社の資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-118">Enables SSO Administrators, SSO Affiliate Administrators, and Application Administrators to update the SSO database, to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="b1a3b-119">だけで、SSO 管理者と SSO 関連管理者または、SSO 管理者だけがいくつかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-119">Some operations can be performed only by the SSO administrators, or only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="b1a3b-120">アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-120">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="b1a3b-121">**SSO クライアント ユーティリティ。**</span><span class="sxs-lookup"><span data-stu-id="b1a3b-121">**SSO Client Utility.**</span></span> <span data-ttu-id="b1a3b-122">エンドユーザーが自分のマッピングを管理し、UI ツールを使用して、資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-122">Enables end users to manage their own mappings and set their credentials using the UI tool.</span></span>  
  
## <a name="sso-com-and-net-interfaces"></a><span data-ttu-id="b1a3b-123">SSO の COM および .NET インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b1a3b-123">SSO COM and .NET interfaces</span></span>  
 <span data-ttu-id="b1a3b-124">エンタープライズ シングル サインオンを使用するカスタム コンポーネントを作成して、SSO システムの管理に役立つスクリプトを作成する COM と .NET のプログラミング インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1a3b-124">Enterprise Single Sign-On provides COM and .NET programmatic interfaces that enable you to create custom components, and to create scripts to facilitate the administration of the SSO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1a3b-125">参照</span><span class="sxs-lookup"><span data-stu-id="b1a3b-125">See Also</span></span>  
 [<span data-ttu-id="b1a3b-126">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b1a3b-126">SSO Components</span></span>](../core/sso-components.md)