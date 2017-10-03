---
title: "受信ポートの追加 MX |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69123b876bdda4b5f999277a1710cdeb1cb61fe7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-mx-receive-port"></a><span data-ttu-id="7358a-102">MX を追加する受信ポート</span><span class="sxs-lookup"><span data-stu-id="7358a-102">Adding MX Receive Port</span></span>
<span data-ttu-id="7358a-103">**追加するには、MX 受信ポート。**</span><span class="sxs-lookup"><span data-stu-id="7358a-103">**To add an MX receive port:**</span></span>  
  
1.  <span data-ttu-id="7358a-104">開始**BizTalk Server 管理コンソール**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="7358a-104">Start **BizTalk Server Administration** console.</span></span>  
  
2.  <span data-ttu-id="7358a-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="7358a-106">右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-106">Right-click **Receive Ports**, point to **New**, and then click **One-Way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="7358a-107">受信ポートのプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ の受信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-107">In the Receive Port Properties dialog box, in the Name box, type **MX_ Receive Port**.</span></span>  
  
5.  <span data-ttu-id="7358a-108">をクリックして**適用**をクリックして、ポートのバインド**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-108">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="7358a-109">右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-109">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="7358a-110">[受信ポート] ダイアログ ボックスのをクリックして**MX_ の受信ポート**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-110">In the Select a Receive Port dialog box, click **MX_ Receive Port**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="7358a-111">受信場所のプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ 受信場所**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-111">In the Receive Location Properties dialog box, in the Name box, type **MX_ Receive Location**.</span></span>  
  
9. <span data-ttu-id="7358a-112">セクションでは、トランスポート、テキスト ボックスのドロップダウン リストをクリックし、選択**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-112">In the Transport section, for the Type text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="7358a-113">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="7358a-113">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="7358a-114">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**、ファイルの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="7358a-114">In the FILE Transport Properties dialog box, click **Browse**, and then select a file location.</span></span>  
  
12. <span data-ttu-id="7358a-115">ファイル トランスポートのプロパティ ダイアログ ボックスでいることを確認\*.xml は、ファイル マスク ボックスに入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-115">In the FILE Transport Properties dialog box, ensure that \*.xml is entered in the File Mask box, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="7358a-116">受信場所のプロパティ ダイアログ ボックスで、BizTalkServerApplication を受信するハンドラー ボックスに入力することを確認します。</span><span class="sxs-lookup"><span data-stu-id="7358a-116">In the Receive Location Properties dialog box, ensure that BizTalkServerApplication is entered for the Receive handler box.</span></span>  
  
14. <span data-ttu-id="7358a-117">受信パイプライン ボックスで選択**受信パイプライン**(パイプライン プロジェクトに配置されている受信パイプライン) ドロップダウン リストからをクリックして**適用**、クリックして**ok**.</span><span class="sxs-lookup"><span data-stu-id="7358a-117">In the Receive Pipeline box, select **Receive Pipeline** (the receive pipeline that has been deployed in the Pipeline project) from the drop-down list, click **Apply**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="7358a-118">をクリックして、構成した場所を右クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="7358a-118">Right-click the location you have just configured, and then click **Enable**.</span></span>