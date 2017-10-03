---
title: "マスター シークレットを生成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, generating
- managing [Master Secret server], generating
ms.assetid: 5512a8ee-bc5b-4fe4-90c7-41e3baaa723b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfbe186aee99616fa35e8f1e98f67c6ac75593c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-generate-the-master-secret"></a><span data-ttu-id="1ae37-102">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="1ae37-102">How to Generate the Master Secret</span></span>
<span data-ttu-id="1ae37-103">この作業を実行するには、マスター シークレット サーバーに対する管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ae37-103">You must have administrator rights on the master secret server in order to perform this task.</span></span> <span data-ttu-id="1ae37-104">また、この作業はマスター シークレット サーバーから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae37-104">In addition, you must perform this task from the master secret server.</span></span>  
  
 <span data-ttu-id="1ae37-105">最初にエンタープライズ シングル サインオンをインストールしたサーバーが、マスター シークレット サーバーになります。</span><span class="sxs-lookup"><span data-stu-id="1ae37-105">The first server where you install Enterprise Single Sign-On becomes the master secret server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1ae37-106">SSO システムに配置できるマスター シークレット サーバーは 1 台のみです。</span><span class="sxs-lookup"><span data-stu-id="1ae37-106">There can be only one master secret server in your SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ae37-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストール実行時にエンタープライズ シングル サインオンをインストールすると、マスター シークレットは構成ウィザードの手順の一部として生成されます。</span><span class="sxs-lookup"><span data-stu-id="1ae37-107">When Enterprise Single Sign-On is installed as part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, the master secret is generated as part of the Configuration Wizard.</span></span> <span data-ttu-id="1ae37-108">この作業は、新しいマスター シークレットを生成する場合にのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae37-108">You will only need to perform this task if you want to generate a new master secret.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="1ae37-109">MMC スナップインを使用してマスター シークレットを生成するには</span><span class="sxs-lookup"><span data-stu-id="1ae37-109">To generate the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="1ae37-110">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="1ae37-110">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="1ae37-111">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="1ae37-111">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="1ae37-112">右クリック**システム**、クリックして**シークレットの生成**です。</span><span class="sxs-lookup"><span data-stu-id="1ae37-112">Right-click **System**, and then click **Generate Secret**.</span></span>  
  
### <a name="to-generate-the-master-secret-using-the-command-line"></a><span data-ttu-id="1ae37-113">コマンド ラインを使用してマスター シークレットを生成するには</span><span class="sxs-lookup"><span data-stu-id="1ae37-113">To generate the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="1ae37-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="1ae37-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1ae37-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ae37-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1ae37-116">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1ae37-116">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1ae37-117">型 **ssoconfig – generateSecret \<*バックアップ ファイル*>**ここで、 \<*バックアップ ファイル*> をマスター シークレットを含むファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae37-117">Type **ssoconfig –generateSecret \<*backup file*>**, where \<*backup file*> is the name of the file that contains the master secret.</span></span>  
  
     <span data-ttu-id="1ae37-118">作成したファイルを保護するためのパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1ae37-118">You will be prompted to enter a password to protect the file you just created.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ae37-119">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ae37-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae37-120">参照</span><span class="sxs-lookup"><span data-stu-id="1ae37-120">See Also</span></span>  
 <span data-ttu-id="1ae37-121">[マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="1ae37-121">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="1ae37-122">[マスター シークレット サーバー](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="1ae37-122">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="1ae37-123">マスタ シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="1ae37-123">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)