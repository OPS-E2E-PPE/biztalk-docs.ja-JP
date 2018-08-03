---
title: 仮想ディレクトリの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: bcd87b89c6c23e709f21e78e3ea98dd2b84575ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968816"
---
# <a name="configuring-the-virtual-directory"></a><span data-ttu-id="da865-102">仮想ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="da865-102">Configuring the Virtual Directory</span></span>
<span data-ttu-id="da865-103">このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションを確認する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="da865-103">This topic shows the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
## <a name="configuring-the-directory"></a><span data-ttu-id="da865-104">ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="da865-104">Configuring the Directory</span></span>  
  
#### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="da865-105">仮想ディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="da865-105">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="da865-106">%systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="da865-106">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="da865-107">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="da865-107">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="da865-108">展開**\<サーバー名\>** 順に展開**サイト**です。</span><span class="sxs-lookup"><span data-stu-id="da865-108">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="da865-109">右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="da865-109">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="da865-110">**仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="da865-110">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="da865-111">手順 1. で作成したフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="da865-111">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="da865-112">またはをクリックして **([...])** フォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="da865-112">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="da865-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="da865-113">Click **OK**.</span></span> <span data-ttu-id="da865-114">下のフォルダーが表示されます、 **Default Web Site**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="da865-114">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="da865-115">フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。</span><span class="sxs-lookup"><span data-stu-id="da865-115">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="da865-116">**アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="da865-116">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="da865-117">フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。</span><span class="sxs-lookup"><span data-stu-id="da865-117">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="verifying-an-application-for-a-user"></a><span data-ttu-id="da865-118">ユーザーに対するアプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="da865-118">Verifying an Application for a User</span></span>  
 <span data-ttu-id="da865-119">インターネット インフォメーション サービス (IIS) アプリケーションは高分離レベルで実行されます。したがって、次の手順を使用して、このアプリケーションが BizTalk Server 分離ホスト ユーザー グループのユーザーのコンテキストで実行できることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da865-119">Internet Information Services (IIS) applications run in high isolation; therefore, you must verify that the application can run in the context of a user in the BizTalk Server Isolated Host Users group by using the following procedure.</span></span>  
  
#### <a name="to-verify-an-application-for-a-user"></a><span data-ttu-id="da865-120">ユーザーのアプリケーションを検証するには</span><span class="sxs-lookup"><span data-stu-id="da865-120">To verify an application for a user</span></span>  
  
1.  <span data-ttu-id="da865-121">コントロール パネルで、開く**管理ツール**、クリックして**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="da865-121">In Control Panel, open **Administrative Tools**, and then click **Component Services**.</span></span>  
  
2.  <span data-ttu-id="da865-122">COM + アプリケーションに移動**コンポーネント サービス**です。</span><span class="sxs-lookup"><span data-stu-id="da865-122">Navigate to the COM+ application in **Component Services**.</span></span>  
  
3.  <span data-ttu-id="da865-123">COM + アプリケーションを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="da865-123">Right-click the COM+ application, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="da865-124">をクリックして**識別**BizTalk Server グループのメンバーであるユーザーにこの COM + アプリケーションを実行する id を変更するとします。</span><span class="sxs-lookup"><span data-stu-id="da865-124">Click **Identify** and change the identity under which this COM+ application runs to a user that is a member of a BizTalk Server group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da865-125">参照</span><span class="sxs-lookup"><span data-stu-id="da865-125">See Also</span></span>  
 [<span data-ttu-id="da865-126">アダプターのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="da865-126">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)