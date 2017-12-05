---
title: "ユーザー マッピングを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f7c1fa75b6fe7bb4c78e18c97fccd1404f89c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="31712-102">ユーザー マッピングを削除する方法</span><span class="sxs-lookup"><span data-stu-id="31712-102">How to Delete User Mappings</span></span>
<span data-ttu-id="31712-103">以下のコマンドを使用して、XML ファイルで指定された 1 つ以上のユーザー マッピングを削除できます。</span><span class="sxs-lookup"><span data-stu-id="31712-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="31712-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="31712-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="31712-105">ユーザーが、アプリケーション ユーザー アカウントのメンバーでないか Active Directory に登録されていない場合、このコマンドを使用してユーザー マッピングを SSO データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="31712-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the SSO database.</span></span>  
  
 <span data-ttu-id="31712-106">ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31712-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="31712-107">マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="31712-107">For more information about creating a mapping, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="31712-108">管理ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="31712-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="31712-109">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="31712-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="31712-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="31712-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="31712-111">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="31712-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="31712-112">型**ssomanage – deletemappings *\<マッピング ファイル名\>***ここで、 \<*マッピング ファイル名*\>は削除するユーザー マッピングが格納されているファイルの名前です。</span><span class="sxs-lookup"><span data-stu-id="31712-112">Type **ssomanage –deletemappings *\<mappings file name\>***, where \<*mappings file name*\> is the name of the file that contains the user mapping(s) you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31712-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="31712-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="31712-114">管理ユーティリティを使用して特定のユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="31712-114">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="31712-115">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="31712-115">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="31712-116">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="31712-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="31712-117">既定のインストール ディレクトリは*\<ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="31712-117">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="31712-118">型 **ssomanage – deletemapping *\<ドメイン\>*\\*\<username\>*  *\<アプリケーション名\>***ここで、 *\<ドメイン\>* Windows ドメイン ユーザー アカウントには *\<username\>* は、Windows ユーザー名と\<*アプリケーション名*\>をする特定のアプリケーションは、ユーザー マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="31712-118">Type **ssomanage –deletemapping *\<domain\>*\\*\<username\>* *\<application name\>***, where *\<domain\>* is the Windows domain for the user account, *\<username\>* is the Windows user name, and \<*application name*\> is the specific application for which you want to remove the user mapping.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31712-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="31712-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="31712-120">クライアント ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="31712-120">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="31712-121">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="31712-121">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="31712-122">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="31712-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="31712-123">既定のインストール ディレクトリは*\<ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="31712-123">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="31712-124">型**ssoclient – deletemapping *\<アプリケーション名\>***ここで、 *\<アプリケーション名\>*は、ユーザー マッピングを削除する関連アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="31712-124">Type **ssoclient –deletemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31712-125">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="31712-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31712-126">参照</span><span class="sxs-lookup"><span data-stu-id="31712-126">See Also</span></span>  
 <span data-ttu-id="31712-127">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="31712-127">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="31712-128">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="31712-128">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="31712-129">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="31712-129">Managing User Mappings</span></span>](../core/managing-user-mappings.md)