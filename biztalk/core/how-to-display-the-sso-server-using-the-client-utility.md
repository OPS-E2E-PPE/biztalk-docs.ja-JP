---
title: クライアント ユーティリティを使用して SSO サーバーを表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], viewing servers
- managing [SSO applications], viewing servers
- SSOClient [SSO], viewing servers
ms.assetid: af79ad96-6d94-48e0-9c80-6f0e38a3b8ac
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d83a3d8cbe1fb6dbf819c368dcd67f622385d88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338066"
---
# <a name="how-to-display-the-sso-server-using-the-client-utility"></a><span data-ttu-id="d5ada-102">クライアント ユーティリティを使用して SSO サーバーを表示する方法</span><span class="sxs-lookup"><span data-stu-id="d5ada-102">How to Display the SSO Server Using the Client Utility</span></span>
<span data-ttu-id="d5ada-103">ユーザーが現在指してシングル サインオン サーバーを表示するのにには、このコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5ada-103">Use this command to display the Single Sign-On Server to which the user is currently pointing.</span></span>  
  
### <a name="to-display-the-sso-server-using-the-client-utility"></a><span data-ttu-id="d5ada-104">クライアント ユーティリティを使用して SSO サーバーを表示するには</span><span class="sxs-lookup"><span data-stu-id="d5ada-104">To display the SSO server using the client utility</span></span>  
  
1.  <span data-ttu-id="d5ada-105">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="d5ada-105">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d5ada-106">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d5ada-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d5ada-107">既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d5ada-107">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d5ada-108">型**ssoclient – showserver**します。</span><span class="sxs-lookup"><span data-stu-id="d5ada-108">Type **ssoclient –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5ada-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5ada-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ada-110">参照</span><span class="sxs-lookup"><span data-stu-id="d5ada-110">See Also</span></span>  
 <span data-ttu-id="d5ada-111">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d5ada-111">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="d5ada-112">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="d5ada-112">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)