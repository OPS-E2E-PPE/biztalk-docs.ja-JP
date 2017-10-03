---
title: "Applications5 関連の作成 |Microsoft ドキュメント"
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
- creating affiliate applications
- tickets, SSO
- affiliate applications, enabling XML
- SSO tickets
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6b42a6f3251d9e897af21fcb4207b6790e91cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="4084a-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="4084a-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="4084a-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4084a-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4084a-104">SSO エラーが発生した場合は、BizTalk Server の構成時にドメイン アカウントを使用したかどうかを確認してください。これは Enterprise SSO サービスの機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="4084a-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="4084a-105">ドメイン アカウントで SSO のみ関数</span><span class="sxs-lookup"><span data-stu-id="4084a-105">SSO only functions under a domain account</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="4084a-106">関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="4084a-106">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="4084a-107">コントロール パネルで、開く**Services**、エンタープライズ シングル サインオン サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4084a-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="4084a-108">コマンド プロンプトで、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="4084a-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="4084a-109">例:</span><span class="sxs-lookup"><span data-stu-id="4084a-109">For example:</span></span>  
  
     <span data-ttu-id="4084a-110">**C:\Program files \common files \enterprise でのシングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="4084a-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="4084a-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="4084a-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="4084a-112">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="4084a-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="4084a-113">使用して関連アプリケーションを作成する * です。スタート、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-113">To create the affiliate application by using *.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="4084a-114">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4084a-114">where:</span></span>  
  
    -   <span data-ttu-id="4084a-115">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="4084a-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="4084a-116">AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="4084a-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="4084a-117">例:</span><span class="sxs-lookup"><span data-stu-id="4084a-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="TIBCO EMS App">  
            <description>TIBCO EMS SSO Application</description>  
            <contact>someone@example.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
            <!—an existing group on the domain controller - >   
            <appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
            <!-- an existing account in the domain group - >   
            <field ordinal="0" label="User ID" masked="no" />  
            <field ordinal="1" label="Password" masked="yes" />  
            <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
    </SSO>  
    ```  
  
 <span data-ttu-id="4084a-118">XML の例を使用する場合、関連アプリケーションである TIBCO EMS App には、コマンド プロンプトに表示される値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4084a-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="4084a-119">シングル サインオン チケットを作成するには</span><span class="sxs-lookup"><span data-stu-id="4084a-119">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="4084a-120">次のコマンドを入力し、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="4084a-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="4084a-121">次の質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="4084a-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="4084a-122">完了時に、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4084a-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="4084a-123">**このコンピューターで使用中の SSO。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="4084a-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="4084a-124">関連アプリケーション XML を有効にするには</span><span class="sxs-lookup"><span data-stu-id="4084a-124">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="4084a-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="4084a-126">次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4084a-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="4084a-127">使用可能な関連アプリケーションが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4084a-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="4084a-128">**Ibi \YOURID-TIBCO EMSApp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="4084a-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="4084a-129">関連アプリケーションの資格情報を設定するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="4084a-130">プロンプトで、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="4084a-131">TIBCO EMS App 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="4084a-132">たとえば、ユーザー id と、SSO サーバーにより、システムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4084a-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="4084a-133">ユーザー ID:**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="4084a-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="4084a-134">パスワード:`******`</span><span class="sxs-lookup"><span data-stu-id="4084a-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="4084a-135">確認入力 </span><span class="sxs-lookup"><span data-stu-id="4084a-135">Confirm?</span></span> <span data-ttu-id="4084a-136">パスワード:`******`</span><span class="sxs-lookup"><span data-stu-id="4084a-136">Password: `******`</span></span>  
  
     <span data-ttu-id="4084a-137">関連アプリケーションは、TIBCO EMS の BizTalk アダプターに表示されます。**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4084a-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4084a-138">参照</span><span class="sxs-lookup"><span data-stu-id="4084a-138">See Also</span></span>  
 [<span data-ttu-id="4084a-139">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="4084a-139">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)