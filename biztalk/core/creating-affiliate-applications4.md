---
title: Applications4 関連の作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets, Single Sign-On
- affiliate applications, setting credentials
- affiliate applications
- Single Sign-On, creating tickets
- SSO tickets
ms.assetid: 790fbe21-8081-4d57-803f-23014c8a3135
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87aa9be716e437e80c0e85bd9e462713e48090ad
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "24015089"
---
# <a name="creating-affiliate-applications"></a><span data-ttu-id="67ea1-102">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="67ea1-102">Creating Affiliate Applications</span></span>
<span data-ttu-id="67ea1-103">次の手順では、SSO を使用して関連アプリケーションを利用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-103">The following steps describe how to get started with affiliate applications using SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67ea1-104">SSO エラーが発生した場合を使用したドメイン アカウント、BizTalk Server を構成したときにこれは、エンタープライズ SSO サービスの機能に影響を確認します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-104">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="67ea1-105">SSO はドメイン アカウントでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-105">SSO only functions under a domain account.</span></span>  
  
### <a name="to-create-an-affiliate-application"></a><span data-ttu-id="67ea1-106">関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="67ea1-106">To create an affiliate application</span></span>  
  
1.  <span data-ttu-id="67ea1-107">コントロール パネルで、開く **サービス**, 、エンタープライズ シングル サインオン サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-107">In Control Panel, open **Services**, and verify that the Enterprise Single Sign-On service is running.</span></span>  
  
2.  <span data-ttu-id="67ea1-108">コマンド プロンプトで、ディレクトリをエンタープライズ シングル サインオン フォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-108">In a command prompt, change directories to the Enterprise Single Sign On folder.</span></span>  
  
     <span data-ttu-id="67ea1-109">例:</span><span class="sxs-lookup"><span data-stu-id="67ea1-109">For example:</span></span>  
  
     <span data-ttu-id="67ea1-110">**C:\Program files \common files files \common files \enterprise シングル サインオン >**</span><span class="sxs-lookup"><span data-stu-id="67ea1-110">**C:\Program Files\Common Files\Enterprise Single Sign-On>**</span></span>  
  
3.  <span data-ttu-id="67ea1-111">エンタープライズ シングル サインオン コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-111">Use the Enterprise Single Sign-On commands.</span></span> <span data-ttu-id="67ea1-112">コマンドの一覧を表示するには、使用、 **-ヘルプ** 切り替えます。</span><span class="sxs-lookup"><span data-stu-id="67ea1-112">For a list of commands, use the **-help** switch.</span></span>  
  
4.  <span data-ttu-id="67ea1-113">\*.XML を基にして関連アプリケーションを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-113">To create the affiliate application using \*.XML as a beginning, type the following command:</span></span>  
  
     `ssomanage.exe -createapps C:\SSOtest\AffiliateApplication.xml`  
  
     <span data-ttu-id="67ea1-114">それぞれの文字の説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="67ea1-114">where:</span></span>  
  
    -   <span data-ttu-id="67ea1-115">C:\SSOtest はアプリケーション XML を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="67ea1-115">C:\SSOtest is the folder that contains your application XML.</span></span>  
  
    -   <span data-ttu-id="67ea1-116">AffiliateApplication.xml は、アプリケーションを作成した、サインオン情報を含む XML です。</span><span class="sxs-lookup"><span data-stu-id="67ea1-116">AffiliateApplication.xml is the application XML you created that contains the Sign-On information.</span></span>  
  
     <span data-ttu-id="67ea1-117">例:</span><span class="sxs-lookup"><span data-stu-id="67ea1-117">For example:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <SSO>  
        <application name="JDEdwardsApp">  
            <description>JDEdwards SSO Application</description>  
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
  
### <a name="to-create-single-sign-on-tickets"></a><span data-ttu-id="67ea1-118">シングル サインオン チケットを作成するには</span><span class="sxs-lookup"><span data-stu-id="67ea1-118">To create Single Sign-On tickets</span></span>  
  
