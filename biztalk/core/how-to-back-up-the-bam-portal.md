---
title: BAM ポータルをバックアップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbfa35fd3adc6fbbcba247fbc5c093a52c05f044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387102"
---
# <a name="how-to-back-up-the-bam-portal"></a><span data-ttu-id="104c7-102">BAM ポータルをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="104c7-102">How to Back Up the BAM Portal</span></span>
<span data-ttu-id="104c7-103">ビジネス アクティビティ監視 (BAM) を使用している場合は、BizTalk server のバックアップの一部として、BAM ポータルをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="104c7-103">If you are using Business Activity Monitoring (BAM), you must back up the BAM portal as part of backing up your BizTalk server.</span></span> <span data-ttu-id="104c7-104">BAM を使用していない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="104c7-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="104c7-105">バックアップ プロセスの特定の部分は、バックアップするインターネット インフォメーション サービス (IIS) のバージョンに応じて著しく異なります。</span><span class="sxs-lookup"><span data-stu-id="104c7-105">Certain portions of the backup process differ markedly depending on which version of Internet Information Services (IIS) you are backing up.</span></span> <span data-ttu-id="104c7-106">IIS 6.0 では、アプリケーション プールの構成と web サイトの構成を個別にバックアップして、パスワードを使用して、構成のバックアップ ファイルを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="104c7-106">IIS 6.0 permits you to back up the application pool configuration and web site configuration separately, and you can encrypt the configuration backup files using a password.</span></span>  
  
 <span data-ttu-id="104c7-107">IIS 7.0 アプリケーション プールと web サイトの両方の構成設定を 1 つのファイルに保存する applicationHost.config します。ApplicationHost.config ファイルは暗号化されませんが、アカウントのパスワードは、存在する場合、ファイルに暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="104c7-107">IIS 7.0 saves configuration settings for both the application pool and web site to a single file, applicationHost.config. The applicationHost.config file is not encrypted, but account passwords, if any, are encrypted in the file.</span></span> <span data-ttu-id="104c7-108">暗号化は、バックアップするには、コンピューターから証明書を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="104c7-108">Encryption is performed using the certificate from the computer you are backing up.</span></span> <span data-ttu-id="104c7-109">この構成は、元の 1 つ以外のコンピューターに復元できません。</span><span class="sxs-lookup"><span data-stu-id="104c7-109">This configuration cannot be restored to a computer other than the one from which it originated.</span></span>  
  
 <span data-ttu-id="104c7-110">IIS 7.0 マネージャーを使用して BAM ポータルの構成をバックアップすることはできません。使用する必要があります、 **Appcmd.exe**コマンド ライン ツール。</span><span class="sxs-lookup"><span data-stu-id="104c7-110">You cannot back up the BAM portal configuration using the IIS 7.0 Manager; you must use the **Appcmd.exe** command-line tool.</span></span> <span data-ttu-id="104c7-111">Appcmd の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)します。</span><span class="sxs-lookup"><span data-stu-id="104c7-111">For more information about Appcmd, see [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="104c7-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="104c7-112">Prerequisites</span></span>  
 <span data-ttu-id="104c7-113">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="104c7-113">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a><span data-ttu-id="104c7-114">BAM ポータル (IIS 7.0) をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="104c7-114">To back up the BAM portal (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="104c7-115">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="104c7-115">Click **Start**, and then click **Run**.</span></span>  
  
2.  <span data-ttu-id="104c7-116">実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="104c7-116">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="104c7-117">*Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="104c7-117">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
3.  <span data-ttu-id="104c7-118">パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="104c7-118">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="104c7-119">型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="104c7-119">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="104c7-120">型`appcmd add backup “`*バックアップ名*`”`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="104c7-120">Type `appcmd add backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="104c7-121">バックアップ名を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="104c7-121">You do not have to enter a backup name.</span></span> <span data-ttu-id="104c7-122">かどうか設定されていないことが自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="104c7-122">If not set, it will be autogenerated.</span></span> <span data-ttu-id="104c7-123">自動生成されたバックアップの名前の例としては"20090224T123302"にします。</span><span class="sxs-lookup"><span data-stu-id="104c7-123">An example of an autogenerated backup name is “20090224T123302.”</span></span>  
  
     <span data-ttu-id="104c7-124">既存の構成のバックアップの一覧を表示するには、次のように入力します。 `appcmd list backup`、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="104c7-124">To see a list of existing configuration backups, type `appcmd list backup`, and then press **Enter**.</span></span> <span data-ttu-id="104c7-125">ユーザーによって作成されたバックアップの保存、 **%windir%\system32\inetsrv\backup**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="104c7-125">Backups created by the user are saved in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="104c7-126">によって提供されるバックアップ オプションの一覧を表示する**appcmd.exe**、型`appcmd backup /?`、キーを押しますと **」と入力**します。</span><span class="sxs-lookup"><span data-stu-id="104c7-126">To see a list of the backup options provided by **appcmd.exe**, type `appcmd backup /?`, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104c7-127">参照</span><span class="sxs-lookup"><span data-stu-id="104c7-127">See Also</span></span>  
 <span data-ttu-id="104c7-128">[BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="104c7-128">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 <span data-ttu-id="104c7-129">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="104c7-129">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="104c7-130">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="104c7-130">BAM Portal</span></span>](../core/bam-portal.md)