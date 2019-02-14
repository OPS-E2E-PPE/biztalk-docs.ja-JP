---
title: SSO チケットの構成 |Microsoft Docs
description: SSO 管理者またはコマンドラインを使用してシステム レベル、および BizTalk Server での関連アプリケーション用のエンタープライズ シングル サインオン チケットを検証しています。
ms.custom: ''
ms.date: 01/08/2019
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO], configuring tickets
- SSO, tickets
- tickets [SSO], configuring
ms.assetid: 32f0384b-ac79-4cce-b3f5-f4f8a73a673a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3abac3a0d527c6834105db8fd1c74fd934fd821d
ms.sourcegitcommit: 41947648c73d437a201b2190307e0270d61e037a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56087934"
---
# <a name="configure-the-sso-tickets-in-biztalk-server"></a><span data-ttu-id="fe102-103">BizTalk Server で SSO チケットを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe102-103">Configure the SSO Tickets in BizTalk Server</span></span>
<span data-ttu-id="fe102-104">シングル サインオン システム全体のエンタープライズ シングル サインオン (SSO) 管理 mmc スナップインまたはチケットの動作を制御するためのコマンドラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe102-104">You can use Enterprise Single Sign-On (SSO) Administration MMC or the command line to control ticket behavior for the entire single sign-on system.</span></span> <span data-ttu-id="fe102-105">このツールを使用して、チケットを許可し、SSO チケットを検証できます。</span><span class="sxs-lookup"><span data-stu-id="fe102-105">Using this tools, you can allow tickets and validate SSO tickets.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="fe102-106">アンインストールの準備</span><span class="sxs-lookup"><span data-stu-id="fe102-106">Before you begin</span></span>

