---
title: "Applications3 関連の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- affiliate applications
- Single Sign-On, creating tickets
- tickets, creating Single Sign-On
- affiliate applications, creating
- SSO tickets
ms.assetid: 800644fd-2286-4e59-894b-260f584dd29f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 857ee7edd623332e72176ac09082f0ec9fc460f4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="0db05-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="0db05-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="0db05-103">次の手順では、シングル サインオン (SSO) を使用して関連アプリケーションを利用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0db05-103">The following steps describe how to get started with affiliate applications using Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0db05-104">SSO エラーが発生した場合は、BizTalk Server を構成したときにドメイン アカウントを使用したことを確認してください。これは、そのことが ESSO サービスの機能に影響するからです。</span><span class="sxs-lookup"><span data-stu-id="0db05-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the ESSO service.</span></span> <span data-ttu-id="0db05-105">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="0db05-105">SSO only functions under a domain account.</span></span>  
  
## <a name="creating-an-affiliate-application"></a><span data-ttu-id="0db05-106">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="0db05-106">Creating an Affiliate Application</span></span>  
  
#### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="0db05-107">関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="0db05-107">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="0db05-108">**コントロール パネルの **、開かれている**Services**、エンタープライズ シングル サインオン サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0db05-108">In **Control Panel**, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="0db05-109">コマンド プロンプトで、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="0db05-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="0db05-110">例:</span><span class="sxs-lookup"><span data-stu-id="0db05-110">For example:</span></span>  
  
     <span data-ttu-id="0db05-111">**C:\Program files \common files \enterprise でのシングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="0db05-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="0db05-112">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0db05-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="0db05-113">コマンドの一覧を表示するには、-help スイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="0db05-113">For a list of commands, use the -help switch.</span></span>  
  
     ![](../core/media/siebeladapter-23-sso-commands.gif "SiebelAdapter_23_SSO_Commands")  
  
4.  <span data-ttu-id="0db05-114">使用して関連アプリケーションを作成する、* です。始まりとしての XML は、次のコマンドに入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-114">To create the affiliate application using the *.XML as a beginning, type in the following command:</span></span>  
  
     <span data-ttu-id="0db05-115">**C:\SSOtest\AffiliateApplication.xml を ssomanage.exe createapps」と入力**</span><span class="sxs-lookup"><span data-stu-id="0db05-115">**ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml**</span></span>  
  
     <span data-ttu-id="0db05-116">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0db05-116">where:</span></span>  
  
     <span data-ttu-id="0db05-117">C:\SSOtest は、アプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="0db05-117">C:\SSOtest is the folder containing your application XML.</span></span>  
  
     <span data-ttu-id="0db05-118">AffiliateApplication.xml は、アプリケーションのサインオン情報を含むを作成した XML です。</span><span class="sxs-lookup"><span data-stu-id="0db05-118">AffiliateApplication.xml is the application XML you created containing the Sign On information.</span></span>  
  
     <span data-ttu-id="0db05-119">例:</span><span class="sxs-lookup"><span data-stu-id="0db05-119">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
         <application name="JDEdwardsApp">  
              <description>JDEdwards SSO Application</description>  
              <contact>someone@microsoft.com</contact>  
              <userGroup>ibi\Domain Users</userGroup>  
              <!—-an existing group on the domain controller - >   
              <appAdminGroup>ibi\YourID</appAdminGroup>  
              <!-- an existing account within the domain group - >   
              <field ordinal="0" label="User ID" masked="no" />  
              <field ordinal="1" label="Password" masked="yes" />  
              <flags groupApp="no" allowTickets="yes" enableApp="yes"/>  
         </application>  
    </SSO>  
    ```  
  
## <a name="creating-single-sign-on-tickets"></a><span data-ttu-id="0db05-120">シングル サインオン チケットの作成</span><span class="sxs-lookup"><span data-stu-id="0db05-120">Creating Single Sign-On Tickets</span></span>  
  
#### <a name="to-create-sso-tickets"></a><span data-ttu-id="0db05-121">SSO チケットを作成するには</span><span class="sxs-lookup"><span data-stu-id="0db05-121">To create SSO tickets</span></span>  
  
1.  <span data-ttu-id="0db05-122">次のコマンドを入力して、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="0db05-122">Type in the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="0db05-123">次の質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="0db05-123">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="0db05-124">完了すると、次の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0db05-124">On completion you receive a confirmation:</span></span>  
  
     <span data-ttu-id="0db05-125">**このコンピューターで使用中の SSO。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="0db05-125">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enabling-the-affiliate-application-xml"></a><span data-ttu-id="0db05-126">関連アプリケーション XML の有効化</span><span class="sxs-lookup"><span data-stu-id="0db05-126">Enabling the Affiliate Application XML</span></span>  
  
#### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="0db05-127">関連アプリケーション XML を有効にするには</span><span class="sxs-lookup"><span data-stu-id="0db05-127">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="0db05-128">次のコマンドに入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-128">Type in the following command:</span></span>  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  <span data-ttu-id="0db05-129">アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドに入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-129">Type in the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="0db05-130">使用可能な関連アプリケーションは、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0db05-130">The Affiliate Applications available for use appear in a list.</span></span>  
  
     <span data-ttu-id="0db05-131">**Ibi \yourid-jdedwardsapp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="0db05-131">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3.  <span data-ttu-id="0db05-132">次のコマンドを入力して、関連アプリケーションの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0db05-132">Type in the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  <span data-ttu-id="0db05-133">プロンプトで、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-133">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="0db05-134">JDEdwardsApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-134">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span> <span data-ttu-id="0db05-135">たとえば、ユーザー id と、SSO サーバーにより、システムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="0db05-135">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="0db05-136">**ユーザー ID:**ユーザー</span><span class="sxs-lookup"><span data-stu-id="0db05-136">**User ID:** user</span></span>  
  
    -   <span data-ttu-id="0db05-137">**パスワード:** ******</span><span class="sxs-lookup"><span data-stu-id="0db05-137">**Password:** ******</span></span>  
  
    -   <span data-ttu-id="0db05-138">**パスワードのパスワード:** ******</span><span class="sxs-lookup"><span data-stu-id="0db05-138">**Confirm? Password:** ******</span></span>  
  
5.  <span data-ttu-id="0db05-139">関連アプリケーションが [BizTalk Adapter for JD Edwards OneWorld トランスポートのプロパティ] ダイアログ ボックスのドロップダウン リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0db05-139">The affiliate application appears in the drop-down list of the BizTalk Adapter for JD Edwards OneWorld Transport Properties dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0db05-140">参照</span><span class="sxs-lookup"><span data-stu-id="0db05-140">See Also</span></span>  
 [<span data-ttu-id="0db05-141">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="0db05-141">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)