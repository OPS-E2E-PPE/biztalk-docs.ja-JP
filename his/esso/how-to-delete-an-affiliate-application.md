---
title: 関連アプリケーションを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="d21f9-102">関連アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="d21f9-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="d21f9-103">MMC スナップインを使用して、または**deleteapps**資格情報データベースから指定された関連アプリケーションを削除するコマンド。</span><span class="sxs-lookup"><span data-stu-id="d21f9-103">Use the MMC Snap-In or the **deleteapps** command to delete the specified affiliate application from the Credential database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d21f9-104">関連アプリケーションを削除すると、そのアプリケーションに関連付けられたすべてのマッピングが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d21f9-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d21f9-105">この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d21f9-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="d21f9-106">MMC スナップインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="d21f9-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="d21f9-107">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、順にクリック**SSO 管理**です。</span><span class="sxs-lookup"><span data-stu-id="d21f9-107">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="d21f9-108">MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="d21f9-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="d21f9-109">関連アプリケーションを右クリックし、をクリックし、 **削除**します。</span><span class="sxs-lookup"><span data-stu-id="d21f9-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="d21f9-110">コマンド ラインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="d21f9-110">To delete an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="d21f9-111">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d21f9-111">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="d21f9-112">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d21f9-112">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="d21f9-113">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d21f9-113">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d21f9-114">型`ssomanage –deleteapp <application name>`ここで、 *\<アプリケーション名 >*資格情報データベースから削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d21f9-114">Type `ssomanage –deleteapp <application name>`, where *\<application name>* is the name of the affiliate application you want to remove from the Credential database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21f9-115">参照</span><span class="sxs-lookup"><span data-stu-id="d21f9-115">See Also</span></span>  
 <span data-ttu-id="d21f9-116">[SSO 関連アプリケーション](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d21f9-116">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="d21f9-117">[関連アプリケーションを有効にする方法](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="d21f9-117">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="d21f9-118">[ユーザー マッピングを管理します。](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d21f9-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="d21f9-119">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="d21f9-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)