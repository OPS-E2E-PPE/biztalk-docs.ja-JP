---
title: 関連アプリケーションを有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="1a5de-102">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="1a5de-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="1a5de-103">MMC スナップインを使用することができます、または**enableapp**コマンドを指定された関連アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1a5de-103">You can use the MMC Snap-In or the **enableapp** command to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="1a5de-104">MMC スナップインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="1a5de-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="1a5de-105">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="1a5de-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="1a5de-106">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="1a5de-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="1a5de-107">関連アプリケーションを右クリックし、をクリックし、 **を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="1a5de-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="1a5de-108">コマンド ラインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="1a5de-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="1a5de-109">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1a5de-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1a5de-110">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1a5de-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1a5de-111">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1a5de-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1a5de-112">型`ssomanage –enableapp <application name>`ここで、 \<*アプリケーション名*> を有効にする関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1a5de-112">Type `ssomanage –enableapp <application name>`, where \<*application name*> is the name of the affiliate application you want to enable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5de-113">参照</span><span class="sxs-lookup"><span data-stu-id="1a5de-113">See Also</span></span>  
 <span data-ttu-id="1a5de-114">[SSO 関連アプリケーション](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1a5de-114">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="1a5de-115">[関連アプリケーションを作成する方法](../esso/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="1a5de-115">[How to Create an Affiliate Application](../esso/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="1a5de-116">[ユーザー マッピングを管理します。](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1a5de-116">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="1a5de-117">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="1a5de-117">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)