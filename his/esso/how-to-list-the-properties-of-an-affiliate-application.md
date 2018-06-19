---
title: 関連アプリケーションのプロパティを一覧表示する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fac15775-39d0-470e-b9d2-21b2d02e1de7
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: e35f1f068f63d4db9738733bcada55047e81a19a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250958"
---
# <a name="how-to-list-the-properties-of-an-affiliate-application"></a><span data-ttu-id="24091-102">関連アプリケーションのプロパティを一覧表示する方法</span><span class="sxs-lookup"><span data-stu-id="24091-102">How to List the Properties of an Affiliate Application</span></span>
<span data-ttu-id="24091-103">**Displayapp**コマンドは、関連アプリケーションに関する次の情報を示します。</span><span class="sxs-lookup"><span data-stu-id="24091-103">The **displayapp** command shows the following information about the affiliate application.</span></span> <span data-ttu-id="24091-104">関連アプリケーションのプロパティの詳細については、次を参照してください。 [SSO 関連アプリケーション](../esso/sso-affiliate-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="24091-104">For more information about the properties for an affiliate application, see [SSO Affiliate Applications](../esso/sso-affiliate-applications.md).</span></span>  
  
 <span data-ttu-id="24091-105">シングル サインオン (SSO) システムでは、関連アプリケーションを更新するために使用する XML ファイルからこの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="24091-105">The Single Sign-On (SSO) system obtains this information from the XML file that you used to update the affiliate application.</span></span> <span data-ttu-id="24091-106">詳細については、次を参照してください。[関連アプリケーションのプロパティを更新する方法](../esso/how-to-update-the-properties-of-an-affiliate-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="24091-106">For more information, see [How to Update the Properties of an Affiliate Application](../esso/how-to-update-the-properties-of-an-affiliate-application.md).</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-administration-utility"></a><span data-ttu-id="24091-107">管理ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="24091-107">To display the properties of an affiliate application using the administration utility</span></span>  
  
1.  <span data-ttu-id="24091-108">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="24091-108">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="24091-109">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="24091-109">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="24091-110">既定のインストール ディレクトリは\<*ドライブ*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="24091-110">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="24091-111">型`ssomanage –displayapp <application name>`ここで、 *\<アプリケーション名 >* のプロパティを表示する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="24091-111">Type `ssomanage –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
### <a name="to-display-the-properties-of-an-affiliate-application-using-the-client-utility"></a><span data-ttu-id="24091-112">クライアント ユーティリティを使用して関連アプリケーションのプロパティを表示するには</span><span class="sxs-lookup"><span data-stu-id="24091-112">To display the properties of an affiliate application using the client utility</span></span>  
  
1.  <span data-ttu-id="24091-113">をクリックして **開始**, 、 をクリックして **実行**, 、型 `cmd`, 、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="24091-113">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="24091-114">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="24091-114">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="24091-115">既定のインストール ディレクトリは\<*ドライブの取り付け*>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="24091-115">The default installation directory is \<*install drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="24091-116">型`ssoclient –displayapp <application name>`ここで、 *\<アプリケーション名 >* のプロパティを表示する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="24091-116">Type `ssoclient –displayapp <application name>`, where *\<application name>* is the name of the affiliate application that you want to display the properties for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24091-117">参照</span><span class="sxs-lookup"><span data-stu-id="24091-117">See Also</span></span>  
 <span data-ttu-id="24091-118">[ユーザー マッピングを管理します。](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="24091-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="24091-119">関連アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="24091-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)