---
title: "仮想ディレクトリを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1461ac2ea0ef9cfee71965fc2cc800d617d1d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-virtual-directory"></a><span data-ttu-id="17c13-102">仮想ディレクトリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="17c13-102">How to Configure the Virtual Directory</span></span>
<span data-ttu-id="17c13-103">このトピックでは、仮想ディレクトリを構成し、ユーザーのアプリケーションを検証する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="17c13-103">This topic describes the procedures for configuring the virtual directory and verifying the application for a user.</span></span>  
  
### <a name="to-configure-the-virtual-directory"></a><span data-ttu-id="17c13-104">仮想ディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="17c13-104">To configure the virtual directory</span></span>  
  
1.  <span data-ttu-id="17c13-105">%systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="17c13-105">On the %systemdrive%, create a folder to be configured as a virtual directory.</span></span>  
  
2.  <span data-ttu-id="17c13-106">をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="17c13-106">Click **Start**, point to **Programs**, click **Administrative Tools**, and click **Internet Information Services (IIS) Manager**.</span></span>  
  
3.  <span data-ttu-id="17c13-107">展開**\<サーバー名 >**順に展開**サイト**です。</span><span class="sxs-lookup"><span data-stu-id="17c13-107">Expand **\<server name>** and then expand **Sites**.</span></span>  
  
4.  <span data-ttu-id="17c13-108">右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="17c13-108">Right-click **Default Web Site** and click **Add Virtual Directory**.</span></span>  
  
5.  <span data-ttu-id="17c13-109">**仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="17c13-109">In the **Add Virtual Directory** dialog box, type the alias.</span></span>  
  
6.  <span data-ttu-id="17c13-110">手順 1. で作成したフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="17c13-110">Type the path of the folder created in step 1.</span></span> <span data-ttu-id="17c13-111">またはをクリックして**([...])**フォルダーの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="17c13-111">Alternatively, click **(…)** to browse to the folder location.</span></span>  
  
7.  <span data-ttu-id="17c13-112">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17c13-112">Click **OK**.</span></span> <span data-ttu-id="17c13-113">下のフォルダーが表示されます、 **Default Web Site**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="17c13-113">The folder is displayed under the **Default Web Site** folder.</span></span>  
  
8.  <span data-ttu-id="17c13-114">フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。</span><span class="sxs-lookup"><span data-stu-id="17c13-114">Right-click the folder and click **Convert to Application**.</span></span>  
  
9. <span data-ttu-id="17c13-115">**アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="17c13-115">In the **Add Application** dialog box, click **OK**.</span></span> <span data-ttu-id="17c13-116">フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。</span><span class="sxs-lookup"><span data-stu-id="17c13-116">The folder is converted to an application (you can see the change in the icon – from a folder icon to the Web site icon).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c13-117">参照</span><span class="sxs-lookup"><span data-stu-id="17c13-117">See Also</span></span>  
 [<span data-ttu-id="17c13-118">シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="17c13-118">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)