1.  <span data-ttu-id="67ea1-119">次のコマンドを入力し、SSO チケットの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-119">Type the following command to control SSO ticket behavior:</span></span>  
  
     `ssomanage.exe -tickets yes yes`  
  
2.  <span data-ttu-id="67ea1-120">表示される次の質問に応答します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-120">Answer the following questions as shown:</span></span>  
  
     `ssomanage -tickets <allowed yes | no> <validate yes | no>`  
  
     <span data-ttu-id="67ea1-121">完了時に、次の確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67ea1-121">On completion, you receive the following confirmation:</span></span>  
  
     <span data-ttu-id="67ea1-122">**このコンピューターで使用中の SSO。操作が正常に完了しました。**</span><span class="sxs-lookup"><span data-stu-id="67ea1-122">**Using SSO server on this computer. The operation completed successfully.**</span></span>  
  
### <a name="to-enable-affiliate-application-xml"></a><span data-ttu-id="67ea1-123">関連アプリケーション XML を有効にするには</span><span class="sxs-lookup"><span data-stu-id="67ea1-123">To enable affiliate application XML</span></span>  
  
1.  <span data-ttu-id="67ea1-124">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-124">Type the following command:</span></span>  
  
     `ssomanage -enableapp JDEdwardsApp`  
  
2.  <span data-ttu-id="67ea1-125">次のコマンドを入力してアプリケーションを一覧表示し、アプリケーションが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-125">Type the following command to list the applications and to verify that the application was created:</span></span>  
  
     `ssoclient.exe –listapps`  
  
     <span data-ttu-id="67ea1-126">利用可能な関連アプリケーションは、リストの表示を使用します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-126">The affiliate applications that are available for use display in a list:</span></span>  
  
     <span data-ttu-id="67ea1-127">**Ibi \yourid-jdedwardsapp に使用可能なアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="67ea1-127">**Applications available for IBI\YourID - JDEdwardsApp**</span></span>  
  
3.  <span data-ttu-id="67ea1-128">関連アプリケーションの資格情報を設定するのには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-128">Type the following command to set the affiliate application credentials:</span></span>  
  
     `ssoclient.exe -setcredentials JDEdwardsApp`  
  
4.  <span data-ttu-id="67ea1-129">プロンプトで、ユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-129">Enter the user name and password at the prompts.</span></span> <span data-ttu-id="67ea1-130">JDEdwardsApp 関連アプリケーションのログオン資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-130">Enter the logon credentials for the JDEdwardsApp affiliate application.</span></span>  
  
     <span data-ttu-id="67ea1-131">たとえば、ユーザーの識別と SSO サーバーを経由してシステムに入力するには、そのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="67ea1-131">For example, enter the user identification and the password for that user to enter into the system through the SSO server.</span></span>  
  
    -   <span data-ttu-id="67ea1-132">ユーザー ID: **ユーザー**</span><span class="sxs-lookup"><span data-stu-id="67ea1-132">User ID: **user**</span></span>  
  
    -   <span data-ttu-id="67ea1-133">パスワード: `******`</span><span class="sxs-lookup"><span data-stu-id="67ea1-133">Password: `******`</span></span>  
  
    -   <span data-ttu-id="67ea1-134">確認入力</span><span class="sxs-lookup"><span data-stu-id="67ea1-134">Confirm?</span></span> <span data-ttu-id="67ea1-135">パスワード: `******`</span><span class="sxs-lookup"><span data-stu-id="67ea1-135">Password: `******`</span></span>  
  
     <span data-ttu-id="67ea1-136">BizTalk adapter for JD Edwards EnterpriseOne の関連アプリケーションが表示されます **トランスポートのプロパティ**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="67ea1-136">The affiliate application appears in the BizTalk Adapter for JD Edwards EnterpriseOne **Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67ea1-137">参照</span><span class="sxs-lookup"><span data-stu-id="67ea1-137">See Also</span></span>  
 [<span data-ttu-id="67ea1-138">BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="67ea1-138">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)