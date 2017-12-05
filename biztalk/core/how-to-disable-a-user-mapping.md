---
title: "ユーザー マッピングを無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b17ab68356d5d39f3f839f736261d4a7ef79c78
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="1924b-102">ユーザー マッピングを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="1924b-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="1924b-103">指定したマッピングに関連付けられたすべての操作を無効にするときに、ユーザー マッピングを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1924b-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="1924b-104">ユーザー マッピングは、削除する前に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1924b-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="1924b-105">ユーザー マッピングを無効にする場合は (D) として表示されます*\<ドメイン\>\\< ユーザー名\>*ユーザー マッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="1924b-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="1924b-106">管理ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="1924b-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="1924b-107">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="1924b-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1924b-108">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1924b-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1924b-109">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1924b-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1924b-110">型 **ssomanage – disablemapping *\<ドメイン\>*\\*\<username\> \<アプリケーション名前\>** *、どこで*\<ドメイン\>*は Windows ドメイン ユーザー アカウントと *\<username\>* は、資格情報を無効にする Windows ユーザー名と*\<アプリケーション名\>*ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1924b-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>***, where *\<domain\>* is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1924b-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1924b-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="1924b-112">クライアント ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="1924b-112">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="1924b-113">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="1924b-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1924b-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1924b-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1924b-115">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1924b-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1924b-116">型**ssoclient – disablemapping *\<アプリケーション名\>***ここで、 *\<アプリケーション名\>*は、ユーザー マッピングを削除する関連アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="1924b-116">Type **ssoclient –disablemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1924b-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1924b-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1924b-118">参照</span><span class="sxs-lookup"><span data-stu-id="1924b-118">See Also</span></span>  
 <span data-ttu-id="1924b-119">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1924b-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="1924b-120">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1924b-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1924b-121">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="1924b-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)