---
title: 関連アプリケーションを削除する方法 |Microsoft Docs
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
ms.openlocfilehash: b24dc6a17f6bbe30af7354b88be822cf7dcb7c08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "65338624"
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="2d324-102">関連アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="2d324-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="2d324-103">MMC スナップインまたはコマンドラインを使用すると、指定された関連アプリケーションを SSO データベースから削除します。</span><span class="sxs-lookup"><span data-stu-id="2d324-103">You can use the MMC Snap-In or the command line to delete the specified affiliate application from the SSO database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d324-104">関連アプリケーションを削除すると、SSO システムは自動的に関連付けられているすべてのマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="2d324-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2d324-105">この作業を実行するには、SSO 管理者または SSO 関連管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d324-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="2d324-106">MMC スナップインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="2d324-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="2d324-107">**開始** メニューのをクリックして**プログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="2d324-107">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="2d324-108">MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="2d324-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="2d324-109">関連アプリケーションを右クリックし、をクリックし、**削除**します。</span><span class="sxs-lookup"><span data-stu-id="2d324-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="2d324-110">コマンドラインを使用して関連アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="2d324-110">To delete an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="2d324-111">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="2d324-111">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="2d324-112">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d324-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2d324-113">既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="2d324-113">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="2d324-114">型 \* \* ssomanage – deleteapp *\<アプリケーション名\>\*\*<em>ここで、*\<アプリケーション名\></em>から削除する関連アプリケーションの名前を指定しますSSO データベース。</span><span class="sxs-lookup"><span data-stu-id="2d324-114">Type \*\*ssomanage –deleteapp \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the affiliate application you want to remove from the SSO database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2d324-115">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d324-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d324-116">参照</span><span class="sxs-lookup"><span data-stu-id="2d324-116">See Also</span></span>  
 <span data-ttu-id="2d324-117">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="2d324-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="2d324-118">[関連アプリケーションを有効にする方法](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="2d324-118">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="2d324-119">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="2d324-119">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="2d324-120">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="2d324-120">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)