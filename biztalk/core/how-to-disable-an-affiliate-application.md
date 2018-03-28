---
title: 関連アプリケーションを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09efa7dd00f563b8b02469909d2105d443438e95
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a><span data-ttu-id="188b9-102">関連アプリケーションを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="188b9-102">How to Disable an Affiliate Application</span></span>
<span data-ttu-id="188b9-103">MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="188b9-103">You can use the MMC Snap-In or the command line to disable the specified affiliate application.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="188b9-104">MMC スナップインを使用して関連アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="188b9-104">To disable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="188b9-105">**開始**  メニューのをクリックして **プログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="188b9-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="188b9-106">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="188b9-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="188b9-107">関連アプリケーションを右クリックし、をクリックし、 **を無効にする**です。</span><span class="sxs-lookup"><span data-stu-id="188b9-107">Right-click the affiliate application, and then click **Disable**.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="188b9-108">コマンド ラインを使用して関連アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="188b9-108">To disable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="188b9-109">をクリックして **開始**, 、 をクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="188b9-109">Click **Start**, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="188b9-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="188b9-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="188b9-111">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="188b9-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="188b9-112">型 **ssomanage – disableapp *\<アプリケーション名\>* * *、どこで\<*アプリケーション名*\>関連アプリケーションの名前を指定します。無効にします。</span><span class="sxs-lookup"><span data-stu-id="188b9-112">Type **ssomanage –disableapp *\<application name\>***, where \<*application name*\> is the name of the affiliate application you want to disable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188b9-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="188b9-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188b9-114">参照</span><span class="sxs-lookup"><span data-stu-id="188b9-114">See Also</span></span>  
 <span data-ttu-id="188b9-115">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="188b9-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="188b9-116">[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="188b9-116">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="188b9-117">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="188b9-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="188b9-118">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="188b9-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)