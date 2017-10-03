---
title: "JD Edwards EnterpriseOne 用送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="3b51d-102">JD Edwards EnterpriseOne 用送信ポートの作成方法</span><span class="sxs-lookup"><span data-stu-id="3b51d-102">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="3b51d-103">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b51d-103">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="3b51d-104">送信ポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="3b51d-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="3b51d-105">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="3b51d-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3b51d-106">BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="3b51d-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="3b51d-107">右クリック**送信ポート** をクリック**新規**、クリックして**静的な送信請求-応答ポート**です。</span><span class="sxs-lookup"><span data-stu-id="3b51d-107">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="3b51d-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="3b51d-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="3b51d-109">**名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SendToJDE`)。</span><span class="sxs-lookup"><span data-stu-id="3b51d-109">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="3b51d-110">**型**ドロップダウン リストで、 **JDEdwards**です。</span><span class="sxs-lookup"><span data-stu-id="3b51d-110">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="3b51d-111">**送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。</span><span class="sxs-lookup"><span data-stu-id="3b51d-111">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="3b51d-112">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b51d-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b51d-113">参照</span><span class="sxs-lookup"><span data-stu-id="3b51d-113">See Also</span></span>  
 [<span data-ttu-id="3b51d-114">JD Edwards EnterpriseOne 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="3b51d-114">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)