---
title: 関連の TIBCO Rendezvous のアプリケーションを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f3603fcb-3594-460b-b74a-618e22d9c4e0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba94161fa534187392e64e6138b6f8ae18920377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354022"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="2b5fe-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="2b5fe-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="2b5fe-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-103">The following steps describe how to start working with affiliate applications and Single Sign-On (SSO).</span></span> <span data-ttu-id="2b5fe-104">エンタープライズ シングル サインオンを使用する方法については、Microsoft のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-104">For complete information about how to use Enterprise Single Sign-On, see the Microsoft documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b5fe-105">SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-105">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="2b5fe-106">ドメイン アカウントでの SSO のみ機能します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-106">SSO only functions under a domain account.</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="2b5fe-107">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-107">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="2b5fe-108">コントロール パネルで、開く**サービス**、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-108">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="2b5fe-109">コマンド プロンプトでは、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-109">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span> <span data-ttu-id="2b5fe-110">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-110">For example:</span></span>  
  
     <span data-ttu-id="2b5fe-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span><span class="sxs-lookup"><span data-stu-id="2b5fe-111">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="2b5fe-112">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-112">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="2b5fe-113">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-113">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="2b5fe-114">使用して関連アプリケーションを作成する \* です。開始、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-114">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="2b5fe-115">各要素の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-115">Where:</span></span>  
  
     <span data-ttu-id="2b5fe-116">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-116">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
     <span data-ttu-id="2b5fe-117">AffiliateApplication.xml は、アプリケーションを作成したシングル サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-117">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="2b5fe-118">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-118">For example:</span></span>  
  
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
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="2b5fe-119">シングル サインオン チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="2b5fe-120">SSO チケットの動作を制御する次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="2b5fe-121">ように、次の質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-121">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
3.  <span data-ttu-id="2b5fe-122">完了時に、次の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-122">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="2b5fe-123">**このコンピューターでは、SSO サーバーを使用します。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="2b5fe-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="2b5fe-124">関連アプリケーション XML を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="2b5fe-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO RendezvousApp`  
  
2.  <span data-ttu-id="2b5fe-126">アプリケーションを一覧表示し、アプリケーションが作成されたことを確認するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="2b5fe-127">使用可能な関連アプリケーションは、一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-127">The affiliate applications that are available for use appear in a list.</span></span>  
  
     <span data-ttu-id="2b5fe-128">**Ibi \YOURID-TIBCO RendezvousApp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="2b5fe-128">**Applications available for IBI\YourID - TIBCO RendezvousApp**</span></span>  
  
3.  <span data-ttu-id="2b5fe-129">関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials TIBCO RendezvousApp`  
  
4.  <span data-ttu-id="2b5fe-130">ユーザー名と、プロンプトでパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-130">Enter the User name and password at the prompts.</span></span>  
  
5.  <span data-ttu-id="2b5fe-131">TIBCO RendezvousApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-131">Enter the logon credentials for the TIBCO RendezvousApp affiliate application.</span></span>  
  
     <span data-ttu-id="2b5fe-132">たとえば、ユーザー id と、SSO サーバーを使用してシステムに入力するユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-132">For example, enter the user identification and the password for the user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="2b5fe-133">ユーザー ID: ユーザー</span><span class="sxs-lookup"><span data-stu-id="2b5fe-133">User ID: user</span></span>  
  
    -   <span data-ttu-id="2b5fe-134">パスワード: \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2b5fe-134">Password: \*\*\*\*\*\*</span></span>  
  
    -   <span data-ttu-id="2b5fe-135">パスワードの確認入力: \* \* \*</span><span class="sxs-lookup"><span data-stu-id="2b5fe-135">Confirm Password: \*\*\*\*\*\*</span></span>  
  
6.  <span data-ttu-id="2b5fe-136">BizTalk adapter for TIBCO Rendezvous の関連アプリケーションが表示されます**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="2b5fe-136">The affiliate application appears in the BizTalk Adapter for TIBCO Rendezvous **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5fe-137">参照</span><span class="sxs-lookup"><span data-stu-id="2b5fe-137">See Also</span></span>  
 [<span data-ttu-id="2b5fe-138">BizTalk Adapter for TIBCO Rendezvous のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="2b5fe-138">Security in BizTalk Adapter for TIBCO Rendezvous</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)   