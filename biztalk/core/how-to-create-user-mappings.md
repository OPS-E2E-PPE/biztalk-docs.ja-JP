---
title: "ユーザー マッピングを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019adf0cd41c643ac77790c96a3450bb967ddd6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="bd737-102">ユーザー マッピングを作成する方法</span><span class="sxs-lookup"><span data-stu-id="bd737-102">How to Create User Mappings</span></span>
<span data-ttu-id="bd737-103">ここで示すコマンドを使用すると、XML ファイルで指定された 1 つ以上のユーザー マッピングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bd737-103">Use this command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="bd737-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bd737-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="bd737-105">ユーザー アカウントが変更された場合は、このコマンドを使用して、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd737-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="bd737-106">また、古いユーザー マッピングを削除する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="bd737-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="bd737-107">マッピングの削除の詳細については、次を参照してください。[ユーザー マッピングを削除する方法](../core/how-to-delete-user-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd737-107">For more information about removing a mapping, see [How to Delete User Mappings](../core/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="bd737-108">作成したユーザー マッピングを SSO システムで使用するには、ユーザー マッピングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bd737-108">After you create a user mapping, you must enable it before you can use this mapping in the SSO system.</span></span> <span data-ttu-id="bd737-109">詳細については、次を参照してください。[ユーザー マッピングを有効にする方法](../core/how-to-enable-a-user-mapping.md)です。</span><span class="sxs-lookup"><span data-stu-id="bd737-109">For more information, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd737-110">ユーザー マッピングでは、ドメイン グループのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bd737-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="bd737-111">管理ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="bd737-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="bd737-112">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="bd737-112">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="bd737-113">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="bd737-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="bd737-114">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="bd737-114">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="bd737-115">型**ssomanage – createmappings *\<マッピング ファイル名\>***ここで、 *\<マッピング ファイル名\>*は作成するユーザー マッピングが格納されているファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="bd737-115">Type **ssomanage –createmappings *\<mappings file name\>***, where *\<mappings file name\>* is the name of file that contains the user mapping(s) you want to create.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd737-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd737-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="bd737-117">クライアント ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="bd737-117">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="bd737-118">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="bd737-118">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="bd737-119">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="bd737-119">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="bd737-120">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="bd737-120">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="bd737-121">型**ssoclient – setcredentials *\<アプリケーション名\>*** ここで、 *\<アプリケーション名\>*は、ユーザーがマッピングを作成する関連アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="bd737-121">Type **ssoclient –setcredentials *\<application name \>***, where *\<application name \>* is the name of affiliate application that the user wants to create a mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd737-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd737-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd737-123">参照</span><span class="sxs-lookup"><span data-stu-id="bd737-123">See Also</span></span>  
 <span data-ttu-id="bd737-124">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="bd737-124">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="bd737-125">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="bd737-125">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="bd737-126">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="bd737-126">Managing User Mappings</span></span>](../core/managing-user-mappings.md)