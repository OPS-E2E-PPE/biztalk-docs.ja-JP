---
title: 関連アプリケーションを有効にする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 2a0e4776b60b81256552552c60aa1abb8abdcde8
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25971200"
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="a1266-102">関連アプリケーションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="a1266-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="a1266-103">MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a1266-103">You can use the MMC Snap-In or the command line to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="a1266-104">MMC スナップインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="a1266-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a1266-105">**開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a1266-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a1266-106">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="a1266-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a1266-107">関連アプリケーションを右クリックし、をクリックし、 **を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="a1266-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="a1266-108">コマンド ラインを使用して関連アプリケーションを有効にするには</span><span class="sxs-lookup"><span data-stu-id="a1266-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="a1266-109">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a1266-109">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="a1266-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a1266-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a1266-111">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a1266-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a1266-112">型 **ssomanage – enableapp *\<アプリケーション名\>* * *、どこで\<* アプリケーション名*\>する関連アプリケーションの名前を指定します。有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1266-112">Type **ssomanage –enableapp *\<application name\>***, where \<* application name*\> is the name of the affiliate application you want to enable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1266-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1266-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1266-114">参照</span><span class="sxs-lookup"><span data-stu-id="a1266-114">See Also</span></span>  
 <span data-ttu-id="a1266-115">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a1266-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="a1266-116">[関連アプリケーションを作成する方法](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="a1266-116">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="a1266-117">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a1266-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="a1266-118">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="a1266-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)