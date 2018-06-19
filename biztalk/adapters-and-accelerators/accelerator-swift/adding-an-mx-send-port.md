---
title: MX 送信ポートを追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3ad5d2f-1fcb-49d4-9974-664733308f45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cd4c16658ad0ff6b85976fbc6a97c4f397acbdb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208914"
---
# <a name="adding-an-mx-send-port"></a><span data-ttu-id="5c9c0-102">MX 送信ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-102">Adding an MX Send Port</span></span>
<span data-ttu-id="5c9c0-103">**MX 送信ポートを追加します。**</span><span class="sxs-lookup"><span data-stu-id="5c9c0-103">**To add an MX send port:**</span></span>  
  
1.  <span data-ttu-id="5c9c0-104">BizTalk Server 管理コンソールで、右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-104">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-Way Send Port**.</span></span>  
  
2.  <span data-ttu-id="5c9c0-105">送信ポートのプロパティ ダイアログ ボックスで、名前で型をボックス**MX_SendPort**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-105">In the Send Port Properties dialog box, in the Name box type **MX_SendPort**.</span></span>  
  
3.  <span data-ttu-id="5c9c0-106">トランスポート セクションで、種類 ボックスのドロップダウン リストをクリックし、選択**ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-106">In the Transport section, for the Type box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="5c9c0-107">クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-107">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="5c9c0-108">[FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-108">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="5c9c0-109">フォルダ ダイアログ ボックスの参照、ファイルの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-109">In the Browse for Folder dialog box, select a file location.</span></span>  
  
7.  <span data-ttu-id="5c9c0-110">ファイル名 ボックスに入力 **%MessageID%.xml**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-110">In the File name box, type **%MessageID%.xml**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="5c9c0-111">送信ポートのプロパティ ダイアログ ボックスでは、送信パイプライン ボックスで、ドロップダウン リストをクリックし、パイプライン プロジェクトで展開して、送信パイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-111">In the Send Port Properties dialog box, click the drop-down list for the send pipeline box, and then select the send pipeline you have deployed in the pipeline project.</span></span>  
  
9. <span data-ttu-id="5c9c0-112">左側のウィンドウでをクリックして**フィルター**、次を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-112">In the left pane, click **Filters**, and then specify the following:</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="5c9c0-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5c9c0-113">Property</span></span>|<span data-ttu-id="5c9c0-114">Microsoft.Solutions.MX_A4SWIFT です。Property.MX_A4SWIFT_Failed</span><span class="sxs-lookup"><span data-stu-id="5c9c0-114">Microsoft.Solutions.MX_A4SWIFT.Property.MX_A4SWIFT_Failed</span></span>|  
    |<span data-ttu-id="5c9c0-115">演算子</span><span class="sxs-lookup"><span data-stu-id="5c9c0-115">Operator</span></span>|<span data-ttu-id="5c9c0-116">オン = =</span><span class="sxs-lookup"><span data-stu-id="5c9c0-116">Select ==</span></span>|  
    |<span data-ttu-id="5c9c0-117">値</span><span class="sxs-lookup"><span data-stu-id="5c9c0-117">Value</span></span>|<span data-ttu-id="5c9c0-118">False</span><span class="sxs-lookup"><span data-stu-id="5c9c0-118">False</span></span>|  
  
10. <span data-ttu-id="5c9c0-119">をクリックして**適用**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-119">Click **Apply**, and then click **OK**.</span></span>  
  
11. <span data-ttu-id="5c9c0-120">送信ポート ペインで右クリック**MX_SendPort**、クリックして**開始**です。</span><span class="sxs-lookup"><span data-stu-id="5c9c0-120">In the Send Ports pane, right-click **MX_SendPort**, and then click **Start**.</span></span>