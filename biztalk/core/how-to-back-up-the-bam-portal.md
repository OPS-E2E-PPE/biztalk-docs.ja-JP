---
title: BAM ポータルをバックアップする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247122"
---
# <a name="how-to-back-up-the-bam-portal"></a><span data-ttu-id="94767-102">BAM ポータルをバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="94767-102">How to Back Up the BAM Portal</span></span>
<span data-ttu-id="94767-103">ビジネス アクティビティの監視 (BAM) を使用している場合は、BizTalk Server のバックアップ処理の一環として BAM ポータルをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94767-103">If you are using Business Activity Monitoring (BAM), you must back up the BAM portal as part of backing up your BizTalk server.</span></span> <span data-ttu-id="94767-104">BAM を使用していない場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="94767-104">If you are not using BAM, this procedure is optional.</span></span>  
  
 <span data-ttu-id="94767-105">バックアップ プロセスの一部は、バックアップ対象のインターネット インフォメーション サービス (IIS) のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="94767-105">Certain portions of the backup process differ markedly depending on which version of Internet Information Services (IIS) you are backing up.</span></span> <span data-ttu-id="94767-106">IIS 6.0 では、アプリケーション プール構成と Web サイト構成を別々にバックアップでき、パスワードを使用して構成バックアップ ファイルを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="94767-106">IIS 6.0 permits you to back up the application pool configuration and web site configuration separately, and you can encrypt the configuration backup files using a password.</span></span>  
  
 <span data-ttu-id="94767-107">IIS 7.0 アプリケーション プールと web サイトの両方の構成設定を 1 つのファイルに保存する applicationHost.config です。ApplicationHost.config ファイルが暗号化されていないが、アカウントのパスワードは、存在する場合、ファイルで暗号化がします。</span><span class="sxs-lookup"><span data-stu-id="94767-107">IIS 7.0 saves configuration settings for both the application pool and web site to a single file, applicationHost.config. The applicationHost.config file is not encrypted, but account passwords, if any, are encrypted in the file.</span></span> <span data-ttu-id="94767-108">暗号化はバックアップ対象のコンピューターの証明書を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="94767-108">Encryption is performed using the certificate from the computer you are backing up.</span></span> <span data-ttu-id="94767-109">この構成は、元のコンピューター以外のコンピューターには復元できません。</span><span class="sxs-lookup"><span data-stu-id="94767-109">This configuration cannot be restored to a computer other than the one from which it originated.</span></span>  
  
 <span data-ttu-id="94767-110">IIS 7.0 マネージャーを使用して BAM ポータルの構成をバックアップすることはできません。使用する必要があります、 **Appcmd.exe**コマンド ライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="94767-110">You cannot back up the BAM portal configuration using the IIS 7.0 Manager; you must use the **Appcmd.exe** command-line tool.</span></span> <span data-ttu-id="94767-111">Appcmd の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)です。</span><span class="sxs-lookup"><span data-stu-id="94767-111">For more information about Appcmd, see [http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94767-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="94767-112">Prerequisites</span></span>  
 <span data-ttu-id="94767-113">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94767-113">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a><span data-ttu-id="94767-114">BAM ポータル (IIS 7.0) をバックアップするには</span><span class="sxs-lookup"><span data-stu-id="94767-114">To back up the BAM portal (IIS 7.0)</span></span>  
  
1.  <span data-ttu-id="94767-115">**[スタート]** ボタンをクリックし、 **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94767-115">Click **Start**, and then click **Run**.</span></span>  
  
2.  <span data-ttu-id="94767-116">実行 ダイアログ ボックスで、名前 ボックスで、以下を入力: `runas /user:` *computername*`\`*accountname* `cmd`、クリックして**OK**またはキーを押して**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-116">On the Run dialog, in the Open box, type the following: `runas /user:`*computername*`\`*accountname* `cmd`, and then click **OK** or press **Enter**.</span></span>  
  
     <span data-ttu-id="94767-117">*Accountname*ローカル コンピューターの administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94767-117">*Accountname* must be a member of the administrators group on the local computer.</span></span>  
  
3.  <span data-ttu-id="94767-118">パスワードを入力メッセージが表示されたら、 *accountname*、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-118">When prompted, type the password for *accountname*, and then press **Enter**.</span></span>  
  
4.  <span data-ttu-id="94767-119">型`cd %windir%\system32\inetsrv`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-119">Type `cd %windir%\system32\inetsrv`, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="94767-120">型`appcmd add backup “`*バックアップ名*`”`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-120">Type `appcmd add backup “`*backupname*`”`, and then press **Enter**.</span></span>  
  
     <span data-ttu-id="94767-121">バックアップ名を入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94767-121">You do not have to enter a backup name.</span></span> <span data-ttu-id="94767-122">設定しない場合は、自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="94767-122">If not set, it will be autogenerated.</span></span> <span data-ttu-id="94767-123">たとえば、自動生成されたバックアップ名は "20090224T123302" になります。</span><span class="sxs-lookup"><span data-stu-id="94767-123">An example of an autogenerated backup name is “20090224T123302.”</span></span>  
  
     <span data-ttu-id="94767-124">既存の構成バックアップの一覧を表示するには、次のように入力します。 `appcmd list backup`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-124">To see a list of existing configuration backups, type `appcmd list backup`, and then press **Enter**.</span></span> <span data-ttu-id="94767-125">ユーザーによって作成されたバックアップが保存される、 **%windir%\system32\inetsrv\backup**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="94767-125">Backups created by the user are saved in the **%windir%\system32\inetsrv\backup** directory.</span></span> <span data-ttu-id="94767-126">によって指定されたバックアップ オプションの一覧を表示する**appcmd.exe**、型`appcmd backup /?`、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="94767-126">To see a list of the backup options provided by **appcmd.exe**, type `appcmd backup /?`, and then press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94767-127">参照</span><span class="sxs-lookup"><span data-stu-id="94767-127">See Also</span></span>  
 <span data-ttu-id="94767-128">[BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="94767-128">[Backing Up a Computer Running BizTalk Server](../core/backing-up-a-computer-running-biztalk-server.md) </span></span>  
 <span data-ttu-id="94767-129">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="94767-129">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="94767-130">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="94767-130">BAM Portal</span></span>](../core/bam-portal.md)