---
title: ユーザー マッピングを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034f587d8c7d87f5fa6aa7e5e33ca4ef147d9f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014387"
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="a9e0c-102">ユーザー マッピングを削除する方法</span><span class="sxs-lookup"><span data-stu-id="a9e0c-102">How to Delete User Mappings</span></span>
<span data-ttu-id="a9e0c-103">以下のコマンドを使用して、XML ファイルで指定された 1 つ以上のユーザー マッピングを削除できます。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="a9e0c-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-104">The following is an example XML file.</span></span>  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
```  
  
 <span data-ttu-id="a9e0c-105">ユーザーが、アプリケーション ユーザー アカウントのメンバーでないか Active Directory に登録されていない場合、このコマンドを使用してユーザー マッピングを SSO データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the SSO database.</span></span>  
  
 <span data-ttu-id="a9e0c-106">ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="a9e0c-107">マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-107">For more information about creating a mapping, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="a9e0c-108">管理ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="a9e0c-108">To delete user mappings using the administration utility</span></span>  
  
1. <span data-ttu-id="a9e0c-109">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="a9e0c-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a9e0c-111">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="a9e0c-112">型<strong>ssomanage – deletemappings *\<ファイル名をマッピング\></strong><em>ここで、 \<</em>ファイル名をマッピング*\>は削除するユーザー マッピングを格納しているファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-112">Type <strong>ssomanage –deletemappings *\<mappings file name\></strong><em>, where \<</em>mappings file name*\> is the name of the file that contains the user mapping(s) you want to delete.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a9e0c-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="a9e0c-114">管理ユーティリティを使用して特定のユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="a9e0c-114">To delete a specific user mapping using the administration utility</span></span>  
  
1. <span data-ttu-id="a9e0c-115">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-115">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="a9e0c-116">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a9e0c-117">既定のインストール ディレクトリは*\<ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-117">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="a9e0c-118">型 **ssomanage – deletemapping *\<ドメイン\>*\\*\<username\> *   *\<アプリケーション名\>**<em>ここで、 *\<ドメイン\></em>が Windows ドメイン ユーザー アカウントの *\<ユーザー名\>* は、Windows ユーザー名と\<* アプリケーション名*\>はユーザー マッピングを削除する特定のアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-118">Type **ssomanage –deletemapping *\<domain\>*\\*\<username\>* *\<application name\>**<em>, where *\<domain\></em> is the Windows domain for the user account, *\<username\>* is the Windows user name, and \<* application name*\> is the specific application for which you want to remove the user mapping.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a9e0c-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="a9e0c-120">クライアント ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="a9e0c-120">To delete a user mapping using the client utility</span></span>  
  
1. <span data-ttu-id="a9e0c-121">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-121">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="a9e0c-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a9e0c-123">既定のインストール ディレクトリは*\<ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-123">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="a9e0c-124">型 * * ssoclient – deletemapping *\<アプリケーション名\>**<em>ここで、*\<アプリケーション名\></em>を削除する関連アプリケーションの名前を指定しますユーザーのマッピング。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-124">Type **ssoclient –deletemapping *\<application name\>**<em>, where *\<application name\></em> is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a9e0c-125">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9e0c-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9e0c-126">参照</span><span class="sxs-lookup"><span data-stu-id="a9e0c-126">See Also</span></span>  
 <span data-ttu-id="a9e0c-127">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a9e0c-127">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="a9e0c-128">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a9e0c-128">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="a9e0c-129">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="a9e0c-129">Managing User Mappings</span></span>](../core/managing-user-mappings.md)