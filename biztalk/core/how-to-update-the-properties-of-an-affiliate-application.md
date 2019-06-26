---
title: 関連アプリケーションのプロパティを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], updating properties
- applications [SSO], properties
ms.assetid: b06eefdd-a5ca-4a32-93d7-72246e31a2e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6c50664fcf9e87ed6980a031fed980bf1e01301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333662"
---
# <a name="how-to-update-the-properties-of-an-affiliate-application"></a><span data-ttu-id="f7f81-102">関連アプリケーションのプロパティを更新する方法</span><span class="sxs-lookup"><span data-stu-id="f7f81-102">How to Update the Properties of an Affiliate Application</span></span>
<span data-ttu-id="f7f81-103">MMC スナップインまたはこのコマンドを使用して、XML ファイルで指定したとおり、1 つまたは複数のアプリケーション プロパティを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="f7f81-103">You can use the MMC Snap-In or this command to update one or more application properties, as specified by the XML file.</span></span> <span data-ttu-id="f7f81-104">このタスクを実行する関連管理者があります。</span><span class="sxs-lookup"><span data-stu-id="f7f81-104">You must be an Affiliate Administrator to perform this task.</span></span> <span data-ttu-id="f7f81-105">次に更新するフィールドを表示する XML ファイルの例を示します。</span><span class="sxs-lookup"><span data-stu-id="f7f81-105">The following is an example XML file that lists the fields you can update.</span></span>  
  
```  
<SSO>  
<application name="SSOApplication">  
<description>An SSO Application</description>  
<contact>someone@companyname.com</contact>  
<appUserAccount>DomainName\AppUserGroup</appUserAccount>  
<appAdminAccount>DomainName\AppAdminGroup</appAdminAccount>  
<flags allowTickets="no" validateTickets="yes"  timeoutTickets="yes" enableApp="no" />  
</application>  
</SSO>  
  
```  
  
 <span data-ttu-id="f7f81-106">関連アプリケーションを作成した後は、次のプロパティを変更できません。</span><span class="sxs-lookup"><span data-stu-id="f7f81-106">After you create an affiliate application, you cannot modify the following properties:</span></span>  
  
-   <span data-ttu-id="f7f81-107">関連アプリケーションの名前</span><span class="sxs-lookup"><span data-stu-id="f7f81-107">Name of the affiliate application</span></span>  
  
-   <span data-ttu-id="f7f81-108">関連アプリケーションに関連付けられたフィールド</span><span class="sxs-lookup"><span data-stu-id="f7f81-108">Fields associated with the affiliate application</span></span>  
  
-   <span data-ttu-id="f7f81-109">関連アプリケーションの種類 (ホスト グループ、単独、構成ストア)</span><span class="sxs-lookup"><span data-stu-id="f7f81-109">Affiliate application type (host group, individual, or configuration store)</span></span>  
  
-   <span data-ttu-id="f7f81-110">関連管理者グループと同じ管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="f7f81-110">Administration account same as affiliate administrators group.</span></span> <span data-ttu-id="f7f81-111">(このフラグを指定すると、この関連アプリケーションの管理者アカウントとして常に関連管理者グループが使用されます)</span><span class="sxs-lookup"><span data-stu-id="f7f81-111">(Specifying this flag will always use the affiliate administrators group as the administrator account for this affiliate application)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7f81-112">allowLocalAccounts フラグを yes に設定すると、管理アカウントとユーザー アカウントにローカル アカウントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7f81-112">You can use local accounts for the administration account and user account by setting the allowLocalAccounts flag to yes.</span></span> <span data-ttu-id="f7f81-113">ただし、このフラグは、1 台のコンピューターのシナリオでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7f81-113">However, you can only use this flag in single-computer scenarios.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7f81-114">SSO 管理者、SSO 関連管理者、またはアプリケーション管理者にこのタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f81-114">You must be an SSO administrator, SSO affiliate administrator, or application administrator to perform this task.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7f81-115">チケット フラグ (validateTickets と timeoutTickets) を変更する SSO 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7f81-115">You must be an SSO administrator to modify the ticketing flags (validateTickets and timeoutTickets).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7f81-116">SSO 関連アプリケーションの管理アカウントを変更するには管理者または SSO 管理者があります。</span><span class="sxs-lookup"><span data-stu-id="f7f81-116">You must be an SSO administrator or an SSO affiliate administrator to modify the application administration account.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="f7f81-117">MMC スナップインを使用して関連アプリケーションのプロパティを更新するには</span><span class="sxs-lookup"><span data-stu-id="f7f81-117">To update the properties of an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="f7f81-118">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="f7f81-118">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="f7f81-119">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="f7f81-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="f7f81-120">関連アプリケーションを右クリックし、 **Update**します。</span><span class="sxs-lookup"><span data-stu-id="f7f81-120">Right-click the affililate application, and then click **Update**.</span></span>  
  
### <a name="to-update-the-properties-of-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="f7f81-121">コマンドラインを使用して関連アプリケーションのプロパティを更新するには</span><span class="sxs-lookup"><span data-stu-id="f7f81-121">To update the properties of an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="f7f81-122">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="f7f81-122">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="f7f81-123">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7f81-123">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="f7f81-124">既定のインストール ディレクトリは **\<ドライブ\>** : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="f7f81-124">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="f7f81-125">型**ssomanage – updateapps\<アプリケーション ファイル名\>** アプリケーション ファイル名は、XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="f7f81-125">Type **ssomanage –updateapps \<application file name\>**, where the application file name is the XML file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7f81-126">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7f81-126">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f81-127">参照</span><span class="sxs-lookup"><span data-stu-id="f7f81-127">See Also</span></span>  
 <span data-ttu-id="f7f81-128">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f7f81-128">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="f7f81-129">[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="f7f81-129">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="f7f81-130">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="f7f81-130">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="f7f81-131">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="f7f81-131">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)