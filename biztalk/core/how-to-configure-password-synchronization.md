---
title: パスワード同期を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b18d6f59b364a12a9ffe775d64a57e310f76e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341299"
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="7c22a-102">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7c22a-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="7c22a-103">SSOCONFIG コマンド ライン ユーティリティを使用して、パスワード同期設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="7c22a-104">再生ファイルのディレクトリを指定するには</span><span class="sxs-lookup"><span data-stu-id="7c22a-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="7c22a-105">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c22a-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="7c22a-106">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="7c22a-107">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7c22a-108">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="7c22a-108">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="7c22a-109">型**ssoconfig-replayfiles\<再生ファイル ディレクトリ\> &#124; -既定**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-109">Type **ssoconfig -replayfiles \<replay files directory\> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c22a-110">サービス アカウントを変更すると、再生ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7c22a-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="7c22a-111">このアカウントを変更する場合は、再生ファイルを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7c22a-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="7c22a-112">表示またはパスワード同期の有効期間を変更するには</span><span class="sxs-lookup"><span data-stu-id="7c22a-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="7c22a-113">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7c22a-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="7c22a-114">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="7c22a-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7c22a-116">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="7c22a-116">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="7c22a-117">型**ssoconfig-syncage」\<パスワードの最大保有期間を時間で\>** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-117">Type **ssoconfig -syncage \<maximum password age in hours\>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7c22a-118">SSOCONFIG ユーティリティは、システム時刻として SQL Server コンピューターの時刻を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c22a-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="7c22a-119">時間に関連するコマンドを使用する場合は、このオプションを思い出してください。</span><span class="sxs-lookup"><span data-stu-id="7c22a-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c22a-120">参照</span><span class="sxs-lookup"><span data-stu-id="7c22a-120">See Also</span></span>  
 [<span data-ttu-id="7c22a-121">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="7c22a-121">Password Synchronization</span></span>](../core/password-synchronization2.md)