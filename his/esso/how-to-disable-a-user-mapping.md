---
title: ユーザー マッピングを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="cc111-102">ユーザー マッピングを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="cc111-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="cc111-103">指定したマッピングに関連付けられたすべての操作を無効にするときに、ユーザー マッピングを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cc111-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="cc111-104">ユーザー マッピングは、削除する前に無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc111-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="cc111-105">ユーザー マッピングを無効にする場合は (D) として表示されます*\<ドメイン >\\< ユーザー名\>*ユーザー マッピングを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="cc111-105">When you disable a user mapping, it will appear as (D) *\<domain>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="cc111-106">管理ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="cc111-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="cc111-107">をクリックして**開始**、 をクリックして**実行**、型`cmd`、キーを押します**ENTER**です。</span><span class="sxs-lookup"><span data-stu-id="cc111-107">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="cc111-108">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc111-108">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="cc111-109">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="cc111-109">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="cc111-110">型`ssomanage –disablemapping <domain>\<username><application name>`ここで、 *\<ドメイン >*は Windows ドメイン ユーザー アカウントを*\<ユーザー名 >* Windows ユーザー名が無効にするには、資格情報、および*\<アプリケーション名 >*ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc111-110">Type `ssomanage –disablemapping <domain>\<username><application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name for which you want to disable the credentials, and *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="cc111-111">クライアント ユーティリティを使用してユーザー マッピングを無効にするには</span><span class="sxs-lookup"><span data-stu-id="cc111-111">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="cc111-112">をクリックして**開始**、 をクリックして**実行**、型`cmd`、キーを押します**ENTER**です。</span><span class="sxs-lookup"><span data-stu-id="cc111-112">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="cc111-113">コマンド プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="cc111-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="cc111-114">既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="cc111-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="cc111-115">型`ssoclient –disablemapping <application name>`ここで、 *\<アプリケーション名 >*ユーザー マッピングを削除する関連アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cc111-115">Type `ssoclient –disablemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc111-116">参照</span><span class="sxs-lookup"><span data-stu-id="cc111-116">See Also</span></span>  
 <span data-ttu-id="cc111-117">[SSO マッピング](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="cc111-117">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="cc111-118">[関連アプリケーションの管理](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="cc111-118">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="cc111-119">ユーザー マッピングの管理</span><span class="sxs-lookup"><span data-stu-id="cc111-119">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)