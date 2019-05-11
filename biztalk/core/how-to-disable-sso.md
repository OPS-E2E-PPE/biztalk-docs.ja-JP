---
title: SSO を無効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c14f83d4130153f7066b542702007bf9f704387
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338080"
---
# <a name="how-to-disable-sso"></a><span data-ttu-id="a05d6-102">SSO を無効にする方法</span><span class="sxs-lookup"><span data-stu-id="a05d6-102">How to Disable SSO</span></span>
<span data-ttu-id="a05d6-103">MMC スナップインまたはコマンドラインを使用して、全体でシングル サインオン システムを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="a05d6-103">You can disable the entire Single Sign-On system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="a05d6-104">ありますすべてのシングル サインオン サーバーを無効にする、しばらく時間がかかるように、最新のグローバル情報を SSO データベースにポーリングします。</span><span class="sxs-lookup"><span data-stu-id="a05d6-104">There will be a short delay for all Single Sign-On Servers to be disabled, as they poll the SSO database for the latest global information.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a><span data-ttu-id="a05d6-105">エンタープライズ シングル サインオン、MMC スナップインを使用して無効にするには</span><span class="sxs-lookup"><span data-stu-id="a05d6-105">To disable Enterprise Single Sign-On using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a05d6-106">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="a05d6-106">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a05d6-107">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="a05d6-107">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a05d6-108">右クリック**システム**、 をクリックし、**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="a05d6-108">Right-click **System**, and then click **Disable**.</span></span>  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a><span data-ttu-id="a05d6-109">エンタープライズ シングル サインオン、コマンドラインを使用して無効にするには</span><span class="sxs-lookup"><span data-stu-id="a05d6-109">To disable Enterprise Single Sign-On using the command line</span></span>  
  
1.  <span data-ttu-id="a05d6-110">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a05d6-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="a05d6-111">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a05d6-111">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a05d6-112">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a05d6-112">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a05d6-113">型**ssomanage – disablesso**します。</span><span class="sxs-lookup"><span data-stu-id="a05d6-113">Type **ssomanage –disablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a05d6-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a05d6-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05d6-115">参照</span><span class="sxs-lookup"><span data-stu-id="a05d6-115">See Also</span></span>  
 <span data-ttu-id="a05d6-116">[SSO を有効にする方法](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="a05d6-116">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 [<span data-ttu-id="a05d6-117">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="a05d6-117">Using SSO</span></span>](../core/using-sso.md)