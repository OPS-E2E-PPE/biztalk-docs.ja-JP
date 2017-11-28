---
title: "JD Edwards OneWorld 用送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="2f238-102">JD Edwards OneWorld 用送信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="2f238-102">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="2f238-103">次の手順を使用すると、送信ポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2f238-103">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="2f238-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="2f238-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="2f238-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**に移動し、必要なアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="2f238-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="2f238-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="2f238-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2f238-107">使用することも**静的な一方向ポート**です。</span><span class="sxs-lookup"><span data-stu-id="2f238-107">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="2f238-108">**送信ポートのプロパティ** ダイアログ ボックスで、**名前**フィールドで、送信ポートの名前を入力 (たとえば、入力**SendToJDE**)。</span><span class="sxs-lookup"><span data-stu-id="2f238-108">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="2f238-109">**型**ドロップダウン リストで、 **[jdeoneworld]**です。</span><span class="sxs-lookup"><span data-stu-id="2f238-109">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="2f238-110">**URI**ドロップダウン リストで、送信ハンドラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="2f238-110">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="2f238-111">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2f238-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f238-112">参照</span><span class="sxs-lookup"><span data-stu-id="2f238-112">See Also</span></span>  
 [<span data-ttu-id="2f238-113">JD Edwards OneWorld 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="2f238-113">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)