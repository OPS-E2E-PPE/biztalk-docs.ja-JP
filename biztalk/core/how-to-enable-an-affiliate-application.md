---
title: 関連アプリケーションを有効にする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb36c7c8d083cb72cd92cc90c088c7d8a35a9731
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004195"
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="232f9-102">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="232f9-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="232f9-103">MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="232f9-103">You can use the MMC Snap-In or the command line to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="232f9-104">MMC スナップインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="232f9-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="232f9-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="232f9-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="232f9-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="232f9-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="232f9-107">関連アプリケーションを右クリックし、**を有効にする**します。</span><span class="sxs-lookup"><span data-stu-id="232f9-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="232f9-108">コマンド ラインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="232f9-108">To enable an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="232f9-109">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="232f9-109">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="232f9-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="232f9-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="232f9-111">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="232f9-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="232f9-112">型<strong>ssomanage – enableapp *\<アプリケーション名\></strong><em>ここで、 \<</em>アプリケーション名*\>の名前を指定します。関連アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="232f9-112">Type <strong>ssomanage –enableapp *\<application name\></strong><em>, where \<</em>application name*\> is the name of the affiliate application you want to enable.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="232f9-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="232f9-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232f9-114">参照</span><span class="sxs-lookup"><span data-stu-id="232f9-114">See Also</span></span>  
 <span data-ttu-id="232f9-115">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="232f9-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="232f9-116">[関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="232f9-116">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="232f9-117">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="232f9-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="232f9-118">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="232f9-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)