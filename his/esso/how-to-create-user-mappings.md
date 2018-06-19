---
title: ユーザー マッピングを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250966"
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="86723-102">ユーザー マッピングを作成する方法</span><span class="sxs-lookup"><span data-stu-id="86723-102">How to Create User Mappings</span></span>
<span data-ttu-id="86723-103">使用して、 **createmappings** XML ファイルで指定された、1 つまたは複数のユーザー マッピングを作成するコマンド。</span><span class="sxs-lookup"><span data-stu-id="86723-103">Use the **createmappings** command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="86723-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="86723-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="86723-105">ユーザー アカウントが変更された場合は、このコマンドを使用して、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86723-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="86723-106">また、古いユーザー マッピングを削除する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="86723-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="86723-107">マッピングの削除の詳細については、次を参照してください。[ユーザー マッピングを削除する方法](../esso/how-to-delete-user-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="86723-107">For more information about removing a mapping, see [How to Delete User Mappings](../esso/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="86723-108">ユーザー マッピングを作成した後に、シングル サインオン (SSO) システムでこのマッピングを使用する前に有効にあります。</span><span class="sxs-lookup"><span data-stu-id="86723-108">After you create a user mapping, you must enable it before you can use this mapping in the Single Sign-On (SSO) system.</span></span> <span data-ttu-id="86723-109">詳細については、次を参照してください。[ユーザー マッピングを有効にする方法](../esso/how-to-enable-a-user-mapping.md)です。</span><span class="sxs-lookup"><span data-stu-id="86723-109">For more information, see [How to Enable a User Mapping](../esso/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="86723-110">ユーザー マッピングでは、ドメイン グループのみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="86723-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="86723-111">管理ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="86723-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="86723-112">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="86723-112">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="86723-113">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="86723-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="86723-114">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="86723-114">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="86723-115">型`ssomanage –createmappings <mappings file name>`ここで、 *\<マッピング ファイル名 >* を作成するユーザー マッピングを格納しているファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="86723-115">Type `ssomanage –createmappings <mappings file name>`, where *\<mappings file name>* is the name of the file that contains the user mappings that you want to create.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="86723-116">クライアント ユーティリティを使用してユーザー マッピングを作成するには</span><span class="sxs-lookup"><span data-stu-id="86723-116">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="86723-117">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="86723-117">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="86723-118">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="86723-118">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="86723-119">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="86723-119">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="86723-120">型`ssoclient –setcredentials <application name >`ここで、 *\<アプリケーション名 >* ユーザーがマッピングを作成する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="86723-120">Type `ssoclient –setcredentials <application name >`, where *\<application name >* is the name of the affiliate application that the user wants to create a mapping for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86723-121">参照</span><span class="sxs-lookup"><span data-stu-id="86723-121">See Also</span></span>  
 <span data-ttu-id="86723-122">[SSO マッピング](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="86723-122">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="86723-123">[関連アプリケーションの管理](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="86723-123">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="86723-124">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="86723-124">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)