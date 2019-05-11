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
ms.openlocfilehash: ca67c8637f3738169e9818795eebefd9faeabe70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390007"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="f82a5-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="f82a5-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="f82a5-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-103">The following steps show how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f82a5-104">SSO エラーが発生した場合は、ときに使用したドメイン アカウントを BizTalk Server を構成するように、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-104">If you receive SSO errors, verify that you used a domain account when you were configuring BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="f82a5-105">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-105">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="f82a5-106">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="f82a5-107">コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="f82a5-108">コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="f82a5-109">例 :</span><span class="sxs-lookup"><span data-stu-id="f82a5-109">For example:</span></span>  
  
    <span data-ttu-id="f82a5-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="f82a5-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="f82a5-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="f82a5-112">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="f82a5-112">For a list of commands, use the **-help** switch.</span></span>  
  
    <span data-ttu-id="f82a5-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span><span class="sxs-lookup"><span data-stu-id="f82a5-113">![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")</span></span>  
  
4. <span data-ttu-id="f82a5-114">使用して関連アプリケーションを作成する \* です。開始、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="f82a5-115">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f82a5-115">where:</span></span>  
  
   - <span data-ttu-id="f82a5-116">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f82a5-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="f82a5-117">AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="f82a5-117">AffiliateApplication.xml is the application XML you created that contains the sign-on information.</span></span>  
  
     <span data-ttu-id="f82a5-118">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-118">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="f82a5-119">シングル サインオン チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-119">Create Single Sign-On Tickets</span></span>  
  
1.  <span data-ttu-id="f82a5-120">SSO チケットの動作を制御する次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="f82a5-121">質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="f82a5-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="f82a5-122">完了時に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f82a5-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="f82a5-123">**このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="f82a5-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-the-affiliate-application-xml"></a><span data-ttu-id="f82a5-124">関連アプリケーション XML を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f82a5-124">Enable the Affiliate Application XML</span></span>  
  
1.  <span data-ttu-id="f82a5-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp PeopleSoftApp`  
  
2.  <span data-ttu-id="f82a5-126">アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="f82a5-127">使用可能な関連アプリケーションは、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f82a5-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="f82a5-128">**Ibi \yourid-peoplesoftapp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="f82a5-128">**Applications available for IBI\YourID - PeopleSoftApp**</span></span>  
  
3.  <span data-ttu-id="f82a5-129">関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials PeopleSoftApp`  
  
4.  <span data-ttu-id="f82a5-130">ユーザー名と、プロンプトでパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="f82a5-131">PeopleSoftApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-131">Enter the logon credentials for the PeopleSoftApp affiliate application.</span></span>  
  
     <span data-ttu-id="f82a5-132">たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f82a5-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="f82a5-133">**ユーザー ID:** `user`</span><span class="sxs-lookup"><span data-stu-id="f82a5-133">**User ID:** `user`</span></span>  
  
    -   <span data-ttu-id="f82a5-134">**パスワード:** `******`</span><span class="sxs-lookup"><span data-stu-id="f82a5-134">**Password:** `******`</span></span>  
  
    -   <span data-ttu-id="f82a5-135">**確認しますか。パスワード:** `******`</span><span class="sxs-lookup"><span data-stu-id="f82a5-135">**Confirm? Password:** `******`</span></span>  
  
5.  <span data-ttu-id="f82a5-136">関連アプリケーションは、BizTalk Adapter for PeopleSoft Enterprise トランスポートのプロパティ ダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f82a5-136">The affiliate application appears in the BizTalk Adapter for PeopleSoft Enterprise Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82a5-137">参照</span><span class="sxs-lookup"><span data-stu-id="f82a5-137">See Also</span></span>  
 [<span data-ttu-id="f82a5-138">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="f82a5-138">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)