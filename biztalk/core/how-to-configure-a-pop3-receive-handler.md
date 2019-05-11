---
title: POP3 受信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive handlers, POP3 adapters
- POP3 adapters, receive handlers
- configuring [POP3 adapters], receive handlers
ms.assetid: 2191c201-545e-4d5a-a1ca-3c38c7b8258d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd3746bf9eb8c692173434cea59d45280e11805
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386974"
---
# <a name="how-to-configure-a-pop3-receive-handler"></a><span data-ttu-id="fe60d-102">POP3 受信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fe60d-102">How to Configure a POP3 Receive Handler</span></span>
<span data-ttu-id="fe60d-103">受信ハンドラーを POP3 に関連付けられているホストを変更するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe60d-103">Use the following procedure to change the host associated with the POP3 receive handler.</span></span>  
  
### <a name="to-configure-the-general-properties-for-a-pop3-receive-handler"></a><span data-ttu-id="fe60d-104">POP3 の全般プロパティの受信ハンドラを構成するには</span><span class="sxs-lookup"><span data-stu-id="fe60d-104">To configure the general properties for a POP3 receive handler</span></span>  
  
1.  <span data-ttu-id="fe60d-105">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="fe60d-105">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="fe60d-106">展開したアダプターの一覧でクリックして**POP3**、右側のウィンドウで、構成する受信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="fe60d-106">In the expanded adapter list, click **POP3**, in the right pane, right-click the receive handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="fe60d-107">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe60d-107">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="fe60d-108">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe60d-108">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe60d-109">参照</span><span class="sxs-lookup"><span data-stu-id="fe60d-109">See Also</span></span>  
 [<span data-ttu-id="fe60d-110">クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点</span><span class="sxs-lookup"><span data-stu-id="fe60d-110">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)