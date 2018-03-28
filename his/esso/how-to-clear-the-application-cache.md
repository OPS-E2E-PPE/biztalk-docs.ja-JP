---
title: アプリケーション キャッシュをクリアする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="7df3d-102">アプリケーション キャッシュをクリアする方法</span><span class="sxs-lookup"><span data-stu-id="7df3d-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="7df3d-103">MMC スナップインを使用して、または**purgecache** (すべての情報、関連アプリケーションに関連付けられている) の資格情報のキャッシュの内容を削除するコマンドのすべてのシングル サインオン (SSO) サーバー上で指定されたアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="7df3d-103">Use the MMC Snap-In or the **purgecache** command to remove the contents of the credential cache (all the information that is associated with the affiliate application) for the specified application on all Single Sign-On (SSO) servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="7df3d-104">MMC スナップインを使用してキャッシュをクリアするには</span><span class="sxs-lookup"><span data-stu-id="7df3d-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="7df3d-105">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="7df3d-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="7df3d-106">ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="7df3d-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="7df3d-107">クリックして **関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="7df3d-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="7df3d-108">結果ウィンドウで 関連アプリケーションを右クリックし、をクリックして **クリア**します。</span><span class="sxs-lookup"><span data-stu-id="7df3d-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="7df3d-109">コマンド ラインを使用してキャッシュをクリアするには</span><span class="sxs-lookup"><span data-stu-id="7df3d-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="7df3d-110">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="7df3d-110">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="7df3d-111">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="7df3d-111">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="7df3d-112">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="7df3d-112">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="7df3d-113">型`ssomanage –purgecache <application name>`ここで、 \<*アプリケーション名*> 用のキャッシュを消去する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="7df3d-113">Type `ssomanage –purgecache <application name>`, where \<*application name*> is the name of the affiliate application that you want to purge the cache for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df3d-114">参照</span><span class="sxs-lookup"><span data-stu-id="7df3d-114">See Also</span></span>  
 <span data-ttu-id="7df3d-115">[SSO 関連アプリケーション](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7df3d-115">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="7df3d-116">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="7df3d-116">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)