- <span data-ttu-id="fe102-107">リモートを行うことができる場合、SSO の管理は、リモートのコンピューターにインストールされて、 [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method)操作。</span><span class="sxs-lookup"><span data-stu-id="fe102-107">If SSO Administration is installed on a remote computer, you can run a remote [IssueTicket](https://docs.microsoft.com/biztalk/core/technical-reference/issoticket-issueticket-method) operation.</span></span> <span data-ttu-id="fe102-108">SSO 管理モジュールとランタイム モジュール (ENTSSO サービス) の間のすべてのトラフィックが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="fe102-108">All traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
- <span data-ttu-id="fe102-109">コマンド ライン ユーティリティ ssomanage.exe を使用して、関連アプリケーション レベルでチケットのタイムアウトを入力できます。</span><span class="sxs-lookup"><span data-stu-id="fe102-109">Using the ssomanage.exe command line utility, you can enter the ticket timeout at the Affiliate Application level.</span></span> <span data-ttu-id="fe102-110">これは、アプリケーションが作成されたときではなく、アプリケーションの更新が行われたときにのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe102-110">You can do this only when an update of the application is made, not when the application is created.</span></span>
  
- <span data-ttu-id="fe102-111">SSO 管理者グループのユーザーだけは、SSO システム レベルおよび関連アプリケーション レベルでチケットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="fe102-111">Only users in the SSO Administrator group can configure tickets at the SSO system-level and at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="fe102-112">システム レベルでチケットが無効になっている場合は、関連アプリケーション レベルで使用できません。</span><span class="sxs-lookup"><span data-stu-id="fe102-112">If ticketing is disabled at the system-level, it can't be used at the Affiliate Application level.</span></span> <span data-ttu-id="fe102-113">システム レベルでチケットを有効にして、関連アプリケーション レベルで無効にすることになります。</span><span class="sxs-lookup"><span data-stu-id="fe102-113">It's possible to enable tickets at the system level, and disable them at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="fe102-114">システム レベルでは、検証が有効である場合、関連アプリケーション レベルでチケットを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe102-114">If validation is enabled at the system-level, tickets must be validated at the Affiliate Application level.</span></span> <span data-ttu-id="fe102-115">システム レベルでの検証を無効にし、関連アプリケーション レベルで有効にすることになります。</span><span class="sxs-lookup"><span data-stu-id="fe102-115">It's possible to disable validation at the system-level, and enable it at the Affiliate Application level.</span></span>  
  
- <span data-ttu-id="fe102-116">システム レベルと関連アプリケーション レベルでチケットのタイムアウトを入力すると、関連アプリケーション レベルで入力した 1 つは、チケットの有効期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="fe102-116">If ticket timeout is entered at the system-level and the Affiliate Application level, the one entered at the Affiliate Application level determines the ticket expiration time.</span></span>  
  
<span data-ttu-id="fe102-117">チケットとチケットの検証の詳細については、次を参照してください。 [SSO チケット](../core/sso-tickets.md)します。</span><span class="sxs-lookup"><span data-stu-id="fe102-117">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
## <a name="allow-affiliate-application-tickets-using-sso-administration"></a><span data-ttu-id="fe102-118">SSO の管理を使用して関連アプリケーションのチケットを許可します。</span><span class="sxs-lookup"><span data-stu-id="fe102-118">Allow Affiliate Application tickets using SSO Administration</span></span>  
  
1.  <span data-ttu-id="fe102-119">**開始**メニューの **すべてのプログラム** > **Microsoft エンタープライズ シングル サインオン** > **SSO の管理**.</span><span class="sxs-lookup"><span data-stu-id="fe102-119">From the **Start** menu, select **All Programs** > **Microsoft Enterprise Single Sign-On** > **SSO Administration**.</span></span>
  
2.  <span data-ttu-id="fe102-120">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**関連アプリケーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="fe102-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="fe102-121">右クリックして**関連アプリケーション** > **プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="fe102-121">Right-click **Affiliate Application** > **Properties**.</span></span>  
  
4.  <span data-ttu-id="fe102-122">選択、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="fe102-122">Choose the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="fe102-123">選択**チケットを許可**し、必要なチケットのタイムアウトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe102-123">Select **Allow Tickets** and enter the ticket timeout you want.</span></span>  
  
## <a name="allow-and-validate-sso-system-level-tickets-using-the-command-line"></a><span data-ttu-id="fe102-124">許可して、コマンドラインを使用して SSO システム レベルのチケットの検証</span><span class="sxs-lookup"><span data-stu-id="fe102-124">Allow and validate SSO system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="fe102-125">コマンド プロンプトを開き ([スタート] メニュー > 型**コマンド プロンプト**> 選択**コマンド プロンプト**)。</span><span class="sxs-lookup"><span data-stu-id="fe102-125">Open a command prompt (Start menu > type **command prompt** > select **Command Prompt**).</span></span>

    > [!TIP]
    >  <span data-ttu-id="fe102-126">ユーザー アカウント制御 (UAC) をサポートするシステムで管理者特権でコマンド プロンプトを開く必要があります (右クリックして**コマンド プロンプト** > **管理者として実行**)。</span><span class="sxs-lookup"><span data-stu-id="fe102-126">On a system that supports User Account Control (UAC), you may need to open the command prompt with Administrative privileges (right-click **Command Prompt** > **Run as administrator**).</span></span>
  
2. <span data-ttu-id="fe102-127">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe102-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fe102-128">既定のインストール ディレクトリは`\Program Files\Common Files\Enterprise Single Sign-On`します。</span><span class="sxs-lookup"><span data-stu-id="fe102-128">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span> <span data-ttu-id="fe102-129">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fe102-129">For example, enter:</span></span> 

    `cd C:\Program Files\Common Files\Enterprise Single Sign-On`
  
3. <span data-ttu-id="fe102-130">型`ssomanage -tickets <allowed yes/no> <validate yes/no>`ここで、 *\<許可はい/いいえ\>* チケットを許可するかどうかどうかを示すと *\<はい/いいえの検証\>* チケットを引き換えるがいる後に検証が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="fe102-130">Type `ssomanage -tickets <allowed yes/no> <validate yes/no>`, where *\<allowed yes/no\>* indicates whether tickets are allowed or not, and *\<validate yes/no\>* indicates whether tickets need to be validated after they're redeemed.</span></span>  
  
    <span data-ttu-id="fe102-131">使用することができます`yes`、 `no`、 `on`、または`off`を許可したり、チケットを検証します。</span><span class="sxs-lookup"><span data-stu-id="fe102-131">You can use `yes`, `no`, `on`, or `off` to allow and/or validate tickets.</span></span> <span data-ttu-id="fe102-132">これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。</span><span class="sxs-lookup"><span data-stu-id="fe102-132">These words are case independent, and must be used regardless of your language settings.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe102-133">参照</span><span class="sxs-lookup"><span data-stu-id="fe102-133">See Also</span></span>

<span data-ttu-id="fe102-134">[SSO について](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="fe102-134">[Understanding SSO](../core/understanding-sso.md) </span></span>  
[<span data-ttu-id="fe102-135">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="fe102-135">Using SSO</span></span>](../core/using-sso.md)
