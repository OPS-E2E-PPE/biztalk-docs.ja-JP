---
title: 関連アプリケーションのプロパティを一覧表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], listing properties
- managing [SSO applications], listing properties
ms.assetid: a120acd7-2f0b-4c72-8a8a-f8e500a773c8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0f2ae68bc2eeafba4bb85abe8ec835dcb2b64b5
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2019
ms.locfileid: "65336855"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="98e02-102">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="98e02-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="98e02-103">ここで示すコマンドを実行すると、関連アプリケーションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98e02-103">This command shows the following information about the affiliate application.</span></span> <span data-ttu-id="98e02-104">関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="98e02-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="98e02-105">SSO システムでは、関連アプリケーションのプロパティに関する情報は、関連アプリケーションの更新に使用する XML ファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="98e02-105">The SSO system obtains this information from the xml file that you used to update the affiliate application.</span></span> <span data-ttu-id="98e02-106">詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="98e02-106">For more information, see [How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="98e02-107">管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="98e02-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1. <span data-ttu-id="98e02-108">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="98e02-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="98e02-109">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="98e02-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="98e02-110">既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="98e02-110">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="98e02-111">型 \* \* ssomanage – displayapp *\<アプリケーション名\>\*\*<em>ここで、*\<アプリケーション名\></em>を表示する関連アプリケーションの名前を指定しますプロパティです。</span><span class="sxs-lookup"><span data-stu-id="98e02-111">Type \*\*ssomanage –displayapp \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="98e02-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="98e02-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="98e02-113">クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="98e02-113">To display the properties of an affiliate application using the client utility</span></span>  
  
1. <span data-ttu-id="98e02-114">**開始** メニューのをクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="98e02-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="98e02-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="98e02-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="98e02-116">既定のインストール ディレクトリは\<*インストール ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="98e02-116">The default installation directory is \<*install drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="98e02-117">型 \* \* ssoclient – displayapp *\<アプリケーション名\>\*\*<em>ここで、*\<アプリケーション名\></em>を表示する関連アプリケーションの名前を指定しますプロパティです。</span><span class="sxs-lookup"><span data-stu-id="98e02-117">Type \*\*ssoclient –displayapp \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="98e02-118">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="98e02-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98e02-119">参照</span><span class="sxs-lookup"><span data-stu-id="98e02-119">See Also</span></span>  
 <span data-ttu-id="98e02-120">[ユーザー マッピングの管理](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="98e02-120">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="98e02-121">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="98e02-121">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)