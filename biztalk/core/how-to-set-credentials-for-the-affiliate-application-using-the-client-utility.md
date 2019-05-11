---
title: クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8c329b46e5eab5f04f5082064f1dea63505bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334520"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="a85d3-102">クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法</span><span class="sxs-lookup"><span data-stu-id="a85d3-102">How to Set Credentials for the Affiliate Application Using the Client Utility</span></span>
<span data-ttu-id="a85d3-103">このコマンドを使用して、ユーザーが特定のアプリケーションにアクセスできるように、ユーザーの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-103">Use this command to set the credentials for a user so that the user is able to access a specific application.</span></span> <span data-ttu-id="a85d3-104">このコマンドも自動的にマッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a85d3-104">This command also automatically enables the mapping.</span></span>  
  
 <span data-ttu-id="a85d3-105">このコマンドでは、入力すると、パスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a85d3-105">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="a85d3-106">ユーザー マッピングが既に存在する場合、このコマンドはその既存のマッピングの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-106">If the user mapping already exists, this command will set the credentials for that existing mapping.</span></span> <span data-ttu-id="a85d3-107">ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。</span><span class="sxs-lookup"><span data-stu-id="a85d3-107">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="a85d3-108">クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="a85d3-108">To set credentials for the affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="a85d3-109">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="a85d3-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a85d3-111">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a85d3-111">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a85d3-112">型**ssoclient – setcredentials\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** 対象となる特定のアプリケーションには資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-112">Type **ssoclient –setcredentials \<application name\>**, where **\<application name\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a85d3-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a85d3-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="a85d3-114">ユーザーの資格情報が表示されたら、このアプリケーションのユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a85d3-114">When prompted for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="a85d3-115">ユーザー マッピングを作成していない場合、SSO システムのアプリケーションのユーザー ID を求められます。</span><span class="sxs-lookup"><span data-stu-id="a85d3-115">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a85d3-116">参照</span><span class="sxs-lookup"><span data-stu-id="a85d3-116">See Also</span></span>  
 <span data-ttu-id="a85d3-117">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a85d3-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="a85d3-118">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="a85d3-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)