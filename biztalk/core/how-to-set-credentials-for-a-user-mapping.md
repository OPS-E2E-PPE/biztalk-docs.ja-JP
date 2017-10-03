---
title: "ユーザー マッピングの資格情報を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc5947b13d9ffcc3721f460ccbcd5bd25701be07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="1a45d-102">ユーザー マッピングの資格情報を設定する方法</span><span class="sxs-lookup"><span data-stu-id="1a45d-102">How to Set Credentials for a User Mapping</span></span>
<span data-ttu-id="1a45d-103">ここで示すコマンドを使用すると、ユーザーが特定のアプリケーションにアクセスするための資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a45d-103">Use this command to set the credentials for a user to access a specific application.</span></span>  
  
 <span data-ttu-id="1a45d-104">このコマンドでは、入力したパスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="1a45d-104">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="1a45d-105">ユーザー マッピングが既に存在する場合、このコマンドは、その既存のマッピングに対して資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1a45d-105">If the user mapping already exists, this command sets the credentials for that existing mapping.</span></span> <span data-ttu-id="1a45d-106">ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="1a45d-106">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="1a45d-107">ユーザー マッピングの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="1a45d-107">To set credentials for a user mapping</span></span>  
  
1.  <span data-ttu-id="1a45d-108">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="1a45d-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1a45d-109">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a45d-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1a45d-110">既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1a45d-110">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1a45d-111">型**ssomanage – setcredentials\<ドメイン >\\< ユーザー名\> \<applicationname >**ここで、 **\<ドメイン >**はWindows ドメイン ユーザー アカウントを**\<ユーザー名 >**は、Windows ユーザー名と **\<applicationname >**を特定のアプリケーションは、資格情報を設定するには。</span><span class="sxs-lookup"><span data-stu-id="1a45d-111">Type **ssomanage –setcredentials \<domain>\\<username\> \<applicationname>**, where **\<domain>** is the Windows domain for the user account, **\<username>** is the Windows user name, and **\<applicationname>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a45d-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a45d-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="1a45d-113">SSO システムからユーザーの資格情報が要求されたら、指定したアプリケーションのユーザー パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a45d-113">When the SSO system prompts you for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="1a45d-114">ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="1a45d-114">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a><span data-ttu-id="1a45d-115">クライアント ユーティリティを使用してユーザー マッピングの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="1a45d-115">To set credentials for a user mapping from the client utility</span></span>  
  
1.  <span data-ttu-id="1a45d-116">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="1a45d-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1a45d-117">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a45d-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1a45d-118">既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1a45d-118">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1a45d-119">型**ssoclient-setcredentials\<アプリケーション名 >**ここで、 **\<アプリケーション名 >**ユーザー マッピングを削除する関連アプリケーションの名前を指定します.</span><span class="sxs-lookup"><span data-stu-id="1a45d-119">Type **ssoclient -setcredentials \<application name>**, where **\<application name>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1a45d-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1a45d-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a45d-121">参照</span><span class="sxs-lookup"><span data-stu-id="1a45d-121">See Also</span></span>  
 <span data-ttu-id="1a45d-122">[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1a45d-122">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="1a45d-123">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1a45d-123">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="1a45d-124">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1a45d-124">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1a45d-125">ユーザー マッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="1a45d-125">Managing User Mappings</span></span>](../core/managing-user-mappings.md)