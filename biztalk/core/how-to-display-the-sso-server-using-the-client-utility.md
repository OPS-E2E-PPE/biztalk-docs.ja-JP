---
title: クライアント ユーティリティを使用して SSO サーバーを表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 1fa4394d3a45c7d0c273d82446b1a5e11d500348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970128"
---
# <a name="how-to-display-the-sso-server-using-the-client-utility"></a><span data-ttu-id="1ff9c-102">クライアント ユーティリティを使用して SSO サーバーを表示する方法</span><span class="sxs-lookup"><span data-stu-id="1ff9c-102">How to Display the SSO Server Using the Client Utility</span></span>
<span data-ttu-id="1ff9c-103">ここで示すコマンドを使用すると、ユーザーが現在接続しているシングル サインオン サーバーを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-103">Use this command to display the Single Sign-On Server to which the user is currently pointing.</span></span>  
  
### <a name="to-display-the-sso-server-using-the-client-utility"></a><span data-ttu-id="1ff9c-104">クライアント ユーティリティを使用して SSO サーバーを表示するには</span><span class="sxs-lookup"><span data-stu-id="1ff9c-104">To display the SSO server using the client utility</span></span>  
  
1.  <span data-ttu-id="1ff9c-105">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-105">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1ff9c-106">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1ff9c-107">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-107">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1ff9c-108">型 **ssoclient – showserver**します。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-108">Type **ssoclient –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ff9c-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="1ff9c-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ff9c-110">参照</span><span class="sxs-lookup"><span data-stu-id="1ff9c-110">See Also</span></span>  
 <span data-ttu-id="1ff9c-111">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1ff9c-111">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1ff9c-112">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="1ff9c-112">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)