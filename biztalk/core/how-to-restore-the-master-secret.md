---
title: マスター シークレットを復元する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [Master Secret server], restoring
- Master Secret server, restoring
- restoring, Master Secret server
ms.assetid: 68e133c5-4591-4d76-9a3b-c9564ff1aa60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04852571be9294ee62733bd78c884b407f2fb5b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384133"
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="fe5a6-102">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="fe5a6-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="fe5a6-103">データ回復の手順の一環として、既存のデータを再使用するマスター シークレットを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-103">As part of data recovery procedures, you may need to restore the master secret to re-use existing data.</span></span> <span data-ttu-id="fe5a6-104">このタスクを実行するためには、Windows 管理者であり、SSO 管理者であるアカウントを使用してマスター シークレット サーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-104">In order to perform this task, you must log on to the master secret server with an account that is both a Windows administrator and an SSO administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="fe5a6-105">MMC スナップインを使用してマスター シークレットを復元するには</span><span class="sxs-lookup"><span data-stu-id="fe5a6-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="fe5a6-106">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="fe5a6-107">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="fe5a6-108">右クリックして**システム**、 をクリックし、**シークレットの復元**します。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-108">Right-click **System**, and then click **Restore Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="fe5a6-109">コマンドラインを使用してマスター シークレットを復元するには</span><span class="sxs-lookup"><span data-stu-id="fe5a6-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="fe5a6-110">**開始** メニューのをクリックして**すべてのプログラム**、順にクリックします**アクセサリ**します。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-110">On the **Start** menu, click **All Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="fe5a6-111">右クリックして**コマンド プロンプト**、 をクリックし、**として実行しています**。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="fe5a6-112">適切な管理者を選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fe5a6-113">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fe5a6-114">既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-114">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="fe5a6-115">型**ssoconfig – restoresecret と入力\<ファイル復元\>** ここで、 **\<ファイルを復元\>** マスター シークレットがファイルの名前とパスには格納されています。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-115">Type **ssoconfig –restoreSecret \<restore file\>**, where **\<restore file\>** is the path and name of the file where the master secret is stored.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe5a6-116">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe5a6-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5a6-117">参照</span><span class="sxs-lookup"><span data-stu-id="fe5a6-117">See Also</span></span>  
 <span data-ttu-id="fe5a6-118">[マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="fe5a6-118">[How to Generate the Master Secret](../core/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="fe5a6-119">[マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="fe5a6-119">[How to Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="fe5a6-120">[マスター シークレット サーバー](../core/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="fe5a6-120">[Master Secret Server](../core/master-secret-server.md) </span></span>  
 [<span data-ttu-id="fe5a6-121">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="fe5a6-121">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)