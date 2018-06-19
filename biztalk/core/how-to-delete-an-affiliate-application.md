---
title: 関連アプリケーションを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cc742b41735f31b0da43560c19df4beb4f126d6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968768"
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="351ca-102">関連アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="351ca-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="351ca-103">MMC スナップインまたはコマンド ラインを使用して、指定した関連アプリケーションを SSO データベースから削除することができます。</span><span class="sxs-lookup"><span data-stu-id="351ca-103">You can use the MMC Snap-In or the command line to delete the specified affiliate application from the SSO database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="351ca-104">関連アプリケーションを削除すると、そのアプリケーションに関連付けられたすべてのマッピングが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="351ca-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="351ca-105">この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="351ca-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="351ca-106">MMC スナップインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="351ca-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="351ca-107">**開始**  メニューのをクリックして **プログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。</span><span class="sxs-lookup"><span data-stu-id="351ca-107">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="351ca-108">MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。</span><span class="sxs-lookup"><span data-stu-id="351ca-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="351ca-109">関連アプリケーションを右クリックし、をクリックし、 **削除**します。</span><span class="sxs-lookup"><span data-stu-id="351ca-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="351ca-110">コマンド ラインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="351ca-110">To delete an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="351ca-111">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="351ca-111">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="351ca-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="351ca-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="351ca-113">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="351ca-113">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="351ca-114">型 * * ssomanage – deleteapp *\<アプリケーション名\>* * *、どこで*\<アプリケーション名\>* を SSO データベースから削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="351ca-114">Type **ssomanage –deleteapp *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove from the SSO database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="351ca-115">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="351ca-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="351ca-116">参照</span><span class="sxs-lookup"><span data-stu-id="351ca-116">See Also</span></span>  
 <span data-ttu-id="351ca-117">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="351ca-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="351ca-118">[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="351ca-118">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="351ca-119">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="351ca-119">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="351ca-120">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="351ca-120">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)