---
title: マスター シークレット サーバーを変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23e588e4ea7ac91b5f4ff8124b33b3611e91e8d4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387010"
---
# <a name="how-to-change-the-master-secret-server"></a><span data-ttu-id="4f0bf-102">マスター シークレット サーバーを変更する方法</span><span class="sxs-lookup"><span data-stu-id="4f0bf-102">How to Change the Master Secret Server</span></span>
<span data-ttu-id="4f0bf-103">マスター シークレット サーバーを設定して、SSO データベースを構成した後は、元のマスター シークレット サーバーが失敗し、復旧できない場合、マスター シークレット サーバーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-103">After you set up the master secret server and configure the SSO database, you can change the master secret server if the original master secret server fails and cannot be recovered.</span></span> <span data-ttu-id="4f0bf-104">マスター シークレット サーバーを変更するには、SSO サーバーをマスター シークレット サーバーを昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-104">To change the master secret server, you need to promote an SSO server to become the master secret server.</span></span>  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a><span data-ttu-id="4f0bf-105">MMC スナップインを使用してマスター シークレット サーバーを変更するには</span><span class="sxs-lookup"><span data-stu-id="4f0bf-105">To change the Master Secret Server using the MMC Snap-in</span></span>  
  
1.  <span data-ttu-id="4f0bf-106">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="4f0bf-107">スコープ ペインで右クリック**システム**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-107">In the scope pane, right click **System**, and then click **Properties**.</span></span> <span data-ttu-id="4f0bf-108">マスター シークレット サーバーが表示されます、**全般**のタブ、**システム プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-108">The Master secret server is displayed on the **General** tab of the **System Properties** dialog box.</span></span>  
  
3.  <span data-ttu-id="4f0bf-109">クリックして**変更**新しいマスターを選択するシークレット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-109">Click **Change** to select a new Master secret server.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4f0bf-110">マスター シークレット サーバーを変更するのには、MMC スナップインを使用して、ときに、マスター シークレット サーバーで操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-110">When using the MMC Snap-in to change the Master Secret Server, the operation must be performed on the Master Secret Server.</span></span> <span data-ttu-id="4f0bf-111">マスター シークレット サーバーではないコンピューターから MMC スナップインを使用してマスター シークレット サーバーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-111">It is not possible to change the Master Secret Server using the MMC Snap-in from a computer that is not the Master Secret Server.</span></span>  
  
4.  <span data-ttu-id="4f0bf-112">新しいマスター シークレット サーバー、マスターを復元するログオン、新しいマスターのレジストリにシークレット サーバーです。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-112">Logon to the new Master secret server to restore the Master secret to the registry of the new Master secret server.</span></span>  
  
5.  <span data-ttu-id="4f0bf-113">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
6.  <span data-ttu-id="4f0bf-114">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4f0bf-115">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
7.  <span data-ttu-id="4f0bf-116">新しいマスター シークレット サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-116">Restart the new Master Secret Server.</span></span>  
  
8.  <span data-ttu-id="4f0bf-117">型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-117">Type **ssoconfig –restoreSecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="4f0bf-118">マスター シークレットは、次の場所にレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-118">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="4f0bf-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span><span class="sxs-lookup"><span data-stu-id="4f0bf-119">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f0bf-120">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a><span data-ttu-id="4f0bf-121">コマンドラインを使用して、マスター シークレット サーバーに 1 つのシングル サインオン サーバーに昇格するには</span><span class="sxs-lookup"><span data-stu-id="4f0bf-121">To promote a Single Sign-On Server to master secret server using the command line</span></span>  
  
1.  <span data-ttu-id="4f0bf-122">マスター シークレット サーバーに昇格させる SSO サーバーの名前を含む XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-122">Create an XML file that includes the name of the SSO server you want to promote to master secret server.</span></span> <span data-ttu-id="4f0bf-123">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-123">For example,</span></span>  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4f0bf-124">変更するには、マスター シークレット サーバーではないコンピューターからマスター シークレット サーバーことを指定した XML ファイルにマスター シークレット サーバー名のみが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-124">To change the Master Secret Server from a computer that is not the Master Secret Server make sure that the specified XML file contains only the Master Secret Server name.</span></span> <span data-ttu-id="4f0bf-125">SSO 管理者の XML タグを含むことはない具体的には、または**ssomanage-updatedb**操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-125">Specifically, it should not contain the SSO Administrators XML tag or the **ssomanage -updatedb** operation will fail.</span></span>  
  
2.  <span data-ttu-id="4f0bf-126">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-126">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3.  <span data-ttu-id="4f0bf-127">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="4f0bf-128">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-128">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="4f0bf-129">型**ssomanage – updatedb** \<**更新ファイル**\>ここで、 \<**更新ファイル**\> XML ファイルの名前を指定します手順 1. で作成します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-129">Type **ssomanage –updatedb** \<**update file**\>, where \<**update file**\> is the name of the XML file you create in step 1.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f0bf-130">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="4f0bf-131">マスター シークレット サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-131">Restart the Master Secret Server.</span></span>  
  
6.  <span data-ttu-id="4f0bf-132">型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-132">Type **ssoconfig –restoresecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
     <span data-ttu-id="4f0bf-133">マスター シークレットは、次の場所にレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-133">The master secret is stored in the registry at the following location:</span></span>  
  
     <span data-ttu-id="4f0bf-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span><span class="sxs-lookup"><span data-stu-id="4f0bf-134">HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4f0bf-135">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f0bf-135">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0bf-136">参照</span><span class="sxs-lookup"><span data-stu-id="4f0bf-136">See Also</span></span>  
 <span data-ttu-id="4f0bf-137">[マスター シークレット サーバー](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="4f0bf-137">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 <span data-ttu-id="4f0bf-138">[マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md) </span><span class="sxs-lookup"><span data-stu-id="4f0bf-138">[How to Cluster the Master Secret Server](../core/how-to-cluster-the-master-secret-server1.md) </span></span>  
 <span data-ttu-id="4f0bf-139">[SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="4f0bf-139">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="4f0bf-140">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="4f0bf-140">Using SSO</span></span>](../core/using-sso.md)