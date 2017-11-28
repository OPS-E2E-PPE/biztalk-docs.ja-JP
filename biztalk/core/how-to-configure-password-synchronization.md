---
title: "パスワード同期を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb913c1719f4833ef36cf9f73f6a96432217f2af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-password-synchronization"></a><span data-ttu-id="d9be8-102">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d9be8-102">How to Configure Password Synchronization</span></span>
<span data-ttu-id="d9be8-103">SSOCONFIG コマンド ライン ユーティリティを使用すると、パスワード同期の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d9be8-103">Use the SSOCONFIG command line utility to configure your password synchronization settings.</span></span>  
  
### <a name="to-specify-the-directory-for-replay-files"></a><span data-ttu-id="d9be8-104">再生ファイルのディレクトリを指定するには</span><span class="sxs-lookup"><span data-stu-id="d9be8-104">To specify the directory for replay files</span></span>  
  
1.  <span data-ttu-id="d9be8-105">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9be8-105">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d9be8-106">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d9be8-106">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d9be8-107">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9be8-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d9be8-108">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d9be8-108">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="d9be8-109">型**ssoconfig-replayfiles\<再生ファイルのディレクトリ > (& a) #124; 既定**Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9be8-109">Type **ssoconfig -replayfiles \<replay files directory> &#124; -default** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9be8-110">サービス アカウントを変更すると、再生ファイルは検出されません。</span><span class="sxs-lookup"><span data-stu-id="d9be8-110">Replay files are not deleted when you change the service account.</span></span> <span data-ttu-id="d9be8-111">このアカウントを変更する場合、再生ファイルを手動で削除することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d9be8-111">If you change this account, you will need to delete the replay files manually.</span></span>  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a><span data-ttu-id="d9be8-112">パスワード同期の最大有効期間を表示または変更するには</span><span class="sxs-lookup"><span data-stu-id="d9be8-112">To display or change maximum password synchronization age</span></span>  
  
1.  <span data-ttu-id="d9be8-113">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9be8-113">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="d9be8-114">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d9be8-114">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="d9be8-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d9be8-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d9be8-116">既定値は\<ドライブ >: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d9be8-116">The default is \<drive>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="d9be8-117">型**ssoconfig-syncage\<パスワードの最大保有期間を時間で >** Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d9be8-117">Type **ssoconfig -syncage \<maximum password age in hours>** and press Enter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9be8-118">SSOCONFIG ユーティリティでは、システム時刻として SQL Server コンピュータの時刻を使用します。</span><span class="sxs-lookup"><span data-stu-id="d9be8-118">The SSOCONFIG utility uses the time on the SQL Server computer as its system time.</span></span> <span data-ttu-id="d9be8-119">時刻に関連するコマンドを使用する際は、このことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d9be8-119">Remember this when using any commands related to time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9be8-120">参照</span><span class="sxs-lookup"><span data-stu-id="d9be8-120">See Also</span></span>  
 [<span data-ttu-id="d9be8-121">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d9be8-121">Password Synchronization</span></span>](../core/password-synchronization2.md)