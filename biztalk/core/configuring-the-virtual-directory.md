---
title: 仮想ディレクトリの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05f694744076f4242309ed58a70903fb7aaedbda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355145"
---
# <a name="configuring-the-virtual-directory"></a><span data-ttu-id="04295-102">仮想ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="04295-102">Configuring the Virtual Directory</span></span>
<span data-ttu-id="04295-103">このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションの確認の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="04295-103">This topic shows the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
## <a name="configuring-the-directory"></a><span data-ttu-id="04295-104">ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="04295-104">Configuring the Directory</span></span>  
  
#### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="04295-105">仮想ディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="04295-105">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="04295-106">%Systemdrive%、仮想ディレクトリとして構成するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="04295-106">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="04295-107">クリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="04295-107">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="04295-108">展開**\<サーバー名\>** 順に展開**サイト**します。</span><span class="sxs-lookup"><span data-stu-id="04295-108">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="04295-109">右クリック**既定の Web サイト**クリック**仮想ディレクトリの追加**します。</span><span class="sxs-lookup"><span data-stu-id="04295-109">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="04295-110">**仮想ディレクトリの追加** ダイアログ ボックスで、エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="04295-110">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="04295-111">手順 1 で作成したフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="04295-111">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="04295-112">またはをクリックして **([...])** フォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="04295-112">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="04295-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04295-113">Click **OK**.</span></span> <span data-ttu-id="04295-114">下のフォルダーに表示される、**既定の Web サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="04295-114">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="04295-115">フォルダーを右クリックし、をクリックして**アプリケーションへの変換**します。</span><span class="sxs-lookup"><span data-stu-id="04295-115">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="04295-116">**アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="04295-116">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="04295-117">フォルダーは、アプリケーション (Web サイト アイコンをフォルダー アイコンから – アイコンの変更を確認できます) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="04295-117">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="verifying-an-application-for-a-user"></a><span data-ttu-id="04295-118">ユーザーに対するアプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="04295-118">Verifying an Application for a User</span></span>  
 <span data-ttu-id="04295-119">インターネット インフォメーション サービス (IIS) アプリケーションは高度な分離; で実行します。そのため、アプリケーションは、次の手順を使用して、BizTalk Server 分離ホスト ユーザー グループ内のユーザーのコンテキストで実行できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04295-119">Internet Information Services (IIS) applications run in high isolation; therefore, you must verify that the application can run in the context of a user in the BizTalk Server Isolated Host Users group by using the following procedure.</span></span>  
  
#### <a name="to-verify-an-application-for-a-user"></a><span data-ttu-id="04295-120">ユーザーのアプリケーションを確認するには</span><span class="sxs-lookup"><span data-stu-id="04295-120">To verify an application for a user</span></span>  
  
1.  <span data-ttu-id="04295-121">コントロール パネルで、開く**管理ツール**、 をクリックし、**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="04295-121">In Control Panel, open **Administrative Tools**, and then click **Component Services**.</span></span>  
  
2.  <span data-ttu-id="04295-122">COM + アプリケーションに移動します**コンポーネント サービス**します。</span><span class="sxs-lookup"><span data-stu-id="04295-122">Navigate to the COM+ application in **Component Services**.</span></span>  
  
3.  <span data-ttu-id="04295-123">COM + アプリケーションを右クリックし、をクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="04295-123">Right-click the COM+ application, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="04295-124">をクリックして**識別**この COM + アプリケーションを BizTalk Server グループのメンバーであるユーザーに実行する id を変更します。</span><span class="sxs-lookup"><span data-stu-id="04295-124">Click **Identify** and change the identity under which this COM+ application runs to a user that is a member of a BizTalk Server group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04295-125">参照</span><span class="sxs-lookup"><span data-stu-id="04295-125">See Also</span></span>  
 [<span data-ttu-id="04295-126">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="04295-126">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)