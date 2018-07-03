---
title: PeopleSoft Enterprise の関連アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95151163-5aaf-4683-afb7-02949ccda3e1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f436c9c3193a895d38df630c1bec88abfadc12c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022888"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="30ab2-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="30ab2-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="30ab2-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30ab2-104">SSO エラーが発生した場合は、ときに使用したドメイン アカウントを BizTalk Server を構成するように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="30ab2-105">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="30ab2-106">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="30ab2-107">コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="30ab2-108">コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="30ab2-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-109">For example:</span></span>  
  
    <span data-ttu-id="30ab2-110">**C:\Program files \common files \enterprise でシングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="30ab2-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="30ab2-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="30ab2-112">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="30ab2-112">For a list of commands, use the **-help** switch.</span></span>  
  
    <span data-ttu-id="30ab2-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="30ab2-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4. <span data-ttu-id="30ab2-114">使用して関連アプリケーションを作成する \* です。開始、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="30ab2-115">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="30ab2-115">where:</span></span>  
  
   - <span data-ttu-id="30ab2-116">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="30ab2-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="30ab2-117">AffiliateApplication.xml は、自分で作成した、サインオン情報を含むアプリケーション XML です。</span><span class="sxs-lookup"><span data-stu-id="30ab2-117">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="30ab2-118">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-118">For example:</span></span>  
  
   ```  
   <?xml version="1.0"?>  
   <SSO>  
        <application name="PeopleSoftApp">  
             <description>PeopleSoft SSO Application</description>  
             <contact>someone@microsoft.com</contact>  
            <appUserAccount>DomainName\AppUserGroup</appUserAccount>  
             <!—-an existing group on the domain controller - >   
             <appAdminAccount>DomainName\AppAdminGroup<appAdminAccount>   
             <!-- an existing account in the domain group - >   
             <field ordinal="0" label="User ID" masked="no" />  
             <field ordinal="1" label="Password" masked="yes" />  
             <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
        </application>  
   </SSO>  
   ```  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="30ab2-119">シングル サインオン チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-119">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="30ab2-120">次のコマンドを入力し、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="30ab2-121">次の質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="30ab2-122">完了時に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30ab2-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="30ab2-123">**このコンピューターで使用中の SSO。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="30ab2-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="30ab2-124">関連アプリケーション XML を有効にします。</span><span class="sxs-lookup"><span data-stu-id="30ab2-124">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="30ab2-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="30ab2-126">次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="30ab2-127">使用可能な関連アプリケーションが一覧内に表示されます。</span><span class="sxs-lookup"><span data-stu-id="30ab2-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="30ab2-128">**Ibi \yourid-peoplesoftapp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="30ab2-128">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="30ab2-129">関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="30ab2-130">プロンプトで、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="30ab2-131">PeopleSoftApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-131">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="30ab2-132">たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="30ab2-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="30ab2-133">**ユーザー ID:** `user`</span><span class="sxs-lookup"><span data-stu-id="30ab2-133">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="30ab2-134">**パスワード:** `******`</span><span class="sxs-lookup"><span data-stu-id="30ab2-134">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="30ab2-135">**パスワードのパスワード:** `******`</span><span class="sxs-lookup"><span data-stu-id="30ab2-135">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="30ab2-136">関連アプリケーションが [BizTalk Adapter for PeopleSoft Enterprise トランスポートのプロパティ] ダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="30ab2-136">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ab2-137">参照</span><span class="sxs-lookup"><span data-stu-id="30ab2-137">See Also</span></span>  
 [<span data-ttu-id="30ab2-138">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="30ab2-138">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)