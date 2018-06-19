---
title: 関連アプリケーションを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3be483f8-2617-459e-9081-aab886c75d93
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5145111b2c585edab92cc10c3e3614e8bb91a85d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250990"
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="cb6ac-102">関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cb6ac-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="cb6ac-103">MMC スナップインを使用することができます、または**createapps」と入力**XML ファイルで指定された、1 つまたは複数のアプリケーションを作成するコマンド。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-103">You can use the MMC Snap-In or the **createapps** command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="cb6ac-104">XML ファイルの Windows-Initiated シングル サインオン (SSO) の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-104">The following is an example XML file for Windows-Initiated Single Sign-On (SSO):</span></span>  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no" configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 <span data-ttu-id="cb6ac-105">関連アプリケーションを作成した後は、次のプロパティを変更できません。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="cb6ac-106">関連アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-106">Name of the affiliate application.</span></span>  
  
-   <span data-ttu-id="cb6ac-107">関連アプリケーションに関連付けられているフィールドです。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-107">Fields associated with the affiliate application.</span></span>  
  
-   <span data-ttu-id="cb6ac-108">関連アプリケーションの種類 (ホスト グループ、個人の場合、または構成ストア)。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-108">Affiliate application type (host group, individual, or configuration store).</span></span>  
  
-   <span data-ttu-id="cb6ac-109">関連管理者グループと同じ管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="cb6ac-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="cb6ac-110">(このフラグを指定するは常に使用関連管理者グループ アカウントの administrator としてこの関連アプリケーションの)。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application.)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb6ac-111">allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="cb6ac-112">ただし、このフラグは 1 台のコンピューターのシナリオ以外では使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cb6ac-113">この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb6ac-114">ドメイン コント ローラーで、構成を実行して、ドメイン ローカル スコープのグループが関連アプリケーションの作成中にアプリケーションの管理者またはアプリケーションのユーザーの指定された場合は、ローカル アカウントのフラグを有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-114">If you are performing the configuration on a Domain Controller, and the Domain Local scope groups are specified for Application Administrators or Application Users while creating Affiliate Applications, it is recommended that you enable the local account flag.</span></span> <span data-ttu-id="cb6ac-115">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="cb6ac-115">To do this:</span></span>  
  
-   <span data-ttu-id="cb6ac-116">MMC スナップインでは、作成プロセス中にアクセス アカウントを許可するローカル アカウントを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-116">In the MMC Snap-in, select Allow local accounts for access accounts during the creation process.</span></span>  
  
-   <span data-ttu-id="cb6ac-117">コマンドラインから指定 allowLocalAccounts 関連アプリケーションの作成用の XML ファイルで = [はい] です。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-117">From the command line, specify allowLocalAccounts=yes in the XML file for Affiliate Application creation.</span></span>  
  
 <span data-ttu-id="cb6ac-118">関連アプリケーションは作成した後で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-118">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="cb6ac-119">詳細については、次を参照してください。[関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-119">For more information, see [How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-microsoft-management-console-mmc-snap-in"></a><span data-ttu-id="cb6ac-120">Microsoft 管理コンソール (MMC) スナップインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="cb6ac-120">To create an affiliate application using the Microsoft Management Console (MMC) Snap-In</span></span>  
  
1.  <span data-ttu-id="cb6ac-121">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-121">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="cb6ac-122">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-122">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="cb6ac-123">右クリック**関連アプリケーション**、クリックして**新規**です。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-123">Right-click **Affiliate Applications**, and then click **New**.</span></span>  
  
4.  <span data-ttu-id="cb6ac-124">指示に従って、**新しい関連アプリケーションの作成**ウィザード。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-124">Follow the instructions in the **Create New Affiliate Application** wizard.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="cb6ac-125">コマンド ラインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="cb6ac-125">To create an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="cb6ac-126">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-126">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="cb6ac-127">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-127">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="cb6ac-128">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-128">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="cb6ac-129">型`ssomanage –createapps <application file name>`ここで、 *\<アプリケーション ファイル名 >* XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-129">Type `ssomanage –createapps <application file name>`, where *\<application file name>* is the XML file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6ac-130">参照</span><span class="sxs-lookup"><span data-stu-id="cb6ac-130">See Also</span></span>  
 <span data-ttu-id="cb6ac-131">[SSO 関連アプリケーション](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cb6ac-131">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="cb6ac-132">[関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="cb6ac-132">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="cb6ac-133">[関連アプリケーションを削除する方法](../esso/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="cb6ac-133">[How to Delete an Affiliate Application](../esso/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="cb6ac-134">[ユーザー マッピングを管理します。](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="cb6ac-134">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="cb6ac-135">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="cb6ac-135">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)