---
title: 関連アプリケーションのプロパティを一覧表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c3ac0c77dbaad27012f104486797c4e47d1e46be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25971928"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="285ee-102">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="285ee-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="285ee-103">ここで示すコマンドを実行すると、関連アプリケーションに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="285ee-103">This command shows the following information about the affiliate application.</span></span> <span data-ttu-id="285ee-104">関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="285ee-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../core/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="285ee-105">SSO システムでは、関連アプリケーションのプロパティに関する情報は、関連アプリケーションの更新に使用する XML ファイルから取得します。</span><span class="sxs-lookup"><span data-stu-id="285ee-105">The SSO system obtains this information from the xml file that you used to update the affiliate application.</span></span> <span data-ttu-id="285ee-106">詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="285ee-106">For more information, see [How to Update the Properties of an Affiliate Application](../core/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="285ee-107">管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="285ee-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="285ee-108">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="285ee-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="285ee-109">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="285ee-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="285ee-110">既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="285ee-110">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="285ee-111">型 * * ssomanage – displayapp *\<アプリケーション名\>* * *、どこで*\<アプリケーション名\>* のプロパティを表示する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="285ee-111">Type **ssomanage –displayapp *\<application name\>***, where *\<application name\>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="285ee-112">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="285ee-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="285ee-113">クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="285ee-113">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="285ee-114">**開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。</span><span class="sxs-lookup"><span data-stu-id="285ee-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="285ee-115">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="285ee-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="285ee-116">既定のインストール ディレクトリは\<*ドライブの取り付け*\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="285ee-116">The default installation directory is \<*install drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="285ee-117">型 * * ssoclient – displayapp *\<アプリケーション名\>* * *、どこで*\<アプリケーション名\>* のプロパティを表示する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="285ee-117">Type **ssoclient –displayapp *\<application name\>***, where *\<application name\>* is the name of the Affiliate Application you want to display the properties for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="285ee-118">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="285ee-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285ee-119">参照</span><span class="sxs-lookup"><span data-stu-id="285ee-119">See Also</span></span>  
 <span data-ttu-id="285ee-120">[ユーザー マッピングを管理します。](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="285ee-120">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="285ee-121">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="285ee-121">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)