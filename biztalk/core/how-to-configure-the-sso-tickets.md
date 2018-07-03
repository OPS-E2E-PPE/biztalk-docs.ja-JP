---
title: SSO チケットを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
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
ms.openlocfilehash: edec81ab1fa64ce7b4523771bb2c69b39c00bdfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018760"
---
# <a name="how-to-configure-the-sso-tickets"></a><span data-ttu-id="545cd-102">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="545cd-102">How to Configure the SSO Tickets</span></span>
<span data-ttu-id="545cd-103">MMC スナップインやコマンド ラインを使用して、チケットを許可するかどうか、システムでチケットを検証するかどうかなど、シングル サインオン システム全体のチケットの動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-103">You can use the MMC Snap-In or the command line to control ticket behavior for the entire Single Sign-On system, including whether to allow tickets, and whether the system must validate the tickets.</span></span>  
  
 <span data-ttu-id="545cd-104">チケットを許可したり検証したりするかどうかを示すために、Yes、No、On、または Off を使用できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-104">You can use Yes, No, On, or Off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="545cd-105">これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。</span><span class="sxs-lookup"><span data-stu-id="545cd-105">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
 <span data-ttu-id="545cd-106">リモート コンピューターに SSO 管理機能がインストールされている場合、リモート チケット発行操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-106">If you have the SSO Administration feature installed on a remote computer, remote IssueTicket operation can be performed.</span></span> <span data-ttu-id="545cd-107">SSO 管理モジュールとランタイム モジュール (ENTSSO サービス) との間のすべてのトラフィックが暗号化されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="545cd-107">Note that all traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
 <span data-ttu-id="545cd-108">コマンド ライン ユーティリティの ssomanage.exe を使用して、アプリケーションの作成時ではなく、アプリケーションの更新が実行されたときのみ、関連アプリケーション レベルでチケットのタイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-108">Using the command line utility, ssomanage.exe, you can specify the ticket timeout at the Affiliate Application level only when an update of the Application is performed,  not at creation time.</span></span>  
  
 <span data-ttu-id="545cd-109">SSO 管理者だけは、SSO システム レベルと関連アプリケーション レベルでチケットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-109">Only an SSO Administrator can configure tickets at the SSO System level and at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="545cd-110">チケットをシステム レベルで無効にすると、関連アプリケーション レベルではチケットを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="545cd-110">If ticketing is disabled at the system level, it cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="545cd-111">チケットをシステム レベルで有効にして、関連アプリケーション レベルで無効にすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="545cd-111">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="545cd-112">検証をシステム レベルで有効にすると、関連アプリケーション レベルでもチケットの検証が必要になります。</span><span class="sxs-lookup"><span data-stu-id="545cd-112">If validation is enabled at the system level, validation of tickets are required at the Affiliate Application level as well.</span></span> <span data-ttu-id="545cd-113">検証をシステム レベルで無効にして、関連アプリケーション レベルで有効にすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="545cd-113">It is possible to disable validation at the system level and enable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="545cd-114">チケットのタイムアウトをシステム レベルと関連アプリケーション レベルの両方で指定した場合、関連アプリケーション レベルで指定したチケットのタイムアウトが、チケットの有効期限の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="545cd-114">If Ticket timeout is specified both at the System level and the Affiliate Application level, the one specified at the Affiliate Application level is used to determine the ticket expiry time.</span></span>  
  
 <span data-ttu-id="545cd-115">チケットとチケットの検証の詳細については、次を参照してください。 [SSO チケット](../core/sso-tickets.md)します。</span><span class="sxs-lookup"><span data-stu-id="545cd-115">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a><span data-ttu-id="545cd-116">MMC スナップインを使用して関連アプリケーションのエンタープライズ シングル サインオン チケットを構成するには</span><span class="sxs-lookup"><span data-stu-id="545cd-116">To configure the Enterprise Single Sign-On tickets using the MMC Snap-In for the Affiliate Application</span></span>  
  
1.  <span data-ttu-id="545cd-117">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="545cd-117">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="545cd-118">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**関連アプリケーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="545cd-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="545cd-119">右クリックして**関連アプリケーション**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="545cd-119">Right-click **Affiliate Application**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="545cd-120">をクリックして、**オプション**タブ。</span><span class="sxs-lookup"><span data-stu-id="545cd-120">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="545cd-121">選択**チケットを許可**とチケットのタイムアウトを適切に構成します。</span><span class="sxs-lookup"><span data-stu-id="545cd-121">Select **Allow Tickets** and configure the ticket timeout as appropriate.</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a><span data-ttu-id="545cd-122">コマンド ラインを使用してエンタープライズ シングル サインオン システム レベルのチケットを構成するには</span><span class="sxs-lookup"><span data-stu-id="545cd-122">To configure the Enterprise Single Sign-On system-level tickets using the command line</span></span>  
  
1. <span data-ttu-id="545cd-123">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="545cd-123">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="545cd-124">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="545cd-124">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="545cd-125">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="545cd-125">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="545cd-126">型 * * ssomanage – チケット\<許可はい/いいえ\> *\<はい/いいえの検証\>**<em>ここで、*\<許可はい/いいえ\></em>チケットを許可するか、そうでないかどうかを示すと*\<はい/いいえの検証\>* チケットは、では引き換え後に検証する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="545cd-126">Type **ssomanage –tickets \<allowed yes/no\> *\<validate yes/no\>**<em>, where *\<allowed yes/no\></em> indicates whether tickets will be allowed or not, and *\<validate yes/no\>* indicates whether tickets will need to be validated after they are redeemed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="545cd-127">チケットを許可したり検証したりするかどうかを示すために、yes、no、on、または off を使用できます。</span><span class="sxs-lookup"><span data-stu-id="545cd-127">You can use yes, no, on, or off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="545cd-128">これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。</span><span class="sxs-lookup"><span data-stu-id="545cd-128">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="545cd-129">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="545cd-129">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="545cd-130">参照</span><span class="sxs-lookup"><span data-stu-id="545cd-130">See Also</span></span>  
 <span data-ttu-id="545cd-131">[SSO について](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="545cd-131">[Understanding SSO](../core/understanding-sso.md) </span></span>  
 [<span data-ttu-id="545cd-132">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="545cd-132">Using SSO</span></span>](../core/using-sso.md)