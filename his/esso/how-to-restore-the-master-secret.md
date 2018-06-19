---
title: マスター シークレットを復元する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b331c9c5-ca90-4a05-b3f6-59db88bf73dc
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 5e640f2762ed9f9cc03a7795062c98a6aa76a59d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250950"
---
# <a name="how-to-restore-the-master-secret"></a><span data-ttu-id="43ded-102">マスター シークレットを復元する方法</span><span class="sxs-lookup"><span data-stu-id="43ded-102">How to Restore the Master Secret</span></span>
<span data-ttu-id="43ded-103">データの回復手順の一部として、既存のデータを再利用するマスター シークレットを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ded-103">As part of data recovery procedures, you might have to restore the master secret to reuse existing data.</span></span> <span data-ttu-id="43ded-104">このタスクを実行するには、Windows 管理者であり、シングル サインオン (SSO) 管理者であるアカウントを使用して、マスタ シークレット サーバーにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43ded-104">To perform this task, you must log on to the master secret server by using an account that is both a Windows administrator and a Single Sign-On (SSO) administrator.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-mmc-snap-in"></a><span data-ttu-id="43ded-105">MMC スナップインを使用してマスター シークレットを復元するには</span><span class="sxs-lookup"><span data-stu-id="43ded-105">To restore the master secret using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="43ded-106">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="43ded-106">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="43ded-107">ENTSSO Microsoft 管理コンソール (MMC) スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="43ded-107">In the scope pane of the ENTSSO Microsoft Management Console (MMC) Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="43ded-108">右クリック**システム**、クリックして**マスター シークレットの復元**です。</span><span class="sxs-lookup"><span data-stu-id="43ded-108">Right-click **System**, and then click **Restore Master Secret**.</span></span>  
  
### <a name="to-restore-the-master-secret-using-the-command-line"></a><span data-ttu-id="43ded-109">コマンド ラインを使用してマスター シークレットを復元するには</span><span class="sxs-lookup"><span data-stu-id="43ded-109">To restore the master secret using the command line</span></span>  
  
1.  <span data-ttu-id="43ded-110">**開始** メニューのをクリックして**プログラム**、クリックして**アクセサリ**です。</span><span class="sxs-lookup"><span data-stu-id="43ded-110">On the **Start** menu, click **Programs**, and then click **Accessories**.</span></span> <span data-ttu-id="43ded-111">右クリック **コマンド プロンプト**, 、クリックして **実行付けて**します。</span><span class="sxs-lookup"><span data-stu-id="43ded-111">Right-click **Command Prompt**, and then click **Run As…**.</span></span>  
  
2.  <span data-ttu-id="43ded-112">適切な管理者を選択し、クリックして **OK**します。</span><span class="sxs-lookup"><span data-stu-id="43ded-112">Select the appropriate Administrator, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="43ded-113">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="43ded-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="43ded-114">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="43ded-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="43ded-115">型`ssoconfig –restoresecret <restore file>`ここで、 *\<ファイルを復元 >* はマスター シークレットが格納されているファイルの名前とパス。</span><span class="sxs-lookup"><span data-stu-id="43ded-115">Type `ssoconfig –restoresecret <restore file>`, where *\<restore file>* is the path and name of the file where the master secret is stored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ded-116">参照</span><span class="sxs-lookup"><span data-stu-id="43ded-116">See Also</span></span>  
 <span data-ttu-id="43ded-117">[マスター シークレットを生成する方法](../esso/how-to-generate-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="43ded-117">[How to Generate the Master Secret](../esso/how-to-generate-the-master-secret.md) </span></span>  
 <span data-ttu-id="43ded-118">[マスター シークレットをバックアップする方法](../esso/how-to-back-up-the-master-secret.md) </span><span class="sxs-lookup"><span data-stu-id="43ded-118">[How to Back Up the Master Secret](../esso/how-to-back-up-the-master-secret.md) </span></span>  
 <span data-ttu-id="43ded-119">[マスター シークレット サーバー](../esso/master-secret-server.md) </span><span class="sxs-lookup"><span data-stu-id="43ded-119">[Master Secret Server](../esso/master-secret-server.md) </span></span>  
 [<span data-ttu-id="43ded-120">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="43ded-120">Managing the Master Secret</span></span>](../esso/managing-the-master-secret.md)