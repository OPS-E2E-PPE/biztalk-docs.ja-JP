---
title: クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3ebe3e1a9e8d2ea8df421d0bade60f35d6925459
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971568"
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="a9f5f-102">クライアント ユーティリティを使用して関連アプリケーションの資格情報を設定する方法</span><span class="sxs-lookup"><span data-stu-id="a9f5f-102">How to Set Credentials for the Affiliate Application Using the Client Utility</span></span>
<span data-ttu-id="a9f5f-103">ここで示すコマンドを使用すると、ユーザーが特定のアプリケーションにアクセスできるようにユーザーの資格情報を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-103">Use this command to set the credentials for a user so that the user is able to access a specific application.</span></span> <span data-ttu-id="a9f5f-104">また、このコマンドにより、マッピングが自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-104">This command also automatically enables the mapping.</span></span>  
  
 <span data-ttu-id="a9f5f-105">このコマンドでは、入力したパスワードは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-105">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="a9f5f-106">ユーザー マッピングが既に存在する場合、このコマンドにより、その既存のマッピングに対して資格情報が設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-106">If the user mapping already exists, this command will set the credentials for that existing mapping.</span></span> <span data-ttu-id="a9f5f-107">ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-107">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a><span data-ttu-id="a9f5f-108">クライアント ユーティリティを使用して関連アプリケーションに資格情報を設定するには</span><span class="sxs-lookup"><span data-stu-id="a9f5f-108">To set credentials for the affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="a9f5f-109">**開始** メニューのをクリックして**実行**、し、入力**cmd**です。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="a9f5f-110">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="a9f5f-111">既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-111">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a9f5f-112">型**ssoclient – setcredentials\<アプリケーション名\>** ここで、 **\<アプリケーション名\>** 対象となる特定のアプリケーションは、資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-112">Type **ssoclient –setcredentials \<application name\>**, where **\<application name\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9f5f-113">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="a9f5f-114">ユーザーの資格情報を要求されたら、このアプリケーションのユーザー パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-114">When prompted for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="a9f5f-115">ユーザー マッピングを作成していない場合、SSO システムからアプリケーションのユーザー ID を入力するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="a9f5f-115">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f5f-116">参照</span><span class="sxs-lookup"><span data-stu-id="a9f5f-116">See Also</span></span>  
 <span data-ttu-id="a9f5f-117">[SSO 関連アプリケーション](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a9f5f-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="a9f5f-118">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="a9f5f-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)