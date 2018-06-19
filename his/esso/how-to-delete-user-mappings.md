---
title: ユーザー マッピングを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c4cdff-b82d-4cfd-8e20-220a2fe78656
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: a9d0a31c3dbc9d5980f59d9f30d20ec15f603a38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30251086"
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="fe0c3-102">ユーザー マッピングを削除する方法</span><span class="sxs-lookup"><span data-stu-id="fe0c3-102">How to Delete User Mappings</span></span>
<span data-ttu-id="fe0c3-103">以下のコマンドを使用して、XML ファイルで指定された 1 つ以上のユーザー マッピングを削除できます。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="fe0c3-104">XML ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="fe0c3-105">ユーザーは、アプリケーション ユーザー アカウントのメンバーではないか、Active Directory に存在しない場合、は、資格情報データベースからのユーザー マッピングを削除するこのコマンドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the Credential database.</span></span>  
  
 <span data-ttu-id="fe0c3-106">ユーザー アカウントを変更する場合は、このコマンドを使用して、古いユーザー マッピングを削除してから、新しいユーザー アカウントのマッピングを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="fe0c3-107">マッピングを作成する詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../esso/how-to-create-user-mappings.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-107">For more information about creating a mapping, see [How to Create User Mappings](../esso/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="fe0c3-108">管理ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="fe0c3-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="fe0c3-109">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fe0c3-110">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="fe0c3-111">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fe0c3-112">型`ssomanage –deletemappings <mappings file name>`ここで、 \<*マッピング ファイル名*> を削除するユーザー マッピングを格納しているファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-112">Type `ssomanage –deletemappings <mappings file name>`, where \<*mappings file name*> is the name of the file that contains the user mappings that you want to delete.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="fe0c3-113">管理ユーティリティを使用して特定のユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="fe0c3-113">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="fe0c3-114">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-114">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fe0c3-115">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-115">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="fe0c3-116">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-116">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fe0c3-117">型`ssomanage –deletemapping <domain>\<username> <application name>`ここで、 *\<ドメイン >* は Windows ドメイン ユーザー アカウントを*\<ユーザー名 >* は、Windows ユーザー名と\< *アプリケーション名*> は、特定のユーザー マッピングを削除するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-117">Type `ssomanage –deletemapping <domain>\<username> <application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name, and \<*application name*> is the specific application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="fe0c3-118">クライアント ユーティリティを使用してユーザー マッピングを削除するには</span><span class="sxs-lookup"><span data-stu-id="fe0c3-118">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="fe0c3-119">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-119">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fe0c3-120">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-120">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="fe0c3-121">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-121">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fe0c3-122">型`ssoclient –deletemapping <application name>`ここで、 *\<アプリケーション名 >* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe0c3-122">Type `ssoclient –deletemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0c3-123">参照</span><span class="sxs-lookup"><span data-stu-id="fe0c3-123">See Also</span></span>  
 <span data-ttu-id="fe0c3-124">[SSO マッピング](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fe0c3-124">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="fe0c3-125">[関連アプリケーションの管理](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fe0c3-125">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="fe0c3-126">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="fe0c3-126">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)