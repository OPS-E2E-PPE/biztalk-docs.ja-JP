---
title: TIBCO EMS 用の関連アプリケーションの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: ce5df15794886f9177f12f2a9e9a33e3ffdc335f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015289"
---
# <a name="create-affiliate-applications"></a><span data-ttu-id="6415b-102">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6415b-102">Create Affiliate Applications</span></span>
<span data-ttu-id="6415b-103">次の手順では、関連アプリケーションとシングル サインオン (SSO) の使用を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6415b-103">The following steps describe how to start using affiliate applications and Single Sign-On (SSO).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6415b-104">SSO エラーが発生した場合は、BizTalk Server の構成時にドメイン アカウントを使用したかどうかを確認してください。これは Enterprise SSO サービスの機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="6415b-104">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server; this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="6415b-105">ドメイン アカウントで SSO のみ関数</span><span class="sxs-lookup"><span data-stu-id="6415b-105">SSO only functions under a domain account</span></span>  
  
## <a name="create-an-affiliate-application"></a><span data-ttu-id="6415b-106">関連アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="6415b-106">Create an affiliate application</span></span>  
  
1.  <span data-ttu-id="6415b-107">コントロール パネルで、開く**Services**、エンタープライズ シングル サインオン サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6415b-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="6415b-108">コマンド プロンプトで、エンタープライズ シングル サインオン フォルダーにディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="6415b-108">In a command prompt, change directories to the Enterprise Single Sign-On folder.</span></span>  
  
     <span data-ttu-id="6415b-109">例:</span><span class="sxs-lookup"><span data-stu-id="6415b-109">For example:</span></span>  
  
     <span data-ttu-id="6415b-110">**C:\Program files \common files \enterprise でのシングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="6415b-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="6415b-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6415b-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="6415b-112">コマンドの一覧は、使用、 **-ヘルプ**スイッチします。</span><span class="sxs-lookup"><span data-stu-id="6415b-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="6415b-113">使用して関連アプリケーションを作成する \* です。スタート、として XML では、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-113">To create the affiliate application by using \*.XML as a start, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="6415b-114">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6415b-114">where:</span></span>  
  
    -   <span data-ttu-id="6415b-115">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="6415b-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="6415b-116">AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="6415b-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="6415b-117">例:</span><span class="sxs-lookup"><span data-stu-id="6415b-117">For example:</span></span>  
  
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
  
 <span data-ttu-id="6415b-118">XML の例を使用する場合、関連アプリケーションである TIBCO EMS App には、コマンド プロンプトに表示される値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6415b-118">By using the example XML, the affiliate application, TIBCO EMS App, contains the values as shown in the command prompt.</span></span>  
  
## <a name="create-single-sign-on-tickets"></a><span data-ttu-id="6415b-119">シングル サインオン チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="6415b-119">Create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="6415b-120">次のコマンドを入力し、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="6415b-120">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="6415b-121">次の質問に回答します。</span><span class="sxs-lookup"><span data-stu-id="6415b-121">Answer the questions:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="6415b-122">完了時に、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6415b-122">On completion, you receive a confirmation:</span></span>  
  
     <span data-ttu-id="6415b-123">**このコンピューターで使用中の SSO。操作が完了しました。**</span><span class="sxs-lookup"><span data-stu-id="6415b-123">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
## <a name="enable-affiliate-application-xml"></a><span data-ttu-id="6415b-124">関連アプリケーション XML を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6415b-124">Enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="6415b-125">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-125">Type the following command:</span></span>  
  
     `ssomanage -enableapp TIBCO EMSApp`  
  
2.  <span data-ttu-id="6415b-126">次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6415b-126">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="6415b-127">使用可能な関連アプリケーションが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6415b-127">The affiliate applications that are available for use appear in a list:</span></span>  
  
     <span data-ttu-id="6415b-128">**Ibi \YOURID-TIBCO EMSApp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="6415b-128">**Applications available for IBI\YourID - TIBCO EMSApp**</span></span>  
  
3.  <span data-ttu-id="6415b-129">関連アプリケーションの資格情報を設定するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-129">Type the following command to set the affiliate application credentials:</span></span>  
  
     `soclient.exe -setcredentials TIBCO EMSApp`  
  
4.  <span data-ttu-id="6415b-130">プロンプトで、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-130">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="6415b-131">TIBCO EMS App 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-131">Enter the logon credentials for the TIBCO EMS App affiliate application.</span></span>  
  
     <span data-ttu-id="6415b-132">たとえば、ユーザー id と、SSO サーバーにより、システムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="6415b-132">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="6415b-133">ユーザー ID:**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="6415b-133">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="6415b-134">パスワード:`******`</span><span class="sxs-lookup"><span data-stu-id="6415b-134">Password: `******`</span></span>  
  
    -   <span data-ttu-id="6415b-135">確認入力 </span><span class="sxs-lookup"><span data-stu-id="6415b-135">Confirm?</span></span> <span data-ttu-id="6415b-136">パスワード:`******`</span><span class="sxs-lookup"><span data-stu-id="6415b-136">Password: `******`</span></span>  
  
     <span data-ttu-id="6415b-137">関連アプリケーションは、TIBCO EMS の BizTalk アダプターに表示されます。**トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="6415b-137">The affiliate application appears in the BizTalk Adapter for TIBCO EMS **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6415b-138">参照</span><span class="sxs-lookup"><span data-stu-id="6415b-138">See Also</span></span>  
[<span data-ttu-id="6415b-139">アダプターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="6415b-139">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)