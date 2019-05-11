---
title: ユーザー マッピングの資格情報を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 228661c4e35175cf5f2e05c86bb0e10123f8e468
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383959"
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="fb579-102">ユーザー マッピングの資格情報を設定する方法</span><span class="sxs-lookup"><span data-stu-id="fb579-102">How to Set Credentials for a User Mapping</span></span>
<span data-ttu-id="fb579-103">このコマンドを使用すると、特定のアプリケーションにアクセスするのにユーザーの資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="fb579-103">Use this command to set the credentials for a user to access a specific application.</span></span>  
  
 <span data-ttu-id="fb579-104">このコマンドでは、入力すると、パスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fb579-104">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="fb579-105">ユーザー マッピングが既に存在する場合、このコマンドは、その既存のマッピングの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb579-105">If the user mapping already exists, this command sets the credentials for that existing mapping.</span></span> <span data-ttu-id="fb579-106">ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。</span><span class="sxs-lookup"><span data-stu-id="fb579-106">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="fb579-107">ユーザー マッピングの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="fb579-107">To set credentials for a user mapping</span></span>  
  
1.  <span data-ttu-id="fb579-108">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="fb579-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="fb579-109">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb579-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fb579-110">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fb579-110">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fb579-111">型**ssomanage – setcredentials\<ドメイン\>\\< ユーザー名\> \<applicationname\>** ここで、  **\<ドメイン\>** が Windows ドメイン ユーザー アカウントの**\<username\>** は、Windows ユーザー名と**\<applicationname\>** は特定のアプリケーションの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb579-111">Type **ssomanage –setcredentials \<domain\>\\<username\> \<applicationname\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name, and **\<applicationname\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb579-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb579-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="fb579-113">SSO システムでは、ユーザーの資格情報の入力を求められたらは、このアプリケーションのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="fb579-113">When the SSO system prompts you for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="fb579-114">ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。</span><span class="sxs-lookup"><span data-stu-id="fb579-114">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a><span data-ttu-id="fb579-115">クライアント ユーティリティからのユーザー マッピングの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="fb579-115">To set credentials for a user mapping from the client utility</span></span>  
  
1.  <span data-ttu-id="fb579-116">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="fb579-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="fb579-117">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb579-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fb579-118">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fb579-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fb579-119">型**ssoclient-setcredentials\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** 関連アプリケーションの名前を指定します。ユーザー マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb579-119">Type **ssoclient -setcredentials \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb579-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb579-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb579-121">参照</span><span class="sxs-lookup"><span data-stu-id="fb579-121">See Also</span></span>  
 <span data-ttu-id="fb579-122">[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fb579-122">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="fb579-123">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fb579-123">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="fb579-124">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fb579-124">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="fb579-125">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="fb579-125">Managing User Mappings</span></span>](../core/managing-user-mappings.md)