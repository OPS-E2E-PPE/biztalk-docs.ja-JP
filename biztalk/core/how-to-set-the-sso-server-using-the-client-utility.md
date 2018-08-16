---
title: クライアント ユーティリティを使用して SSO サーバーを設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], selecting servers
- managing [SSO applications], selecting servers
- SSOClient [SSO], selecting servers
ms.assetid: a0f1038c-60c9-4e9d-a730-1ecfa036743b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f212bb5e6601274a473c6f9854d5e23af9715cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008867"
---
# <a name="how-to-set-the-sso-server-using-the-client-utility"></a><span data-ttu-id="b8105-102">クライアント ユーティリティを使用して SSO サーバーを設定する方法</span><span class="sxs-lookup"><span data-stu-id="b8105-102">How to Set the SSO Server Using the Client Utility</span></span>
<span data-ttu-id="b8105-103">ssoclient を使用するたびに、まず、ユーザーが構成情報を含む正しいシングル サインオン サーバーを参照するように設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8105-103">Each time you use ssoclient, you must first point the user to the correct Single Sign-On server that contains their configuration information.</span></span>  
  
### <a name="to-set-the-sso-server-for-a-user-using-the-client-utility"></a><span data-ttu-id="b8105-104">クライアント ユーティリティを使用してユーザーに対して SSO サーバーを設定するには</span><span class="sxs-lookup"><span data-stu-id="b8105-104">To set the SSO Server for a user using the client utility</span></span>  
  
1. <span data-ttu-id="b8105-105">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="b8105-105">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="b8105-106">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b8105-106">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b8105-107">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="b8105-107">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="b8105-108">型<strong>ssoclient – サーバー *\<シングル サインオン サーバー\></strong><em>ここで、 \<</em>シングル サインオン サーバー\>* が、ユーザー シングル サインオン サーバーの名前に接続しようとします。</span><span class="sxs-lookup"><span data-stu-id="b8105-108">Type <strong>ssoclient –server *\<Single Sign-On Server\></strong><em>, where \<</em>Single Sign-On Server\>* is the name of the Single Sign-On server the user wants to connect to.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b8105-109">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8105-109">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8105-110">参照</span><span class="sxs-lookup"><span data-stu-id="b8105-110">See Also</span></span>  
 <span data-ttu-id="b8105-111">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b8105-111">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="b8105-112">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="b8105-112">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)