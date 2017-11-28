---
title: "Applications1 関連の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, affiliate
- Single Sign-On, tickets
- affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f52c59caf451a2e0b55c775bf70a36a9a05ae9c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="c9bc5-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="c9bc5-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="c9bc5-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-103">The following steps describe how to start working with affiliate applications and Single Sign-On (SSO).</span></span> <span data-ttu-id="c9bc5-104">エンタープライズ シングル サインオンの使用方法の詳細については、Microsoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-104">For complete information about how to use Enterprise Single Sign-On, see the Microsoft documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9bc5-105">SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-105">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="c9bc5-106">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-106">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="c9bc5-107">関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="c9bc5-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="c9bc5-108">コントロール パネルで、開く**Services**、エンタープライズ シングル サインオン サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-108">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="c9bc5-109">コマンド プロンプトで、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span> <span data-ttu-id="c9bc5-110">例:</span><span class="sxs-lookup"><span data-stu-id="c9bc5-110">For example:</span></span>  
  
     <span data-ttu-id="c9bc5-111">**C:\Program files \common files \enterprise でのシングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="c9bc5-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="c9bc5-112">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="c9bc5-113">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-113">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="c9bc5-114">使用して関連アプリケーションを作成する * です。スタート、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-114">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="c9bc5-115">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-115">Where:</span></span>  
  
     <span data-ttu-id="c9bc5-116">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
     <span data-ttu-id="c9bc5-117">AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-117">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="c9bc5-118">例:</span><span class="sxs-lookup"><span data-stu-id="c9bc5-118">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO RendezvousApp">  
            <description> TIBCO Rendezvous SSO Application</description>  
            <contact>someone@microsoft.com</contact>  
            <userGroup>ibi\Domain Users</userGroup>  
            <!—an existing group on the domain controller - >   
            <appAdminGroup>ibi\YourID</appAdminGroup>  
            <!-- an existing account within the domain group - >   
  
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
  
        </application>  
    </SSO>  
    ```  
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="c9bc5-119">シングル サインオン チケットを作成するには</span><span class="sxs-lookup"><span data-stu-id="c9bc5-119">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="c9bc5-120">次のコマンドを入力し、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="c9bc5-121">表示される次の質問に応答します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-121">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  <span data-ttu-id="c9bc5-122">完了時に、次の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-122">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="c9bc5-123">**このコンピューターで使用中の SSO。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="c9bc5-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="c9bc5-124">関連アプリケーション XML を有効にするには</span><span class="sxs-lookup"><span data-stu-id="c9bc5-124">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="c9bc5-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  <span data-ttu-id="c9bc5-126">次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="c9bc5-127">使用可能な関連アプリケーションが一覧内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="c9bc5-128">**Ibi \YOURID-TIBCO RendezvousApp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="c9bc5-128">**Applications available for IBI\YourID - TIBCO RendezvousApp**</span></span>  
  
3.  <span data-ttu-id="c9bc5-129">関連アプリケーションの資格情報を設定するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  <span data-ttu-id="c9bc5-130">ユーザー名とパスワードのプロンプトで入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-130">Enter the User name and password at the prompts.</span></span>  
  
5.  <span data-ttu-id="c9bc5-131">TIBCO RendezvousApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-131">Enter the logon credentials for the TIBCO RendezvousApp affiliate application.</span></span>  
  
     <span data-ttu-id="c9bc5-132">たとえば、そのユーザーが SSO サーバーを経由してシステムに入力するユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-132">For example, enter the user identification and the password for the user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="c9bc5-133">ユーザー ID: user</span><span class="sxs-lookup"><span data-stu-id="c9bc5-133">User ID: user</span></span>  
  
    -   <span data-ttu-id="c9bc5-134">パスワード: ******</span><span class="sxs-lookup"><span data-stu-id="c9bc5-134">Password: ******</span></span>  
  
    -   <span data-ttu-id="c9bc5-135">パスワードの確認入力: ******</span><span class="sxs-lookup"><span data-stu-id="c9bc5-135">Confirm Password: ******</span></span>  
  
6.  <span data-ttu-id="c9bc5-136">関連アプリケーションが TIBCO Rendezvous の BizTalk アダプターに表示される**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-136">The affiliate application appears in the BizTalk Adapter for TIBCO Rendezvous **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bc5-137">参照</span><span class="sxs-lookup"><span data-stu-id="c9bc5-137">See Also</span></span>  
 <span data-ttu-id="c9bc5-138">[BizTalk Adapter for TIBCO Rendezvous のセキュリティ](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="c9bc5-138">[Security in BizTalk Adapter for TIBCO Rendezvous](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="c9bc5-139">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9bc5-139">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)