---
title: ユーザー マッピングを無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d1715268630f4eed26f8004fc3d61cde15830b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338116"
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="573de-102">ユーザー マッピングを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="573de-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="573de-103">指定したマッピングに関連付けられているすべての操作をオフにする場合に、ユーザーのマッピングを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="573de-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="573de-104">削除する前に、ユーザーのマッピングを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="573de-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="573de-105">ユーザー マッピングを無効にすると、(D) として表示されます*\<ドメイン\>\\< ユーザー名\>* ユーザー マッピングの一覧を表示する場合。</span><span class="sxs-lookup"><span data-stu-id="573de-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="573de-106">管理ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="573de-106">To disable a user mapping using the administration utility</span></span>  
  
1. <span data-ttu-id="573de-107">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="573de-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="573de-108">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="573de-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="573de-109">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="573de-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="573de-110">型**ssomanage – disablemapping *\<ドメイン\>*\\*\<username\> \<アプリケーション名\>** <em>ここで、*\<ドメイン\></em>ユーザー アカウントの Windows ドメインと*\<username\>\* が、資格情報を無効にする Windows ユーザー名と*\<アプリケーション名\>* ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="573de-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>**<em>, where \*\<domain\></em> is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="573de-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="573de-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="573de-112">クライアント ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="573de-112">To disable a user mapping using the client utility</span></span>  
  
1. <span data-ttu-id="573de-113">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="573de-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="573de-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="573de-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="573de-115">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="573de-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="573de-116">型 \* \* ssoclient – disablemapping *\<アプリケーション名\>\*\*<em>ここで、*\<アプリケーション名\></em>を削除する関連アプリケーションの名前を指定しますユーザーのマッピング。</span><span class="sxs-lookup"><span data-stu-id="573de-116">Type \*\*ssoclient –disablemapping \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="573de-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="573de-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573de-118">参照</span><span class="sxs-lookup"><span data-stu-id="573de-118">See Also</span></span>  
 <span data-ttu-id="573de-119">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="573de-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="573de-120">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="573de-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="573de-121">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="573de-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)