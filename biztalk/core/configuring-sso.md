---
title: SSO の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233042"
---
# <a name="configuring-sso"></a><span data-ttu-id="2c783-102">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="2c783-102">Configuring SSO</span></span>
<span data-ttu-id="2c783-103">コマンド ライン ユーティリティ、UI ツール、または COM インターフェイスか Microsoft .NET インターフェイスを使用して、エンタープライズ シングル サインオンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-103">You can configure Enterprise Single Sign-On by using command line utilities, UI tools, or COM or Microsoft .NET interfaces.</span></span>  
  
## <a name="sso-command-line-utilities"></a><span data-ttu-id="2c783-104">SSO コマンド ライン ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="2c783-104">SSO command line utilities</span></span>  
 <span data-ttu-id="2c783-105">次の 3 つの異なるコマンド ライン ユーティリティを使用して、エンタープライズ シングル サインオンの作業を実行します。</span><span class="sxs-lookup"><span data-stu-id="2c783-105">You use three different command line utilities to perform Enterprise Single Sign-On tasks:</span></span>  
  
 <span data-ttu-id="2c783-106">**SSOConfig です。**</span><span class="sxs-lookup"><span data-stu-id="2c783-106">**SSOConfig.**</span></span> <span data-ttu-id="2c783-107">SSO 管理者は、SSO データベースを構成し、マスタ シークレットを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-107">Enables an SSO administrator to configure the SSO database and to manage the master secret.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c783-108">構成ウィザードで SSO データベースおよびマスタ シークレット サーバーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c783-108">The Configuration Wizard creates the SSO database and the master secret server.</span></span>  
  
 <span data-ttu-id="2c783-109">**SSOManage です。**</span><span class="sxs-lookup"><span data-stu-id="2c783-109">**SSOManage.**</span></span> <span data-ttu-id="2c783-110">SSO 管理者、SSO 関連管理者、およびアプリケーション管理者は、追加する SSO データベースの更新、アプリケーションの削除と管理、ユーザー マッピングの管理、および関連アプリケーションのユーザー用の資格情報の設定を行えます。</span><span class="sxs-lookup"><span data-stu-id="2c783-110">Enables SSO administrators, SSO affiliate administrators, and application administrators to update the SSO database to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="2c783-111">一部の操作をできるのは、SSO 管理者のみ、または SSO 管理者と SSO 関連管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="2c783-111">Some operations can be performed only by the SSO administrators, or, only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="2c783-112">アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者も実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-112">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and the SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="2c783-113">**SSOClient です。**</span><span class="sxs-lookup"><span data-stu-id="2c783-113">**SSOClient.**</span></span> <span data-ttu-id="2c783-114">シングル サインオン ユーザーは、固有のユーザー マッピングを管理し、資格証明を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-114">Enables Single Sign-On users to manage their own user mappings and set their credentials.</span></span>  
  
 <span data-ttu-id="2c783-115">SSO アカウントの詳細については、次を参照してください。 [SSO ユーザー グループ](../core/sso-user-groups.md)です。</span><span class="sxs-lookup"><span data-stu-id="2c783-115">For more information about the SSO accounts, see [SSO User Groups](../core/sso-user-groups.md).</span></span>  
  
## <a name="sso-ui-tools"></a><span data-ttu-id="2c783-116">SSO UI ツール</span><span class="sxs-lookup"><span data-stu-id="2c783-116">SSO UI tools</span></span>  
 <span data-ttu-id="2c783-117">**エンタープライズ SSO MMC スナップイン。**</span><span class="sxs-lookup"><span data-stu-id="2c783-117">**Enterprise SSO MMC Snap-in.**</span></span> <span data-ttu-id="2c783-118">SSO 管理者、SSO 関連管理者、およびアプリケーション管理者は、SSO データベースの更新、アプリケーションの追加、削除、管理、ユーザー マッピングの管理、および関連アプリケーションのユーザー用の資格情報の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2c783-118">Enables SSO Administrators, SSO Affiliate Administrators, and Application Administrators to update the SSO database, to add, delete and manage applications, administer user mappings, and to set credentials for the affiliate application users.</span></span> <span data-ttu-id="2c783-119">一部の操作は、SSO 管理者のみ、または SSO 管理者と SSO 関連管理者のみが実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-119">Some operations can be performed only by the SSO administrators, or only by the SSO administrators and SSO affiliate administrators.</span></span> <span data-ttu-id="2c783-120">アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-120">All operations that can be performed by the Application Administrators can also be performed by the SSO Administrators and SSO Affiliate Administrators.</span></span>  
  
 <span data-ttu-id="2c783-121">**SSO クライアント ユーティリティ。**</span><span class="sxs-lookup"><span data-stu-id="2c783-121">**SSO Client Utility.**</span></span> <span data-ttu-id="2c783-122">エンド ユーザーは、UI ツールを使用して、固有のマッピングを管理し、資格証明を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2c783-122">Enables end users to manage their own mappings and set their credentials using the UI tool.</span></span>  
  
## <a name="sso-com-and-net-interfaces"></a><span data-ttu-id="2c783-123">SSO の COM インターフェイスおよび .NET インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c783-123">SSO COM and .NET interfaces</span></span>  
 <span data-ttu-id="2c783-124">エンタープライズ シングル サインオンでは、カスタム コンポーネントの作成、および SSO システムの管理を容易にするスクリプトの作成をプログラムから行える、COM および .NET のインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2c783-124">Enterprise Single Sign-On provides COM and .NET programmatic interfaces that enable you to create custom components, and to create scripts to facilitate the administration of the SSO system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c783-125">参照</span><span class="sxs-lookup"><span data-stu-id="2c783-125">See Also</span></span>  
 [<span data-ttu-id="2c783-126">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2c783-126">SSO Components</span></span>](../core/sso-components.md)