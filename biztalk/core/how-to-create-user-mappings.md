---
title: ユーザー マッピングを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df63045a5627bd3d7c356e76e4c836ee6ce28622
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338916"
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="0e068-102">ユーザー マッピングを作成する方法</span><span class="sxs-lookup"><span data-stu-id="0e068-102">How to Create User Mappings</span></span>
<span data-ttu-id="0e068-103">ここで示すコマンドを使用すると、XML ファイルで指定された 1 つ以上のユーザー マッピングを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0e068-103">Use this command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="0e068-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0e068-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="0e068-105">ユーザー アカウントが変更された場合は、このコマンドを使用して、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e068-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="0e068-106">また、古いユーザー マッピングを削除する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="0e068-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="0e068-107">マッピングを削除する方法の詳細については、次を参照してください。[ユーザー マッピングを削除する方法](../core/how-to-delete-user-mappings.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e068-107">For more information about removing a mapping, see [How to Delete User Mappings](../core/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="0e068-108">作成したユーザー マッピングを SSO システムで使用するには、ユーザー マッピングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e068-108">After you create a user mapping, you must enable it before you can use this mapping in the SSO system.</span></span> <span data-ttu-id="0e068-109">詳細については、次を参照してください。[ユーザー マッピングを有効にする方法](../core/how-to-enable-a-user-mapping.md)します。</span><span class="sxs-lookup"><span data-stu-id="0e068-109">For more information, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0e068-110">ユーザー マッピングでは、ドメイン グループのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0e068-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="0e068-111">管理ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="0e068-111">To create user mappings using the administration utility</span></span>  
  
1. <span data-ttu-id="0e068-112">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="0e068-112">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="0e068-113">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0e068-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0e068-114">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="0e068-114">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="0e068-115">型 \* \* ssomanage – createmappings *\<ファイル名をマッピング\>\*\*<em>ここで、*\<ファイル名をマッピング\></em>必要なユーザー マッピングを含むファイルの名前を指定します作成します。</span><span class="sxs-lookup"><span data-stu-id="0e068-115">Type \*\*ssomanage –createmappings \*\<mappings file name\>\*\*<em>, where \*\<mappings file name\></em> is the name of file that contains the user mapping(s) you want to create.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0e068-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e068-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="0e068-117">クライアント ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="0e068-117">To create user mappings using the client utility</span></span>  
  
1. <span data-ttu-id="0e068-118">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="0e068-118">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="0e068-119">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0e068-119">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="0e068-120">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="0e068-120">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="0e068-121">型 \* \* ssoclient – setcredentials \*\<アプリケーション名\> \**<em>ここで、*\<アプリケーション名\></em>ユーザーがする関連アプリケーションの名前を指定しますマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="0e068-121">Type \*\*ssoclient –setcredentials \*\<application name \>\*\*<em>, where \*\<application name \></em> is the name of affiliate application that the user wants to create a mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0e068-122">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="0e068-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e068-123">参照</span><span class="sxs-lookup"><span data-stu-id="0e068-123">See Also</span></span>  
 <span data-ttu-id="0e068-124">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="0e068-124">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="0e068-125">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0e068-125">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="0e068-126">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="0e068-126">Managing User Mappings</span></span>](../core/managing-user-mappings.md)