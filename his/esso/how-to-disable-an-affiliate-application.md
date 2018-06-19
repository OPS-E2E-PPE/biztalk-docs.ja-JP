---
title: 関連アプリケーションを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7df6e78-6d18-443d-82dc-4351c20a8c4e
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 6bae89d2a05ec34095e0fa2ac3feafc7b88b894e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250926"
---
# <a name="how-to-disable-an-affiliate-application"></a><span data-ttu-id="fa366-102">関連アプリケーションを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="fa366-102">How to Disable an Affiliate Application</span></span>
<span data-ttu-id="fa366-103">MMC スナップインを使用して、または**disableapp**指定された関連アプリケーションを無効にするコマンド。</span><span class="sxs-lookup"><span data-stu-id="fa366-103">Use the MMC Snap-In or the **disableapp** command to disable the specified affiliate application.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="fa366-104">MMC スナップインを使用して関連アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="fa366-104">To disable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="fa366-105">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="fa366-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="fa366-106">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="fa366-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="fa366-107">関連アプリケーションを右クリックし、をクリックし、 **を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="fa366-107">Right-click the affiliate application, and then click **Disable**.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="fa366-108">コマンド ラインを使用して関連アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="fa366-108">To disable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="fa366-109">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fa366-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="fa366-110">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fa366-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="fa366-111">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="fa366-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="fa366-112">型`ssomanage –disableapp <application name>`ここで、 \<*アプリケーション名*> を無効にする関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fa366-112">Type `ssomanage –disableapp <application name>`, where \<*application name*> is the name of the affiliate application you want to disable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa366-113">参照</span><span class="sxs-lookup"><span data-stu-id="fa366-113">See Also</span></span>  
 <span data-ttu-id="fa366-114">[SSO 関連アプリケーション](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="fa366-114">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="fa366-115">[関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="fa366-115">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="fa366-116">[ユーザー マッピングを管理します。](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="fa366-116">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="fa366-117">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="fa366-117">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)