---
title: ユーザー マッピングを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 917f3eb2d1438bb53b9a8a583e3985b0843f09b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385141"
---
# <a name="how-to-enable-a-user-mapping"></a><span data-ttu-id="57744-102">ユーザー マッピングを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="57744-102">How to Enable a User Mapping</span></span>
<span data-ttu-id="57744-103">ユーザーを有効にする必要がありますでシングル サインオン システムでマッピングを使用する前にマッピングすることができます。</span><span class="sxs-lookup"><span data-stu-id="57744-103">You must enable a user mapping before it you can use the mapping in the Single Sign-On system.</span></span>  
  
 <span data-ttu-id="57744-104">ユーザー マッピングを有効にすると (E) として表示されます**\<ドメイン\>\\< ユーザー名\>** ユーザー マッピングの一覧を表示する場合。</span><span class="sxs-lookup"><span data-stu-id="57744-104">When you enable a user mapping, it will appear as (E) **\<domain\>\\<username\>** when you list the user mappings.</span></span>  
  
 <span data-ttu-id="57744-105">-Setcredentials コマンドを使用して資格情報を設定した場合、マッピングは既に有効にするに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57744-105">Note that if you have set the credentials using the -setcredentials command, the mapping will already be enabled.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="57744-106">管理ユーティリティを使用してユーザー マッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="57744-106">To enable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="57744-107">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="57744-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="57744-108">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="57744-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="57744-109">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="57744-109">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="57744-110">型**ssomanage – enablemapping\<ドメイン\>\\< ユーザー名\>\<アプリケーション名\>** ここで、  **\<ドメイン\>** が Windows ドメイン ユーザー アカウントの**\<username\>** 資格情報、およびを有効にするWindowsユーザー名は、**\<アプリケーション名\>** ユーザー マッピングを削除し、enter する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="57744-110">Type **ssomanage –enablemapping \<domain\>\\<username\>\<application name\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name for which you want to enable the credentials, and **\<application name\>** is the name of the affiliate application you want to remove the user mapping for and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57744-111">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="57744-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="57744-112">クライアント ユーティリティを使用してユーザー マッピングを有効にするには</span><span class="sxs-lookup"><span data-stu-id="57744-112">To enable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="57744-113">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="57744-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="57744-114">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="57744-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="57744-115">既定のインストール ディレクトリは**\<ドライブ\>**: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="57744-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="57744-116">型**ssoclient – enablemapping\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** する関連アプリケーションの名前を指定しますユーザー マッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="57744-116">Type **ssoclient –enablemapping \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="57744-117">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="57744-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57744-118">参照</span><span class="sxs-lookup"><span data-stu-id="57744-118">See Also</span></span>  
 <span data-ttu-id="57744-119">[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="57744-119">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="57744-120">[SSO マッピング](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="57744-120">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="57744-121">[関連アプリケーションの管理](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="57744-121">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="57744-122">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="57744-122">Managing User Mappings</span></span>](../core/managing-user-mappings.md)