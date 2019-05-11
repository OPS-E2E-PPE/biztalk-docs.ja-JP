---
title: 自動登録と承認プロセス |Microsoft Docs
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
ms.openlocfilehash: aafe1e5557d61303370b2119a82340288d8744f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399869"
---
# <a name="the-auto-enlist-and-approval-process"></a><span data-ttu-id="f0ca2-102">自動登録と承認プロセス</span><span class="sxs-lookup"><span data-stu-id="f0ca2-102">The Auto-Enlist and Approval Process</span></span>
<span data-ttu-id="f0ca2-103">2 つの方法で Microsoft BizTalk Server のエンドポイントを公開する ESB 管理ポータルを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-103">You can configure the ESB Management Portal to publish Microsoft BizTalk Server endpoints in two ways:</span></span>  
  
- <span data-ttu-id="f0ca2-104">それを構成するには承認プロセスを管理者が確認し、登録要求を承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-104">It can be configured through the approval process, where an administrator must confirm and approve the registration request.</span></span>  
  
- <span data-ttu-id="f0ca2-105">使用して構成できます自動発行ポータルに自動的に公開する要求 Universal Description, Discovery, and Integration (UDDI) のレジストリに管理者の介入なし。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-105">It can be configured by using auto-publish, where the portal automatically publishes the request into the Universal Description, Discovery, and Integration (UDDI) registry without requiring administrator intervention.</span></span>  
  
  <span data-ttu-id="f0ca2-106">次の 2 つの手順」の説明に従って、ポータルの UDDI の統合機能の他のいくつかの設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-106">You can also specify several other settings of the UDDI Integration features of the portal, as described in the following two procedures.</span></span>  
  
### <a name="to-configure-auto-approval-and-publishing-in-the-esb-management-portal"></a><span data-ttu-id="f0ca2-107">ESB 管理ポータルでの自動承認と発行を構成するには</span><span class="sxs-lookup"><span data-stu-id="f0ca2-107">To configure auto-approval and publishing in the ESB Management Portal</span></span>  
  
1.  <span data-ttu-id="f0ca2-108">BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-108">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="f0ca2-109">ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**レジストリ設定**ポータルを開く[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-109">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="f0ca2-110">自動承認と発行を有効にするには、上部にあるテキスト ボックスに UDDI サーバーの URL を入力、 **UDDI の詳細**クリックして、ページのセクション、**自動**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-110">To enable auto-approval and publishing, type the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page, and then select the **AutoPublish** check box.</span></span>  
  
4.  <span data-ttu-id="f0ca2-111">自動承認と公開を無効にする、オフ、**自動発行**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-111">To disable auto-approval and publishing, clear the **Auto Publish** check box.</span></span>  
  
### <a name="to-configure-e-mail-and-registry-settings-for-the-uddi-integration-features"></a><span data-ttu-id="f0ca2-112">UDDI の統合機能の電子メールとレジストリの設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="f0ca2-112">To configure e-mail and registry settings for the UDDI Integration features</span></span>  
  
1.  <span data-ttu-id="f0ca2-113">BizTalk Server 管理者アカウントのグループのメンバーであるアカウントを使用してポータルにログオンすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-113">Make sure that you log on to the portal using an account that is a member of the BizTalk Server Administrators account group.</span></span>  
  
