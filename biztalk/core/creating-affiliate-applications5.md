---
title: TIBCO EMS 用の関連アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 191e5b56-dab9-4bf3-9f89-a900907d64e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 325b663f569b9cfce6fab8a65cc8b1f400d9d263
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353929"
---
# <a name="create-affiliate-applications"></a><span data-ttu-id="ea62e-102">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-102">Create Affiliate Applications</span></span>
<span data-ttu-id="ea62e-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea62e-104">SSO エラーが発生した場合は、BizTalk Server を構成したときに、ドメイン アカウントを使用したことを確認します。これは、エンタープライズ SSO サービスの機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="ea62e-105">ドメイン アカウントでの SSO のみ関数</span><span class="sxs-lookup"><span data-stu-id="ea62e-105">SSO only functions under a domain account</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="ea62e-106">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-106">Create an affiliate application</span></span>  
  
1. <span data-ttu-id="ea62e-107">コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2. <span data-ttu-id="ea62e-108">コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
    <span data-ttu-id="ea62e-109">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-109">For example:</span></span>  
  
    <span data-ttu-id="ea62e-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="ea62e-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3. <span data-ttu-id="ea62e-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="ea62e-112">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="ea62e-112">For a list of commands, use the **-help** switch.</span></span>  
  
4. <span data-ttu-id="ea62e-113">使用して関連アプリケーションを作成する \* です。開始、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-113">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
    `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
    <span data-ttu-id="ea62e-114">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea62e-114">where:</span></span>  
  
   - <span data-ttu-id="ea62e-115">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ea62e-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
   - <span data-ttu-id="ea62e-116">AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="ea62e-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="ea62e-117">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-117">For example:</span></span>  
  
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
  
   <span data-ttu-id="ea62e-118">XML の例を使用すると、関連アプリケーションは、TIBCO EMS のアプリは、コマンド プロンプトで示すように値を格納します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="ea62e-119">シングル サインオン チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="ea62e-120">SSO チケットの動作を制御する次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="ea62e-121">質問に答えます。</span><span class="sxs-lookup"><span data-stu-id="ea62e-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="ea62e-122">完了時に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea62e-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="ea62e-123">**このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="ea62e-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="ea62e-124">関連アプリケーション XML を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ea62e-124">Enable affiliate application XML</span></span>  
  
1. <span data-ttu-id="ea62e-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-125">Type the following command:</span></span>  
  
    `ssomanage -enableapp TIBCO EMSApp`  
  
2. <span data-ttu-id="ea62e-126">アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
    `ssoclient.exe –listapps`  
  
    <span data-ttu-id="ea62e-127">使用可能な関連アプリケーションは、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea62e-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
    <span data-ttu-id="ea62e-128">**Ibi \YOURID-TIBCO EMSApp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="ea62e-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3. <span data-ttu-id="ea62e-129">関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-129">Type the following command to set the affiliate application credentials:</span></span>  
  
    `soclient.exe -setcredentials TIBCO EMSApp`  
  
4. <span data-ttu-id="ea62e-130">ユーザー名と、プロンプトでパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="ea62e-131">TIBCO EMS App 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
    <span data-ttu-id="ea62e-132">たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea62e-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
   - <span data-ttu-id="ea62e-133">ユーザー ID:**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="ea62e-133">User ID: **user**</span></span>  
  
   - <span data-ttu-id="ea62e-134">パスワード: `******`</span><span class="sxs-lookup"><span data-stu-id="ea62e-134">Password: `******`</span></span>  
  
   - <span data-ttu-id="ea62e-135">確認しますか。</span><span class="sxs-lookup"><span data-stu-id="ea62e-135">Confirm?</span></span> <span data-ttu-id="ea62e-136">パスワード: `******`</span><span class="sxs-lookup"><span data-stu-id="ea62e-136">Password: `******`</span></span>  
  
     <span data-ttu-id="ea62e-137">BizTalk adapter for TIBCO EMS の関連アプリケーションが表示されます**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ea62e-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea62e-138">参照</span><span class="sxs-lookup"><span data-stu-id="ea62e-138">See Also</span></span>  
[<span data-ttu-id="ea62e-139">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ea62e-139">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)