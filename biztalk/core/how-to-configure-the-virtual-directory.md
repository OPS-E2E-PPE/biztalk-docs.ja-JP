---
title: 仮想ディレクトリを構成する方法 |Microsoft Docs
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
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4a0e35a4d88c9f8a64074cef40a9c701e5e7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385975"
---
# <a name="how-to-configure-the-virtual-directory"></a><span data-ttu-id="9be70-102">仮想ディレクトリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9be70-102">How to Configure the Virtual Directory</span></span>
<span data-ttu-id="9be70-103">このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションを確認する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9be70-103">This topic describes the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="9be70-104">仮想ディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="9be70-104">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="9be70-105">%Systemdrive%、仮想ディレクトリとして構成するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9be70-105">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="9be70-106">クリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="9be70-106">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="9be70-107">展開**\<サーバー名\>** 順に展開**サイト**します。</span><span class="sxs-lookup"><span data-stu-id="9be70-107">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="9be70-108">右クリック**既定の Web サイト**クリック**仮想ディレクトリの追加**します。</span><span class="sxs-lookup"><span data-stu-id="9be70-108">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="9be70-109">**仮想ディレクトリの追加** ダイアログ ボックスで、エイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9be70-109">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="9be70-110">手順 1 で作成したフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="9be70-110">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="9be70-111">またはをクリックして **([...])** フォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="9be70-111">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="9be70-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9be70-112">Click **OK**.</span></span> <span data-ttu-id="9be70-113">下のフォルダーに表示される、**既定の Web サイト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="9be70-113">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="9be70-114">フォルダーを右クリックし、をクリックして**アプリケーションへの変換**します。</span><span class="sxs-lookup"><span data-stu-id="9be70-114">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="9be70-115">**アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="9be70-115">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="9be70-116">フォルダーは、アプリケーション (Web サイト アイコンをフォルダー アイコンから – アイコンの変更を確認できます) に変換されます。</span><span class="sxs-lookup"><span data-stu-id="9be70-116">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be70-117">参照</span><span class="sxs-lookup"><span data-stu-id="9be70-117">See Also</span></span>  
 [<span data-ttu-id="9be70-118">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="9be70-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)