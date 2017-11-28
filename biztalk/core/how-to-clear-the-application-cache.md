---
title: "アプリケーション キャッシュをクリアする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eacb7a786ad2729dbbea365e70c3aba8fabed5d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="668e6-102">アプリケーション キャッシュをクリアする方法</span><span class="sxs-lookup"><span data-stu-id="668e6-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="668e6-103">MMC スナップインまたはコマンド ラインを使用して、すべてのシングル サインオン サーバーの指定したアプリケーションの、資格情報キャッシュの内容 (関連アプリケーションに関連付けられたすべての情報) を削除できます。</span><span class="sxs-lookup"><span data-stu-id="668e6-103">You can use the MMC Snap-In or the command line to remove the contents of the credential cache (all the information associated with the affiliate application) for the specified application on all of the Single Sign-On Servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="668e6-104">MMC スナップインを使用してキャッシュをクリアするには</span><span class="sxs-lookup"><span data-stu-id="668e6-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="668e6-105">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="668e6-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="668e6-106">ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="668e6-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="668e6-107">をクリックして**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="668e6-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="668e6-108">結果ウィンドウで、関連アプリケーションを右クリックし、をクリックして**クリア**です。</span><span class="sxs-lookup"><span data-stu-id="668e6-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="668e6-109">コマンド ラインを使用してキャッシュをクリアするには</span><span class="sxs-lookup"><span data-stu-id="668e6-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="668e6-110">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="668e6-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="668e6-111">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="668e6-111">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="668e6-112">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="668e6-112">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="668e6-113">型**ssomanage – purgecache *\<アプリケーション名 >***ここで、 \<*アプリケーション名*> 関連アプリケーションの名前を指定しますキャッシュを消去するには。</span><span class="sxs-lookup"><span data-stu-id="668e6-113">Type **ssomanage –purgecache *\<application name>***, where \<*application name*> is the name of the affiliate application you want to purge the cache for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="668e6-114">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="668e6-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="668e6-115">参照</span><span class="sxs-lookup"><span data-stu-id="668e6-115">See Also</span></span>  
 <span data-ttu-id="668e6-116">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="668e6-116">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="668e6-117">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="668e6-117">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)