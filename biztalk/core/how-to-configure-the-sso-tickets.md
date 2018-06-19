---
title: SSO チケットを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c3b19d14a35d42c4a46bf9527a97f5bf749b875f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968648"
---
# <a name="how-to-configure-the-sso-tickets"></a><span data-ttu-id="f043e-102">SSO チケットを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f043e-102">How to Configure the SSO Tickets</span></span>
<span data-ttu-id="f043e-103">MMC スナップインやコマンド ラインを使用して、チケットを許可するかどうか、システムでチケットを検証するかどうかなど、シングル サインオン システム全体のチケットの動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-103">You can use the MMC Snap-In or the command line to control ticket behavior for the entire Single Sign-On system, including whether to allow tickets, and whether the system must validate the tickets.</span></span>  
  
 <span data-ttu-id="f043e-104">チケットを許可したり検証したりするかどうかを示すために、Yes、No、On、または Off を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-104">You can use Yes, No, On, or Off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="f043e-105">これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。</span><span class="sxs-lookup"><span data-stu-id="f043e-105">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
 <span data-ttu-id="f043e-106">リモート コンピューターに SSO 管理機能がインストールされている場合、リモート チケット発行操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-106">If you have the SSO Administration feature installed on a remote computer, remote IssueTicket operation can be performed.</span></span> <span data-ttu-id="f043e-107">SSO 管理モジュールとランタイム モジュール (ENTSSO サービス) との間のすべてのトラフィックが暗号化されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f043e-107">Note that all traffic between the SSO Administration module and the Runtime module (ENTSSO service) is encrypted.</span></span>  
  
 <span data-ttu-id="f043e-108">コマンド ライン ユーティリティの ssomanage.exe を使用して、アプリケーションの作成時ではなく、アプリケーションの更新が実行されたときのみ、関連アプリケーション レベルでチケットのタイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-108">Using the command line utility, ssomanage.exe, you can specify the ticket timeout at the Affiliate Application level only when an update of the Application is performed,  not at creation time.</span></span>  
  
 <span data-ttu-id="f043e-109">SSO 管理者だけは、SSO システム レベルと関連アプリケーション レベルでチケットを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-109">Only an SSO Administrator can configure tickets at the SSO System level and at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="f043e-110">チケットをシステム レベルで無効にすると、関連アプリケーション レベルではチケットを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f043e-110">If ticketing is disabled at the system level, it cannot be used at the Affiliate Application level either.</span></span> <span data-ttu-id="f043e-111">チケットをシステム レベルで有効にして、関連アプリケーション レベルで無効にすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="f043e-111">It is possible to enable tickets at the system level and disable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="f043e-112">検証をシステム レベルで有効にすると、関連アプリケーション レベルでもチケットの検証が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f043e-112">If validation is enabled at the system level, validation of tickets are required at the Affiliate Application level as well.</span></span> <span data-ttu-id="f043e-113">検証をシステム レベルで無効にして、関連アプリケーション レベルで有効にすることは可能です。</span><span class="sxs-lookup"><span data-stu-id="f043e-113">It is possible to disable validation at the system level and enable it at the Affiliate Application level.</span></span>  
  
 <span data-ttu-id="f043e-114">チケットのタイムアウトをシステム レベルと関連アプリケーション レベルの両方で指定した場合、関連アプリケーション レベルで指定したチケットのタイムアウトが、チケットの有効期限の決定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f043e-114">If Ticket timeout is specified both at the System level and the Affiliate Application level, the one specified at the Affiliate Application level is used to determine the ticket expiry time.</span></span>  
  
 <span data-ttu-id="f043e-115">チケットとチケットの検証の詳細については、次を参照してください。 [SSO チケット](../core/sso-tickets.md)です。</span><span class="sxs-lookup"><span data-stu-id="f043e-115">For more information about tickets and tickets validation, see [SSO Tickets](../core/sso-tickets.md).</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-tickets-using-the-mmc-snap-in-for-the-affiliate-application"></a><span data-ttu-id="f043e-116">MMC スナップインを使用して関連アプリケーションのエンタープライズ シングル サインオン チケットを構成するには</span><span class="sxs-lookup"><span data-stu-id="f043e-116">To configure the Enterprise Single Sign-On tickets using the MMC Snap-In for the Affiliate Application</span></span>  
  
1.  <span data-ttu-id="f043e-117">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="f043e-117">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="f043e-118">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**関連アプリケーション**ノード。</span><span class="sxs-lookup"><span data-stu-id="f043e-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Affiliate Applications** node.</span></span>  
  
3.  <span data-ttu-id="f043e-119">右クリック**関連アプリケーション**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f043e-119">Right-click **Affiliate Application**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f043e-120">クリックして、**オプション**タブです。</span><span class="sxs-lookup"><span data-stu-id="f043e-120">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="f043e-121">選択**チケットを許可**し、必要に応じてチケットのタイムアウトを構成します。</span><span class="sxs-lookup"><span data-stu-id="f043e-121">Select **Allow Tickets** and configure the ticket timeout as appropriate.</span></span>  
  
### <a name="to-configure-the-enterprise-single-sign-on-system-level-tickets-using-the-command-line"></a><span data-ttu-id="f043e-122">コマンド ラインを使用してエンタープライズ シングル サインオン システム レベルのチケットを構成するには</span><span class="sxs-lookup"><span data-stu-id="f043e-122">To configure the Enterprise Single Sign-On system-level tickets using the command line</span></span>  
  
1.  <span data-ttu-id="f043e-123">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="f043e-123">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="f043e-124">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f043e-124">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="f043e-125">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="f043e-125">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="f043e-126">型**ssomanage – チケット\<はい/いいえの許可\> *\<はい/いいえの検証\>*** ここで、 *\<はい/いいえの許可\>* チケットを許可するか、かどうかを示すと*\<検証はい/いいえ\>* チケットは、では引き換え後に検証する必要があるかどうかを示します.</span><span class="sxs-lookup"><span data-stu-id="f043e-126">Type **ssomanage –tickets \<allowed yes/no\> *\<validate yes/no\>***, where *\<allowed yes/no\>* indicates whether tickets will be allowed or not, and *\<validate yes/no\>* indicates whether tickets will need to be validated after they are redeemed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f043e-127">チケットを許可したり検証したりするかどうかを示すために、yes、no、on、または off を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f043e-127">You can use yes, no, on, or off to indicate whether to allow and/or validate tickets.</span></span> <span data-ttu-id="f043e-128">これらの語は大文字と小文字が区別されないため、言語の設定に関係なく使用してください。</span><span class="sxs-lookup"><span data-stu-id="f043e-128">These words are case independent, and must be used regardless of your language settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f043e-129">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f043e-129">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f043e-130">参照</span><span class="sxs-lookup"><span data-stu-id="f043e-130">See Also</span></span>  
 <span data-ttu-id="f043e-131">[SSO について](../core/understanding-sso.md) </span><span class="sxs-lookup"><span data-stu-id="f043e-131">[Understanding SSO](../core/understanding-sso.md) </span></span>  
 [<span data-ttu-id="f043e-132">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="f043e-132">Using SSO</span></span>](../core/using-sso.md)