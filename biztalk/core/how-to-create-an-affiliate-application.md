---
title: "関連アプリケーションを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], creating
- applications [SSO], creating
- creating, applications [SSO]
ms.assetid: d0967c4b-6201-416a-9d3a-23b5de5b83d6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d36fa977c7da90c3f894dd1153799008459c1feb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-an-affiliate-application"></a><span data-ttu-id="aae6a-102">関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="aae6a-102">How to Create an Affiliate Application</span></span>
<span data-ttu-id="aae6a-103">MMC スナップインまたはここで示すコマンドを使用すると、XML ファイルで指定された 1 つ以上のアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="aae6a-103">You can use the MMC Snap-In or this command to create one or more applications, as specified by the XML file.</span></span> <span data-ttu-id="aae6a-104">Windows 側開始 SSO の XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="aae6a-104">An example XML file for Windows Initiated SSO is:</span></span>  
  
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
  
 <span data-ttu-id="aae6a-105">関連アプリケーションを作成した後は、次のプロパティを変更できません。</span><span class="sxs-lookup"><span data-stu-id="aae6a-105">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="aae6a-106">関連アプリケーションの名前</span><span class="sxs-lookup"><span data-stu-id="aae6a-106">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="aae6a-107">関連アプリケーションに関連付けられたフィールド</span><span class="sxs-lookup"><span data-stu-id="aae6a-107">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="aae6a-108">関連アプリケーションの種類 (ホスト グループ、単独、構成ストア)</span><span class="sxs-lookup"><span data-stu-id="aae6a-108">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="aae6a-109">関連管理者グループと同じ管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="aae6a-109">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="aae6a-110">(このフラグを指定すると、この関連アプリケーションの管理者アカウントとして常に関連管理者グループが使用されます)</span><span class="sxs-lookup"><span data-stu-id="aae6a-110">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aae6a-111">allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="aae6a-111">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="aae6a-112">ただし、このフラグは 1 台のコンピューターのシナリオ以外では使用できません。</span><span class="sxs-lookup"><span data-stu-id="aae6a-112">However, you should only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aae6a-113">この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aae6a-113">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
 <span data-ttu-id="aae6a-114">関連アプリケーションは作成した後で有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="aae6a-114">After you create the affiliate application, you must enable it.</span></span> <span data-ttu-id="aae6a-115">詳細については、次を参照してください。[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="aae6a-115">For more information, see [How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md).</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="aae6a-116">MMC スナップインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="aae6a-116">To create an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="aae6a-117">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="aae6a-117">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="aae6a-118">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="aae6a-118">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="aae6a-119">右クリック**関連アプリケーション**、クリックして**アプリケーションの作成**です。</span><span class="sxs-lookup"><span data-stu-id="aae6a-119">Right-click **Affiliate Applications**, and then click **Create Application**.</span></span>  
  
4.  <span data-ttu-id="aae6a-120">指示に従って、**エンタープライズ シングル サインオン アプリケーション ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="aae6a-120">Follow the instructions in the **Enterprise Single Sign-On Application Wizard**.</span></span>  
  
### <a name="to-create-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="aae6a-121">コマンド ラインを使用して関連アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="aae6a-121">To create an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="aae6a-122">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="aae6a-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="aae6a-123">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="aae6a-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="aae6a-124">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="aae6a-124">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="aae6a-125">型**ssomanage – createapps」と入力*\<アプリケーション ファイル名 >***ここで、 *\<アプリケーション ファイル名 >* XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="aae6a-125">Type **ssomanage –createapps *\<application file name>***, where *\<application file name>* is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aae6a-126">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="aae6a-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aae6a-127">参照</span><span class="sxs-lookup"><span data-stu-id="aae6a-127">See Also</span></span>  
 <span data-ttu-id="aae6a-128">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="aae6a-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="aae6a-129">[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="aae6a-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="aae6a-130">[関連アプリケーションを削除する方法](../core/how-to-delete-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="aae6a-130">[How to Delete an Affiliate Application](../core/how-to-delete-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="aae6a-131">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="aae6a-131">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="aae6a-132">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="aae6a-132">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)