2.  <span data-ttu-id="f0ca2-114">ポイントして、**管理者**ポータルのメイン メニューで、タブをクリックして**レジストリ設定**ポータルを開く[レジストリ設定 ページ](../esb-toolkit/registry-settings-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-114">Point to the **Admin** tab on the portal main menu, and then click **Registry Settings** to open the portal [Registry Settings Page](../esb-toolkit/registry-settings-page.md).</span></span>  
  
3.  <span data-ttu-id="f0ca2-115">上部にあるテキスト ボックスに、UDDI サーバーの URL の編集、 **UDDI 詳細**ページのセクション。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-115">Edit the URL of your UDDI server in the text box at the top of the **UDDI Details** section of the page.</span></span> <span data-ttu-id="f0ca2-116">既定の UDDI サービスは、ローカルの Microsoft UDDI サービスです。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-116">The default UDDI service is the local Microsoft UDDI service.</span></span>  
  
4.  <span data-ttu-id="f0ca2-117">選択、 **Anonymous**する場合は、UDDI サーバーにアクセスするときに、匿名認証を使用するポータル チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-117">Select the **Anonymous** check box if you want the portal to use anonymous authentication when accessing the UDDI server.</span></span>  
  
5.  <span data-ttu-id="f0ca2-118">UDDI 発行時に電子メールで通知するように、要求が承認を待ちを選択する場合は、ポータル、**通知が有効になっている** チェック ボックス、**電子メール通知**ページのセクション。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-118">If you want the portal to notify you by e-mail when a UDDI publishing request is awaiting approval, select the **Notification Enabled** check box in the **Email Notification** section of the page.</span></span> <span data-ttu-id="f0ca2-119">電子メール サーバー、電子メール メッセージの配信アドレス、適切な「差出人」電子メール アドレス、メッセージの件名、およびメッセージ本文の詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-119">Then enter the details of your e-mail server, the address for delivery of e-mail messages, an appropriate "from" e-mail address, the message subject, and the message body.</span></span>  
  
6.  <span data-ttu-id="f0ca2-120">管理者の連絡先名を入力し、UDDI の受信確認の電子メール アドレスに電子メール メッセージの要求、**既定の設定の**ページのセクション。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-120">Enter the administrator contact name and e-mail address for the receipt of UDDI request e-mail messages in the **Default Settings** section of the page.</span></span>  
  
### <a name="to-approve-or-decline-a-registration-request-as-an-administrator"></a><span data-ttu-id="f0ca2-121">承認または管理者としての登録要求を拒否するには</span><span class="sxs-lookup"><span data-stu-id="f0ca2-121">To approve or decline a registration request as an administrator</span></span>  
  
1.  <span data-ttu-id="f0ca2-122">BizTalk Server 管理者グループのメンバーであるアカウントを使用してポータルにログインすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-122">Make sure that you log into the portal using an account that is a member of the BizTalk Server Administrators group.</span></span>  
  
2.  <span data-ttu-id="f0ca2-123">ポイントして、**レジストリ**ポータルのメイン メニューで、タブをクリックして**保留中の要求の管理**ポータルを開く[保留中の要求の管理ページ](../esb-toolkit/manage-pending-requests-page.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-123">Point to the **Registry** tab on the portal main menu, and then click **Manage Pending Requests** to open the portal [Manage Pending Requests Page](../esb-toolkit/manage-pending-requests-page.md).</span></span>  
  
3.  <span data-ttu-id="f0ca2-124">保留中の要求を承認するには、クリックして、**承認**一覧でその要求の横にあるアイコン (チェック マーク)。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-124">To approve a pending request, click the **Approve** icon (the check mark) next to that request in the list.</span></span>  
  
4.  <span data-ttu-id="f0ca2-125">保留中の要求を拒否する をクリックして、**拒否**一覧でその要求の横にあるアイコン (十字)。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-125">To reject a pending request, click the **Reject** icon (the cross mark) next to that request in the list.</span></span>  
  
5.  <span data-ttu-id="f0ca2-126">保留中の要求の詳細を表示する をクリックして、**詳細を表示する**アイコン (虫眼鏡) を開く、[レジストリ詳細ページ](../esb-toolkit/registry-details-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-126">To view details of a pending request, click the **View Details** icon (the magnifying glass) to open the [Registry Details Page](../esb-toolkit/registry-details-page.md).</span></span> <span data-ttu-id="f0ca2-127">発行し、削除、またはこのページで、要求を更新できます。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-127">You can publish, delete, or update the request in this page.</span></span>  
  
6.  <span data-ttu-id="f0ca2-128">要求の状態を確認して、以前の要求の一覧を表示、クリックして、**要求履歴を表示する**リンク。</span><span class="sxs-lookup"><span data-stu-id="f0ca2-128">To review the requests status and see a list of previous requests, click the **View Request History** link.</span></span>