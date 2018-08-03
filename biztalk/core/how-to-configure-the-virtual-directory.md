---
title: 仮想ディレクトリを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: f00c5f75062ffd084cd19f23bfa66768d3d67ca5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969008"
---
# <a name="how-to-configure-the-virtual-directory"></a><span data-ttu-id="3f0f6-102">仮想ディレクトリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3f0f6-102">How to Configure the Virtual Directory</span></span>
<span data-ttu-id="3f0f6-103">このトピックでは、仮想ディレクトリを構成し、ユーザーのアプリケーションを検証する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-103">This topic describes the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="3f0f6-104">仮想ディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="3f0f6-104">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="3f0f6-105">%systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-105">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="3f0f6-106">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-106">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="3f0f6-107">展開**\<サーバー名\>** 順に展開**サイト**です。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-107">Expand **\<server name\>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="3f0f6-108">右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-108">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="3f0f6-109">**仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-109">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="3f0f6-110">手順 1. で作成したフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-110">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="3f0f6-111">またはをクリックして **([...])** フォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-111">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="3f0f6-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-112">Click **OK**.</span></span> <span data-ttu-id="3f0f6-113">下のフォルダーが表示されます、 **Default Web Site**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-113">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="3f0f6-114">フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-114">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="3f0f6-115">**アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-115">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="3f0f6-116">フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。</span><span class="sxs-lookup"><span data-stu-id="3f0f6-116">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0f6-117">参照</span><span class="sxs-lookup"><span data-stu-id="3f0f6-117">See Also</span></span>  
 [<span data-ttu-id="3f0f6-118">アダプターのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3f0f6-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)