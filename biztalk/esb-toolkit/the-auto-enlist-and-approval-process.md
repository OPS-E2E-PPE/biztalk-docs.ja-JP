---
title: 自動参加および承認プロセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dfd3e72e-e28b-4ee3-bc4a-89ef3f64e6d5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333e1403ffd45f80a98d3eb17f5d3aa2b63c7798
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295626"
---
# <a name="the-auto-enlist-and-approval-process"></a><span data-ttu-id="5f199-102">自動参加と承認のプロセス</span><span class="sxs-lookup"><span data-stu-id="5f199-102">The Auto-Enlist and Approval Process</span></span>
<span data-ttu-id="5f199-103">2 つの方法で Microsoft BizTalk Server のエンドポイントを公開する、ESB の管理ポータルを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f199-103">You can configure the ESB Management Portal to publish Microsoft BizTalk Server endpoints in two ways:</span></span>  
  
-   <span data-ttu-id="5f199-104">これは、管理者のことを確認して登録要求を承認する必要がありますここで、承認プロセスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5f199-104">It can be configured through the approval process, where an administrator must confirm and approve the registration request.</span></span>  
  
-   <span data-ttu-id="5f199-105">使用して構成できます自動発行が、ここで、ポータルに自動的に公開要求 Universal Description, Discovery, and Integration (UDDI) のレジストリに管理者の介入なし。</span><span class="sxs-lookup"><span data-stu-id="5f199-105">It can be configured by using auto-publish, where the portal automatically publishes the request into the Universal Description, Discovery, and Integration (UDDI) registry without requiring administrator intervention.</span></span>  
  
 <span data-ttu-id="5f199-106">次の 2 つの手順で説明されても、ポータルの UDDI の統合機能の他のいくつかの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5f199-106">You can also specify several other settings of the UDDI Integration features of the portal, as described in the following two procedures.</span></span>  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a><span data-ttu-id="5f199-107">ESB の管理ポータルで自動承認と公開を構成するには</span><span class="sxs-lookup"><span data-stu-id="5f199-107">To configure auto-approval and publishing in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="5f199-108">BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f199-108">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="5f199-109">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**レジストリ設定**を開くには、ポータル[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f199-109">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="5f199-110">自動承認と公開を有効にするには、上部にあるテキスト ボックスに、UDDI サーバーの URL を入力、 **UDDI 詳細**クリックし、ページのセクション、**自動**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="5f199-110">To enable auto-approval and publishing, type the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page, and then select the **AutoPublish** check box.</span></span>  
  
4.  <span data-ttu-id="5f199-111">自動承認と公開を無効にする、オフ、**自動発行**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="5f199-111">To disable auto-approval and publishing, clear the **Auto Publish** check box.</span></span>  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a><span data-ttu-id="5f199-112">UDDI の統合機能の電子メールとレジストリの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="5f199-112">To configure e-mail and registry settings for the UDDI Integration features</span></span>  
  
1.  <span data-ttu-id="5f199-113">BizTalk Server 管理者アカウント グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5f199-113">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group.</span></span>  
  
2.  <span data-ttu-id="5f199-114">をポイント、 **Admin**ポータルのメイン メニュー タブをクリックして**レジストリ設定**を開くには、ポータル[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f199-114">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="5f199-115">上部にあるテキスト ボックスに、UDDI サーバーの URL を編集、 **UDDI 詳細**ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="5f199-115">Edit the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page.</span></span> <span data-ttu-id="5f199-116">既定の UDDI サービスは、ローカルの Microsoft UDDI サービスです。</span><span class="sxs-lookup"><span data-stu-id="5f199-116">The default UDDI service is the local Microsoft UDDI service.</span></span>  
  
4.  <span data-ttu-id="5f199-117">選択、**匿名**する場合は、ポータル UDDI サーバーにアクセスするときに、匿名認証を使用する チェック ボックスです。</span><span class="sxs-lookup"><span data-stu-id="5f199-117">Select the **Anonymous** check box if you want the portal to use anonymous authentication when accessing the UDDI server.</span></span>  
  
5.  <span data-ttu-id="5f199-118">要求が承認を待ち、UDDI 発行時に電子メールで通知するように、選択する場合は、ポータル、**通知が有効になっている** チェック ボックス、**電子メール通知**ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="5f199-118">If you want the portal to notify you by e-mail when a UDDI publishing request is awaiting approval, select the **Notification Enabled** check box in the **Email Notification** section of the page.</span></span> <span data-ttu-id="5f199-119">電子メール サーバー、電子メール メッセージの配信アドレス、適切な"from"電子メール アドレス、メッセージの件名、およびメッセージ本文の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f199-119">Then enter the details of your e-mail server, the address for delivery of e-mail messages, an appropriate "from" e-mail address, the message subject, and the message body.</span></span>  
  
6.  <span data-ttu-id="5f199-120">管理者の連絡先の名前を入力し、UDDI の受信確認の電子メール アドレスに電子メール メッセージの要求、**既定の設定の**ページのセクションです。</span><span class="sxs-lookup"><span data-stu-id="5f199-120">Enter the administrator contact name and e-mail address for the receipt of UDDI request e-mail messages in the **Default Settings** section of the page.</span></span>  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a><span data-ttu-id="5f199-121">承認または管理者としての登録要求を拒否するには</span><span class="sxs-lookup"><span data-stu-id="5f199-121">To approve or decline a registration request as an administrator</span></span>  
  
1.  <span data-ttu-id="5f199-122">BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f199-122">Make sure that you log into the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="5f199-123">をポイント、**レジストリ**ポータルのメイン メニュー タブをクリックして**保留中の要求の管理**を開くには、ポータル[保留中の要求 ページの管理](../esb-toolkit/manage-pending-requests-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f199-123">Point to the **Registry** tab on the portal main menu, and then click **Manage Pending Requests** to open the portal [Manage Pending Requests Page](../esb-toolkit/manage-pending-requests-page.md).</span></span>  
  
3.  <span data-ttu-id="5f199-124">保留中の要求を承認するには、クリックして、**承認**一覧にその要求の横にあるアイコン (チェック マーク)。</span><span class="sxs-lookup"><span data-stu-id="5f199-124">To approve a pending request, click the **Approve** icon (the check mark) next to that request in the list.</span></span>  
  
4.  <span data-ttu-id="5f199-125">保留中の要求を拒否する をクリックして、**拒否**一覧にその要求の横にあるアイコン (クロス マーク)。</span><span class="sxs-lookup"><span data-stu-id="5f199-125">To reject a pending request, click the **Reject** icon (the cross mark) next to that request in the list.</span></span>  
  
5.  <span data-ttu-id="5f199-126">保留中の要求の詳細を表示する をクリックして、**詳細を表示する**アイコン (虫眼鏡) を開くには、[レジストリ詳細 ページ](../esb-toolkit/registry-details-page.md)です。</span><span class="sxs-lookup"><span data-stu-id="5f199-126">To view details of a pending request, click the **View Details** icon (the magnifying glass) to open the [Registry Details Page](../esb-toolkit/registry-details-page.md).</span></span> <span data-ttu-id="5f199-127">発行し、削除、またはこのページで、要求を更新できます。</span><span class="sxs-lookup"><span data-stu-id="5f199-127">You can publish, delete, or update the request in this page.</span></span>  
  
6.  <span data-ttu-id="5f199-128">要求の状態を確認して、以前の要求の一覧を表示をクリックして、**要求履歴を表示する**リンクします。</span><span class="sxs-lookup"><span data-stu-id="5f199-128">To review the requests status and see a list of previous requests, click the **View Request History** link.</span></span>