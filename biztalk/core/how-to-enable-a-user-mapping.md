---
title: "ユーザー マッピングを有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af4679d277a12335f8a9776695cd829473df460d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-a-user-mapping"></a><span data-ttu-id="51990-102">ユーザー マッピングを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="51990-102">How to Enable a User Mapping</span></span>
<span data-ttu-id="51990-103">シングル サインオン システムでマッピングを使用するには、ユーザー マッピングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51990-103">You must enable a user mapping before it you can use the mapping in the Single Sign-On system.</span></span>  
  
 <span data-ttu-id="51990-104">ユーザー マッピングを有効にする場合は (E) として表示されます**\<ドメイン >\\< ユーザー名\>**ユーザー マッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="51990-104">When you enable a user mapping, it will appear as (E) **\<domain>\\<username\>** when you list the user mappings.</span></span>  
  
 <span data-ttu-id="51990-105">-setcredentials コマンドを使用して資格情報を設定した場合、マッピングは既に有効になっています。</span><span class="sxs-lookup"><span data-stu-id="51990-105">Note that if you have set the credentials using the -setcredentials command, the mapping will already be enabled.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="51990-106">管理ユーティリティを使用してユーザー マッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="51990-106">To enable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="51990-107">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="51990-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="51990-108">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="51990-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="51990-109">既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="51990-109">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="51990-110">型**ssomanage – enablemapping\<ドメイン >\\< ユーザー名\>\<アプリケーション名 >**ここで、 **\<ドメイン >**はWindows ドメイン ユーザー アカウントを**\<ユーザー名 >**は、資格情報を有効にする Windows ユーザー名と**\<アプリケーション名 >**ユーザー マッピングを削除し、ENTER キーを押してする関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51990-110">Type **ssomanage –enablemapping \<domain>\\<username\>\<application name>**, where **\<domain>** is the Windows domain for the user account, **\<username>** is the Windows user name for which you want to enable the credentials, and **\<application name>** is the name of the affiliate application you want to remove the user mapping for and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51990-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="51990-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="51990-112">クライアント ユーティリティを使用してユーザー マッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="51990-112">To enable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="51990-113">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="51990-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="51990-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="51990-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="51990-115">既定のインストール ディレクトリは**\<ドライブ >**: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="51990-115">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="51990-116">型**ssoclient – enablemapping\<アプリケーション名 >**ここで、 **\<アプリケーション名 >**ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="51990-116">Type **ssoclient –enablemapping \<application name>**, where **\<application name>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51990-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="51990-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51990-118">参照</span><span class="sxs-lookup"><span data-stu-id="51990-118">See Also</span></span>  
 <span data-ttu-id="51990-119">[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="51990-119">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="51990-120">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="51990-120">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="51990-121">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="51990-121">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="51990-122">ユーザー マッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="51990-122">Managing User Mappings</span></span>](../core/managing-user-mappings.md)